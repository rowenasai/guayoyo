# Modelo de datos

## Principio: se guarda lo mínimo y se calcula el resto

| Se guarda | Se calcula (no se guarda) |
|---|---|
| Dosis de café (g) | Agua total = `aguaHasta` del último paso |
| Agua acumulada y tiempo acumulado de cada paso | Ratio = agua total / dosis |
| Instrucción de cada paso | Gramos de cada vertido (por diferencia con el paso anterior) |
| | Tiempo total = `tiempoHasta` del último paso |
| | Número de pasos = `pasos.length` |
| | Días desde el tueste = hoy − `fechaTueste` |

Guardar solo lo mínimo evita que dos datos se contradigan (por ejemplo, una dosis cambiada con un agua total antigua).

## Café

| Campo | Tipo | Obligatorio | Notas |
|---|---|---|---|
| `id` | texto | automático | `crypto.randomUUID()`. Imprescindible para migrar a un backend |
| `nombre` | texto | **sí** | |
| `origen` | texto | **sí** | |
| `region` | texto | no | |
| `productor` | texto | no | |
| `tostador` | texto | no | |
| `altitud` | número (msnm) | no | Mayor que 0 si se rellena |
| `fechaTueste` | fecha | no | No puede ser futura. Permite calcular los días desde el tueste (dato derivado, no se guarda) |
| `variedad` | texto | no | |
| `proceso` | texto | no | |
| `notasCata` | texto | no | |
| `imagen` | texto o `null` | no | `null` en la v1 si no se implementa la foto |
| `receta` | Receta | sí | Siempre hay una receta válida |

Los campos vacíos se guardan vacíos; mostrar "-" es decisión de la pantalla, no de los datos.

## Receta

| Campo | Tipo | Obligatorio | Notas |
|---|---|---|---|
| `dosis` | número (g) | sí | Mayor que 0 |
| `temperatura` | número (°C) | no | |
| `molienda` | texto | no | |
| `pasos` | lista de Paso | sí | Mínimo 1 |

## Paso

| Campo | Tipo | Notas |
|---|---|---|
| `nombre` | texto | "Bloom", "1er vertido"... |
| `aguaHasta` | número (g) | Agua **acumulada** en la báscula al final del paso |
| `tiempoHasta` | número (s) | Segundo en que **termina** el paso |
| `instruccion` | texto | "Vierte generando turbulencia" |

Cada paso incluye el vertido y la espera; el siguiente empieza cuando termina el tiempo del anterior.

## Validaciones
- `dosis` mayor que 0.
- Al menos un paso.
- `aguaHasta` nunca disminuye de un paso al siguiente (puede repetirse).
- `tiempoHasta` siempre aumenta de un paso al siguiente.
- `nombre` y `origen` no pueden estar vacíos.
- `altitud`, si se rellena, es un número mayor que 0.
- `fechaTueste`, si se rellena, no es posterior a hoy.

## Ejemplo: Kenya Mukurweini

```json
{
  "id": "…",
  "nombre": "Kenya Mukurweini",
  "origen": "Kenia",
  "region": "Nyeri",
  "productor": "Mukurweini",
  "variedad": "SL28",
  "proceso": "Lavado",
  "notasCata": "Almendra, naranja y té negro",
  "imagen": null,
  "receta": {
    "dosis": 18,
    "temperatura": 88,
    "molienda": "Media",
    "pasos": [
      { "nombre": "Bloom",       "aguaHasta": 50,  "tiempoHasta": 30,  "instruccion": "Vierte generando turbulencia" },
      { "nombre": "1er vertido", "aguaHasta": 150, "tiempoHasta": 75,  "instruccion": "Vierte con un poco de turbulencia" },
      { "nombre": "2do vertido", "aguaHasta": 300, "tiempoHasta": 150, "instruccion": "Vierte sin turbulencia" }
    ]
  }
}
```

Valores calculados: agua total 300 g · ratio 1:16,7 · vertidos de 50, 100 y 150 g · tiempo total 2:30.

## Escalar la receta (dosis de hoy)

Factor = dosis de hoy / dosis de la receta. Cada `aguaHasta` se multiplica por el factor y se redondea; el último paso da siempre el agua total exacta. Los tiempos no se escalan.

## Decisión de diseño: valores acumulados en lugar de porcentajes
Valoré guardar cada paso como porcentaje del agua total, pero daba números como 16,666… % y no coincide con cómo se escribe una receta ("hasta 150 g"). Los valores acumulados son naturales de escribir, simplifican el temporizador y escalan igual.

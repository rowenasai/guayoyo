# Decisiones técnicas

| Decisión | Motivo | Contrapartida |
|---|---|---|
| HTML, CSS y JavaScript puro, sin framework | Practicar lo que ya conozco y entender qué problema resolvería React | Más código manual para actualizar la pantalla |
| Módulos ES (`import` / `export`) | Cada archivo con una responsabilidad | Requiere servidor local (Live Server) |
| `localStorage`, accedido solo desde `storage.js` | Gratis, sin backend. | Datos solo en ese navegador, límite de unos 5 MB |
| Cálculos en funciones puras (`calculos.js`) | Reciben datos y devuelven resultados, sin tocar la pantalla | Requiere disciplina para no mezclar lógica e interfaz |
| Tiempo con `Date.now()` | `setInterval` se desajusta; el reloj del sistema no | La pausa necesita guardar el tiempo acumulado |
| SVG para la rueda del temporizador | Escala bien y permite dibujar tramos por paso | Se hace en dos pasos: rueda simple y luego con tramos |
| Sin librerías externas | Menos dependencias y menos riesgo; todo el código es comprensible | Más trabajo propio |
| Tests con `node --test` | Viene incluido en Node, no requiere instalar nada | Solo prueba la lógica, no la interfaz |
| Screen Wake Lock API para mantener la pantalla encendida | Sin ella el móvil se apaga a mitad de la preparación | No funciona en todos los navegadores y se libera al cambiar de pestaña: hay que reactivarla y no depender de ella |
| Hosting estático | La app son archivos estáticos y se publica al subir cambios | Revisar las condiciones vigentes del plan gratuito |

## Estructura prevista

```
guayoyo/
  docs/
  src/
    js/
      main.js        (arranque y navegación)
      storage.js     (única puerta de acceso a los datos)
      calculos.js    (funciones puras de cálculo)
      timer.js       (lógica del temporizador)
    css/
      styles.css
  index.html
  README.md
```

## Preparado para el proyecto 2 (backend)
- Todo el acceso a datos pasa por `storage.js`.
- Cada café tiene un `id` único, independiente del orden.
- Solo se guardan datos simples, convertibles a JSON.
- El campo `imagen` ya existe en el modelo.

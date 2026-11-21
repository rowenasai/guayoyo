# Roadmap (10 días)

## Fase 1: Cimientos y lógica

### Día 1: el proyecto existe y está en línea
- [x] 1.1 Crear repositorio y estructura de carpetas
- [ ] 1.2 Pasar los documentos de la Fase 0 a `docs/`
- [ ] 1.3 `index.html` con la estructura de la pantalla de preparación
- [ ] 1.4 CSS base para móvil: variables, tipografía, columna centrada
- [ ] 1.5 Primer despliegue en el hosting

### Día 2: la lógica de cálculo
- [ ] 2.1 Datos de ejemplo: el Kenya Mukurweini como objeto
- [ ] 2.2 `calculos.js`: agua total y ratio
- [ ] 2.3 `calculos.js`: gramos por vertido y tiempo total
- [ ] 2.4 `calculos.js`: escalar la receta según la dosis
- [ ] 2.5 Tests con `node --test` usando la receta del Kenya

### Día 3: la receta en pantalla
- [ ] 3.1 Mostrar la receta en pantalla a partir de los datos
- [ ] 3.2 Campo "dosis de hoy" conectado al cálculo
- [ ] 3.3 Validar la dosis (vacía, 0, negativa)
- [ ] 3.4 Función para formatear tiempo (`150` → `2:30`)

> Hito: primera versión publicada, una calculadora de la receta.

## Fase 2: Temporizador

### Día 4: el reloj
- [ ] 4.1 Reloj con `Date.now()`: iniciar y mostrar el tiempo
- [ ] 4.2 Actualizar la pantalla sin desajustarse
- [ ] 4.3 Pausar y reanudar
- [ ] 4.4 Rueda SVG simple que se va llenando

### Día 5: los pasos
- [ ] 5.1 Detectar en qué paso estamos
- [ ] 5.2 Mostrar paso actual, instrucción, meta de agua y siguiente paso
- [ ] 5.3 Dividir la rueda en tramos proporcionales
- [ ] 5.4 Estado "Final": el reloj sigue y botón "Terminar"

> Hito: temporizador completo con la receta real.

## Fase 3: Cafés y recetas

### Día 6: guardar y listar
- [ ] 6.1 `storage.js`: guardar y leer cafés en `localStorage`
- [ ] 6.2 Pantalla de inicio: lista, estado vacío y cafés de ejemplo
- [ ] 6.3 Navegación entre pantallas
- [ ] 6.4 Formulario para añadir un café (con los campos opcionales: tostador, altitud y fecha de tueste)

### Día 7: editar, borrar y editor de pasos
- [ ] 7.1 Editar un café
- [ ] 7.2 Borrar con confirmación
- [ ] 7.3 Editor de pasos: añadir y quitar
- [ ] 7.4 Validaciones de los pasos

> Hito: MVP completo.

## Fase 4: Pulido y robustez

### Día 8: la experiencia de uso
- [ ] 8.1 Sonidos al cambiar de paso y al final
- [ ] 8.2 Señal visual para quien tenga el móvil en silencio
- [ ] 8.3 Mensajes de error y estados vacíos
- [ ] 8.4 Probar en un móvil real y corregir
- [ ] 8.5 Pantalla siempre encendida durante el temporizador (Wake Lock), con reactivación al volver a la pestaña

### Día 9: calidad del código
- [ ] 9.1 Limpiar el código: nombres claros, funciones cortas, comentarios útiles
- [ ] 9.2 Más tests, incluyendo casos raros
- [ ] 9.3 Revisión de seguridad: nada de `innerHTML` con texto del usuario; validar los datos leídos de `localStorage`
- [ ] 9.4 Accesibilidad básica: contraste, etiquetas de formulario, teclado
- [ ] 9.5 (opcional) Búsqueda de cafés

## Fase 5: Publicación

### Día 10
- [ ] 10.1 Capturas y GIF corto del temporizador
- [ ] 10.2 README completo
- [ ] 10.3 Despliegue final y prueba desde otro dispositivo
- [ ] 10.4 Tarjeta del proyecto y enlace en el portfolio
- [ ] 10.5 (opcional) Foto del café

## Si voy justa, se recorta en este orden
Foto · búsqueda · tramos de la rueda · sonido.
El README y el despliegue no se recortan.

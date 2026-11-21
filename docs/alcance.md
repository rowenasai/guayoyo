# Alcance del proyecto

## Problema
Quienes preparan café de filtro en casa o en el trabajo suelen tener varios cafés con recetas distintas. Muchas de esas recetas están apuntadas en notas, cuadernos o simplemente en la memoria. Guayoyo permite guardar cada café con su receta y seguirla paso a paso con un temporizador.

## Objetivo del proyecto
- Aprender a construir una aplicación web desde cero con HTML, CSS y JavaScript.
- Aplicar lógica real: cálculo de recetas, temporizador, validaciones y persistencia de datos.
- Publicar una pieza de portfolio funcional y bien documentada.

## Por qué este proyecto
En lugar del típico proyecto de principiante (una calculadora o un temporizador sueltos), lo apliqué a un contexto en el que me muevo a diario, tanto en el trabajo como en casa: el café de especialidad.

## Para quién
Baristas aficionados y profesionales que usan V60, tienen varios cafés y necesitan sus recetas en un solo lugar, con la guía de un temporizador.

## MVP (versión 1)

| Entra en el MVP |
|---|
| Lista de cafés con sus datos (nombre, origen, región, productor, variedad, proceso, altitud, tostador, fecha de tueste, notas de cata) |
| Añadir, editar y borrar cafés |
| Una receta por café, con pasos editables |
| Cálculo de agua, ratio y gramos de cada vertido |
| Dosis "de hoy" sin modificar la receta guardada |
| Temporizador guiado con rueda por tramos, pausa y final |
| Señal sonora y visual al cambiar de paso |
| Pantalla encendida mientras corre el temporizador |
| Datos guardados en el navegador (`localStorage`) |

## Opcional
- Búsqueda de cafés por nombre
- Foto del café

## Fuera del MVP
- Cuentas de usuario y sincronización entre dispositivos
- Subida de imágenes a la nube
- Varias recetas por café
- Otros métodos de preparación (Aeropress, prensa francesa...)
- Historial de preparaciones
- PWA instalable y offline
- Separar "vertido" y "espera" dentro de un paso

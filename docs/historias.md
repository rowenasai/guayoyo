# Historias de usuario

Prioridad: **M** imprescindible · **S** deseable · **C** opcional.

## Cafés

| # | Historia | Criterios de aceptación | P |
|---|---|---|---|
| 1 | Como usuaria, quiero ver la lista de mis cafés, para elegir cuál preparar | Se ven nombre y datos principales · campos vacíos con "-" · si no hay cafés, mensaje y opción de añadir el primero | M |
| 2 | Como usuaria, quiero añadir un café con sus datos, para tenerlo en mi lista | Nombre y origen obligatorios · resto opcional (incluidos tostador, altitud y fecha de tueste) · altitud, si se rellena, es un número mayor que 0 · al guardar vuelvo a la lista y aparece · al recargar sigue ahí | M |
| 3 | Como usuaria, quiero modificar los datos de un café, para corregir errores o actualizarlos | Formulario relleno con los datos actuales · si salgo sin guardar, no se aplican cambios | M |
| 4 | Como usuaria, quiero eliminar un café, para mantener mi lista ordenada | Pide confirmación · desaparece de la lista y no vuelve al recargar | M |
| 5 | Como usuaria, quiero buscar un café por nombre, para encontrarlo rápido | La lista se filtra mientras escribo · si no hay resultados, lo indica | S |
| 6 | Como usuaria, quiero añadir una foto a un café, para reconocerlo de un vistazo | Acepto solo imágenes · se reduce de tamaño antes de guardarla · sin foto, se muestra una imagen por defecto | C |

## Recetas

| # | Historia | Criterios de aceptación | P |
|---|---|---|---|
| 7 | Como usuaria, quiero definir la receta de un café, para prepararlo siempre igual | Dosis mayor que 0 · temperatura y molienda opcionales · un café nuevo trae una receta base · se muestran agua total, ratio y tiempo total calculados | M |
| 8 | Como usuaria, quiero añadir un paso a la receta, para describir cada vertido | Cada paso tiene nombre, agua hasta (g), tiempo hasta (s) e instrucción · el agua no puede ser menor que la del paso anterior · el tiempo debe ser mayor que el del anterior · el error se muestra junto al campo | M |
| 9 | Como usuaria, quiero modificar o quitar un paso, para ajustar mi receta | Se puede cambiar cualquier campo · no se puede quitar el último paso · los totales se recalculan al instante | M |

## Cálculo

| # | Historia | Criterios de aceptación | P |
|---|---|---|---|
| 10 | Como usuaria, quiero ver cuánta agua llevo en cada vertido, para no hacer cuentas | Agua total = agua hasta del último paso · los gramos de cada vertido se calculan por diferencia · se muestra el ratio | M |
| 11 | Como usuaria, quiero cambiar la dosis solo para hoy, para preparar otra cantidad sin tocar mi receta | La dosis no puede estar vacía ni ser 0 · el agua de cada paso se recalcula en proporción · los tiempos no cambian · la receta guardada no se modifica | M |

## Temporizador

| # | Historia | Criterios de aceptación | P |
|---|---|---|---|
| 12 | Como usuaria, quiero iniciar la preparación, para que el temporizador me guíe | Parte de 0:00 · la rueda muestra un tramo por paso, proporcional a su duración | M |
| 13 | Como usuaria, quiero ver en qué paso estoy, para saber qué hacer en cada momento | Se ven nombre del paso, instrucción, meta de agua acumulada y siguiente paso | M |
| 14 | Como usuaria, quiero recibir un aviso al cambiar de paso, para no mirar la pantalla todo el rato | Suena una señal al empezar cada paso y otra al final · hay también señal visual, por si el móvil está en silencio | M |
| 15 | Como usuaria, quiero pausar y reanudar, para poder parar si me interrumpen | Al reanudar, el tiempo continúa donde se quedó · el tiempo es correcto aunque cambie de pestaña | M |
| 16 | Como usuaria, quiero terminar la preparación, para cerrar el proceso | Al llegar al tiempo total aparece "Final" y el reloj sigue contando · "Terminar" vuelve a la pantalla anterior · si paro antes de tiempo, pide confirmación | M |
| 17 | Como usuaria, quiero que la pantalla no se apague mientras preparo, para no tocar el móvil con las manos ocupadas | La pantalla permanece encendida mientras corre el temporizador · si el navegador no lo permite, la app sigue funcionando sin error · al volver a la pestaña con el temporizador en marcha, se vuelve a activar | M |

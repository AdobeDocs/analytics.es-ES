---
title: Resolución del monitor
description: Resolución del monitor del visitante en píxeles.
translation-type: ht
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: ht
source-wordcount: '239'
ht-degree: 100%

---


# Resolución del monitor

La dimensión “Resolución del monitor” muestra la altura y la anchura de la pantalla activa en píxeles. Esta dimensión es útil cuando desea saber dónde está el “pliegue” en el sitio para los visitantes o en qué medida pueden ampliar los visitantes su ventana del explorador. Conocer la ubicación del pliegue permite optimizar la visualización del contenido.

Esta dimensión es diferente a la altura y la anchura del explorador. La altura y la anchura del explorador es el número de píxeles dentro del espacio del explorador visible, mientras que la resolución del monitor es el número de píxeles de todo el monitor. Si desea ver la diferencia entre estas dos variables en su propio equipo, abra la consola del explorador (F12 en la mayoría de los exploradores) y copie y pegue el siguiente código en la consola:

```js
"Monitor resolution: " + screen.width + "x" + screen.height + "\nBrowser resolution: " + window.innerWidth + "x" + window.innerHeight;
```

Las dimensiones del explorador son siempre más pequeñas que la resolución del monitor, ya que las dimensiones del explorador no incluyen la navegación del explorador ni los bordes.

## Rellene esta dimensión con datos

Esta dimensión recupera datos de la [`s`cadena de consulta](/help/implement/validate/query-parameters.md) en solicitudes de imagen. AppMeasurement recopila estos datos mediante la variable JavaScript `screen.width` y `screen.height` en el explorador. Si utiliza una biblioteca de AppMeasurement (por ejemplo, mediante Adobe Experience Platform Launch), esta dimensión funciona de forma predeterminada. Si utiliza un método de recopilación de datos fuera de AppMeasurement (por ejemplo, a través de la API), asegúrese de incluir el parámetro de cadena de consulta `s` en las solicitudes de imágenes.

## Elementos de dimensión

Los elementos de dimensión incluyen todas las resoluciones de monitor recopiladas. Los valores de ejemplo incluyen `1920 x 1080`, `1366 x 768` y `1280 x 720`.

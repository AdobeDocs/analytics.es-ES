---
title: Resolución del monitor
description: Resolución del monitor del visitante en píxeles.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 1%

---


# Resolución del monitor

La dimensión &#39;Resolución del monitor&#39; muestra la altura y la anchura de la pantalla activa en píxeles. Esta dimensión es útil cuando desea comprender dónde se encuentra el &quot;pliegue&quot; en el sitio para los visitantes o en qué medida los visitantes pueden hacer que la ventana del explorador sea amplia. El comprender dónde se encuentra el pliegue le permite optimizar el contenido para su visualización.

Esta dimensión es diferente a la altura y la anchura del explorador. La altura y la anchura del explorador es el número de píxeles dentro del espacio del explorador visible, mientras que la resolución del monitor es el número de píxeles de todo el monitor. Si desea ver la diferencia entre estas dos variables en su propio equipo, abra la consola del explorador (F12 en la mayoría de los exploradores) y copie y pegue el siguiente código en la consola:

```js
"Monitor resolution: " + screen.width + "x" + screen.height + "\nBrowser resolution: " + window.innerWidth + "x" + window.innerHeight;
```

Las dimensiones del navegador son siempre más pequeñas que la resolución del monitor, ya que las dimensiones del navegador no incluyen la navegación del navegador ni los bordes.

## Rellenar esta dimensión con datos

Esta dimensión recupera datos de la cadena [`s` de](/help/implement/validate/query-parameters.md) consulta en solicitudes de imagen. AppMeasurement recopila estos datos mediante la variable JavaScript `screen.width` y `screen.height` en el explorador. Si utiliza una biblioteca de AppMeasurement (por ejemplo, mediante Adobe Experience Platform Launch), esta dimensión funciona de forma predeterminada. Si utiliza un método de recopilación de datos fuera de AppMeasurement (por ejemplo, a través de la API), asegúrese de incluir el parámetro de cadena de `s` consulta en las solicitudes de imagen.

## Elementos de dimensión

Los elementos de dimensión incluyen todas las resoluciones de monitor recopiladas. Los valores de ejemplo incluyen `1920 x 1080`, `1366 x 768`y `1280 x 720`.

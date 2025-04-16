---
title: Resolución del monitor
description: Resolución del monitor del visitante en píxeles.
feature: Dimensions
exl-id: 6bae65eb-4546-4d07-877d-6e257fbe6cfa
source-git-commit: e3a1c1fde3809cb73b1bda091b8be43778515d1a
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 72%

---

# Resolución del monitor

La &#39;Resolución del monitor&#39; [dimensión](overview.md) muestra la altura y anchura de la pantalla activa en píxeles. Esta dimensión es útil cuando desea saber dónde está el “pliegue” en el sitio para los visitantes o en qué medida pueden ampliar los visitantes su ventana del explorador. Conocer la ubicación del pliegue permite optimizar la visualización del contenido.

Esta dimensión es diferente a la [altura](browser-height.md) y la [anchura](browser-width.md) del explorador. La altura y la anchura del explorador es el número de píxeles dentro del espacio del explorador visible, mientras que la resolución del monitor es el número de píxeles de todo el monitor. Si desea ver la diferencia entre estas dos variables en su propio equipo, abra la consola del explorador (F12 en la mayoría de los exploradores) y copie y pegue el siguiente código en la consola:

```js
"Monitor resolution: " + screen.width + "x" + screen.height + "; Browser resolution: " + window.innerWidth + "x" + window.innerHeight;
```

Las dimensiones del explorador son siempre más pequeñas que la resolución del monitor, ya que las dimensiones del explorador no incluyen la navegación del explorador ni los bordes.

## Rellene esta dimensión con datos

Esta dimensión recupera datos de la [`s`cadena de consulta](/help/implement/validate/query-parameters.md) en solicitudes de imagen. AppMeasurement recopila estos datos mediante la variable JavaScript `screen.width` y `screen.height` en el explorador. Si utiliza una biblioteca de AppMeasurement (por ejemplo, mediante etiquetas en Adobe Experience Platform), esta dimensión funciona de forma predeterminada.

Si utiliza un método de recopilación de datos fuera de AppMeasurement (por ejemplo, a través de la API), asegúrese de incluir el parámetro de cadena de consulta `s` en las solicitudes de imagen. Si falta la cadena de consulta `s` o si una biblioteca de recopilación de datos no puede recopilar la resolución del monitor, esos datos se muestran en [!UICONTROL `Not Specified`].

## Elementos de dimensión

Los elementos de dimensión incluyen todas las resoluciones de monitor recopiladas. Los valores de ejemplo incluyen `1920 x 1080`, `1366 x 768` y `1280 x 720`.

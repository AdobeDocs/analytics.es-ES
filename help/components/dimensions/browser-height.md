---
title: Altura del explorador - agrupada
description: Altura de la ventana del explorador en píxeles.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 0%

---


# Altura del explorador

La dimensión &#39;Altura del explorador - agrupada&#39; muestra la altura de la ventana del explorador, clasificada en grupos de 100 píxeles. Esta dimensión es útil cuando desea comprender dónde está el &quot;pliegue&quot; en el sitio para los visitantes. El comprender dónde se encuentra el pliegue le permite optimizar el contenido para su visualización.

Esta dimensión es diferente a la altura de la pantalla. La altura del explorador es el número de píxeles dentro del espacio visible del explorador, mientras que la altura de la pantalla es la altura de todo el monitor en píxeles. Si desea ver la diferencia entre estas dos variables en su propio equipo, abra la consola del explorador (F12 en la mayoría de los exploradores) y copie y pegue el siguiente código en la consola:

```javascript
"Browser height: " + window.innerHeight + " pixels\nScreen height: " + screen.height + " pixels";
```

La altura del explorador siempre es menor o igual a la altura de la pantalla, ya que la altura del explorador no incluye la navegación del explorador ni los bordes.

## Rellenar esta dimensión con datos

Esta dimensión recupera datos de la cadena [`bh` de](/help/implement/validate/query-parameters.md) consulta en solicitudes de imagen. AppMeasurement recopila estos datos mediante la variable JavaScript `window.innerHeight` en el explorador. Si utiliza una biblioteca de AppMeasurement (por ejemplo, mediante Adobe Experience Platform Launch), esta dimensión funciona de forma predeterminada. Si utiliza un método de recopilación de datos fuera de AppMeasurement (por ejemplo, a través de la API), asegúrese de incluir el parámetro de cadena de `bh` consulta en la primera visita individual de cada visita.

Adobe mantiene la altura del explorador durante una visita. Si la altura del explorador se ajusta a mitad de la visita, el ajuste no se registra.

## Elementos de dimensión

Los elementos de dimensión incluyen todas las alturas recopiladas del navegador, clasificadas en grupos de 100 píxeles. Por ejemplo, si la altura del navegador de una visita es `720`, se agrupa en el elemento de dimensión `700 to 799`.

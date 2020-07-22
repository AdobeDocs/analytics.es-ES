---
title: Ancho del explorador - agrupado
description: Ancho de la ventana del explorador en píxeles.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 0%

---


# Ancho del explorador

La dimensión &#39;Ancho del explorador - agrupado&#39; muestra la anchura de la ventana del explorador, clasificada en grupos de 100 píxeles. Esta dimensión es útil cuando desea comprender la amplitud con la que los visitantes ven el contenido. El comprender la amplitud con la que se visualiza el contenido puede permitirle optimizar el contenido para su visualización.

Esta dimensión es diferente al ancho de pantalla. El ancho del explorador es el número de píxeles dentro del espacio del explorador visible, mientras que el ancho de pantalla es el ancho de todo el monitor en píxeles. Si desea ver la diferencia entre estas dos variables en su propio equipo, abra la consola del explorador (F12 en la mayoría de los exploradores) y copie y pegue el siguiente código en la consola:

```javascript
"Browser width: " + window.innerWidth + " pixels\nScreen width: " + screen.width + " pixels";
```

El ancho del explorador siempre es menor o igual al ancho de la pantalla, ya que el ancho del explorador no incluye barras de desplazamiento ni bordes.

## Rellenar esta dimensión con datos

Esta dimensión recupera datos de la cadena [`bw` de](/help/implement/validate/query-parameters.md) consulta en solicitudes de imagen. AppMeasurement recopila estos datos mediante la variable JavaScript `window.innerWidth` en el explorador. Si utiliza una biblioteca de AppMeasurement (por ejemplo, mediante Adobe Experience Platform Launch), esta dimensión funciona de forma predeterminada. Si utiliza un método de recopilación de datos fuera de AppMeasurement (por ejemplo, a través de la API), asegúrese de incluir el parámetro de cadena de `bw` consulta en la primera visita individual de cada visita.

Adobe mantiene el ancho del navegador para una visita. Si el ancho del explorador se ajusta a mitad de la visita, el ajuste no se registra.

## Elementos de dimensión

Los elementos de dimensión incluyen todos los anchos recopilados del navegador, clasificados en grupos de 100 píxeles. Por ejemplo, si el ancho del navegador de una visita individual es `1280`, se agrupa en el elemento de dimensión `1200 to 1299`.

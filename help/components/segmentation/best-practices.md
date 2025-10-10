---
title: Prácticas recomendadas
description: Conozca algunas prácticas recomendadas de segmentación.
feature: Segmentation
exl-id: 4115a804-5063-430a-b9d3-2b64b26ca4d8
source-git-commit: 35f2812c1a1a4eed090e04d67014fcebf88a80ec
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 60%

---

# Prácticas recomendadas de segmentación

Los segmentos complejos suelen ser necesarios para obtener los datos deseados. Si los segmentos complejos son ineficientes y se utilizan en un grupo de informes grande, la creación de los informes tarda mucho más. Tenga en cuenta los siguientes recursos al crear o editar un segmento para minimizar la complejidad.

## Usar solamente el operador `Contains` como último recurso

El operador [**[!UICONTROL Contains ]**](/help/components/segmentation/seg-reference/seg-operators.md) es una de las características de segmentación que requiere más procesamiento, ya que el operador debe analizar todo el contenido de cada valor. Considere la posibilidad de utilizar otros operadores, como**[!UICONTROL  Comienza con ]**o**[!UICONTROL  Finaliza con ]**, si los valores deseados se encuentran al principio o al final de una cadena.

Si el operador **[!UICONTROL Contains]** de un segmento devuelve un gran número de resultados, el informe suele agotar el tiempo de espera. Por ejemplo, si creó un segmento donde **[!UICONTROL Referente]** **[!UICONTROL es igual a]** `"."`, el segmento busca a través del contenido de cada valor. Considere utilizar el operador **[!UICONTROL Exists]** en su lugar.

## Usar clasificaciones para agrupar elementos de dimensión

Si tiene muchas condiciones de segmento, pueden degradar rápidamente el rendimiento del segmento. Por ejemplo, **[!UICONTROL Página]** **[!UICONTROL es igual que]** `X` **[!UICONTROL O]** **[!UICONTROL Página]** **[!UICONTROL es igual que]** `Y` **[!UICONTROL O]** **[!UICONTROL Página]** **[!UICONTROL es igual que]** `Z` se repite con cientos de valores diferentes. En lugar de escribir estos cientos de condiciones, clasifique todos los valores deseados en un segmento y luego utilice el valor clasificado en un segmento.

1. Cree una clasificación para la variable con la que esté trabajando.
2. Descargue la plantilla de clasificación y ábrala en la hoja de cálculo o en el editor de texto que desee.
3. Asigne el mismo valor a cada elemento de dimensión que desee incluir en el segmento.
4. Usar el importador de clasificaciones para volver a importar la hoja de cálculo en Adobe Analytics
5. Una vez que la clasificación haya terminado de procesarse, cree un segmento usando el valor clasificado.

Este método aumenta drásticamente el rendimiento y proporciona una manera fácil de modificar las condiciones de los segmentos. En lugar de editar el segmento con valores diferentes, puede añadir o eliminar elementos de dimensión de la clasificación.

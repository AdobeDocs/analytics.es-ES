---
title: Prácticas recomendadas de segmentación
description: Cree segmentos óptimos que devuelvan datos de forma eficaz.
translation-type: tm+mt
source-git-commit: e758c070f402113b6d8a9069437b53633974a3e9
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 0%

---


# Prácticas recomendadas de segmentación

Los segmentos complejos suelen ser necesarios para obtener los datos deseados. Si los segmentos complejos son ineficientes y se utilizan en un grupo de informes grande, la ejecución de los informes tarda mucho más. Tenga en cuenta los siguientes recursos al crear o editar un segmento para minimizar la complejidad.

## Utilice únicamente el operador &#39;Contains&#39; como último recurso

El operador &#39;Contiene&#39; es una de las características de segmentación que más requiere procesamiento, ya que tiene que analizar todo el contenido de cada valor. Considere la posibilidad de utilizar otros operadores, como &quot;Inicios con&quot; o &quot;Termina con&quot;, si los valores deseados se encuentran al principio o al final de una cadena.

Si el operador &#39;Contiene&#39; de un segmento devuelve un gran número de resultados, el informe suele agotar el tiempo de espera. Por ejemplo, si ha creado un segmento en el que `Referrer equals "."`, el segmento busca a través del contenido de cada valor. Considere utilizar el operador &#39;Existe&#39; en su lugar.

## Usar clasificaciones para agrupar elementos de dimensión

Si tiene muchas condiciones de segmento, pueden degradar rápidamente el rendimiento del segmento. Por ejemplo, `Page equals X or Page equals Y or Page equals Z` se repite con cientos de valores diferentes. En lugar de escribir estos cientos de condiciones, clasifique todos los valores deseados en un segmento y luego utilice el valor clasificado en un segmento.

1. Cree una clasificación para la variable con la que esté trabajando.
2. Descargue la plantilla de clasificación y ábrala en la hoja de cálculo o en el editor de texto que desee.
3. Asigne el mismo valor a cada elemento de dimensión que desee incluir en el segmento.
4. Use el importador de clasificaciones para volver a importar la hoja de cálculo en Adobe Analytics
5. Una vez que la clasificación haya terminado de procesarse, cree un segmento usando el valor clasificado.

Este método aumenta drásticamente el rendimiento y proporciona una manera fácil de modificar las condiciones de los segmentos. En lugar de editar el segmento con valores diferentes, puede agregar o eliminar elementos de dimensión de la clasificación.

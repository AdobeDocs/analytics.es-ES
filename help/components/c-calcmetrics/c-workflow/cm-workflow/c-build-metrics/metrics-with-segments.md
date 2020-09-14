---
description: 'La segmentación de una métrica individual le permite realizar comparaciones de métricas dentro del mismo informe. '
title: Métricas segmentadas
uuid: 88f9829b-76e4-4598-9494-084a91602bc1
translation-type: tm+mt
source-git-commit: 234a2eadfe02322daa886d2edbea042f8ad99e1e
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 59%

---


# Métricas segmentadas

En el creador de métricas calculadas, puede aplicar segmentos dentro de su definición de métrica. Esto resulta útil si desea derivar nuevas métricas para utilizarlas en la análisis. Tenga en cuenta que las definiciones de segmentos se pueden actualizar a través del Generador de segmentos. Si se realizan cambios, el segmento se actualizará automáticamente en cualquier lugar donde se aplique, incluso si forma parte de una definición de métrica calculada.

![](assets/german-visitors.png)

## Crear una métrica segmentada {#create}

Supongamos que desea comparar diferentes aspectos de los segmentos de &quot;Visitantes alemanes&quot; con los de un segmento de &quot;Visitantes internacionales&quot;. Puede crear métricas que le proporcionarán información como:

* ¿De qué forma se compara el contenido de navegación ente los dos grupos? (Otro ejemplo sería: ¿De qué forma se compara la tasa de conversión entre los dos segmentos?)
* Como porcentaje del total de visitantes, ¿cuántos visitantes alemanes navegan por determinadas páginas en comparación con los visitantes internacionales?
* ¿Cuáles son las principales diferencias en términos de a qué contenido se accede desde estos segmentos diferentes?

1. Si no tiene un segmento comparable, cree un segmento ad hoc en el Creador de métricas calculadas llamado &quot;Visitantes alemanes&quot;, donde &quot;Países&quot; es igual a &quot;Alemania&quot;. Arrastre la dimensión de países al lienzo de definición y seleccione que el valor sea Alemania:

   ![](assets/segment-from-dimension.png)

   >[!NOTE]
   >
   >También puede llevar a cabo esta acción en el [Generador de segmentos](/help/components/segmentation/segmentation-workflow/seg-build.md), pero hemos simplificado el flujo de trabajo al establecer que las dimensiones estén disponibles en el creador de métricas calculadas. &quot;Adhoc&quot; means that the segment is not visible in the **[!UICONTROL Segments]** list in the left rail. Sin embargo, puede hacerlo público si pasa el ratón por el icono “i”, que se sitúa junto a ella, y hace clic en **[!UICONTROL Hacer público]**.

1. Si no tiene ningún segmento comparable, cree un segmento que se llame “Visitantes internacionales” en el que “Países” no sea igual a “Alemania”.
1. Cree y guarde una métrica llamada “Visitantes de Alemania” arrastrando el segmento de Alemania al lienzo Definición y la métrica de Visitantes únicos dentro de este:

   ![](assets/german-visitors.png)

1. Repita el paso 3 con el segmento de Visitantes internacionales y la métrica de Visitantes únicos para crear una métrica de Visitantes internacionales.
1. En Analysis Workspace, arrastre la dimensión **[!UICONTROL Página]** a una tabla de formato libre y, luego, las dos métricas calculadas nuevas en paralelo en la parte superior:

   ![](assets/workspace-pages.png)

## Porcentaje de métricas totales {#percent-total}

Puede llevar el ejemplo anterior un paso más allá comparando el segmento con una población total. Para ello, cree dos métricas nuevas, &quot;% de los Visitantes totales de Alemania&quot; y &quot;% de los Visitantes internacionales totales&quot;:

1. Coloque el segmento de Visitantes de Alemania (o internacionales) en el lienzo.
1. Coloque otro segmento de Visitantes de Alemania (o internacionales) a continuación. Sin embargo, en esta ocasión, haga clic en el icono de configuración (el engranaje) para seleccionar “Total” como Tipo de métrica. El formato debe ser “Porcentaje”. El operador debe ser “dividido por”. Al final, tendrá esta definición de métrica:

   ![](assets/cm_metric_total.png)

1. Aplique esta métrica a su proyecto:

   ![](assets/cm_percent_total.png)


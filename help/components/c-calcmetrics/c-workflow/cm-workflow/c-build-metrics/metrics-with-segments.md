---
description: La segmentación de una métrica individual le permite realizar comparaciones de métricas dentro del mismo informe.
title: Métricas segmentadas
feature: Calculated Metrics
exl-id: 1e7e048b-9d90-49aa-adcc-15876c864e04
source-git-commit: 08e29da4847e8ef70bd4435949e26265d770f557
workflow-type: tm+mt
source-wordcount: '477'
ht-degree: 68%

---

# Métricas segmentadas

En el Creador de métricas calculadas, puede aplicar segmentos dentro de su definición de métrica. Esto es útil si desea derivar nuevas métricas para usarlas en el análisis. Tenga en cuenta que las definiciones de segmentos se pueden actualizar a través del Generador de segmentos. Si se realizan cambios, el segmento se actualizará automáticamente en cualquier lugar donde se aplique, incluso si forma parte de una definición de métrica calculada.

![](assets/german-visitors.png)

## Creación de una métrica segmentada {#create}

Digamos que desea comparar distintos aspectos de los segmentos de “Visitantes alemanes” para aquellos de un segmento en “Visitantes internacionales”. Puede crear métricas que le proporcionarán información como:

* ¿De qué forma se compara el contenido de navegación ente los dos grupos? (Otro ejemplo sería: ¿De qué forma se compara la tasa de conversión entre los dos segmentos?)
* Como un porcentaje de visitantes totales, ¿cuántos visitantes alemanes navegan por ciertas páginas en comparación con los visitantes internacionales?
* ¿Cuáles son las principales diferencias en términos de a qué contenido se accede desde estos segmentos diferentes?

Cree y guarde una métrica llamada &quot;Visitantes alemanes&quot; y una métrica llamada &quot;Visitantes internacionales&quot;:

1. Cree un segmento ad hoc en el Creador de métricas calculadas que se llame &quot;Visitantes alemanes&quot;, en el que la opción &quot;Países&quot; sea &quot;Alemania&quot;.

   Arrastre la dimensión Países al lienzo Definición y seleccione [!UICONTROL **Alemania**] como valor:

   ![](assets/segment-from-dimension.png)

   >[!NOTE]
   >
   >También puede hacerlo en el [Generador de segmentos](/help/components/segmentation/segmentation-workflow/seg-build.md), pero hemos simplificado el flujo de trabajo al establecer que las dimensiones estén disponibles en el Creador de métricas calculadas. La opción “ad hoc” implica que el segmento no esté visible en la lista **[!UICONTROL Segmentos]** del carril de la izquierda. Sin embargo, puede hacerlo público si pasa el ratón por el icono “i”, que se sitúa junto a ella, y hace clic en **[!UICONTROL Hacer público]**.

1. Arrastre el segmento Alemania al lienzo Definición y arrastre la métrica Visitantes únicos dentro de este:

   ![](assets/german-visitors.png)

1. Seleccione [!UICONTROL **Guardar**] para guardar la métrica calculada.

1. Cree un segmento ad hoc en el Creador de métricas calculadas llamado &quot;Visitantes internacionales&quot;, donde &quot;Países&quot; no sea igual a &quot;Alemania&quot;.

   Arrastre la dimensión Países al lienzo Definición, seleccione [!UICONTROL **Alemania**] como valor y, a continuación, seleccione [!UICONTROL **no es igual que**] como operador.

1. Arrastre la métrica Visitantes únicos dentro.

1. Seleccione [!UICONTROL **Guardar**] para guardar la métrica calculada.

1. En Analysis Workspace, arrastre la dimensión **[!UICONTROL Página]** a una tabla de forma libre y, luego, las dos métricas calculadas nuevas en paralelo en la parte superior:

   ![](assets/workspace-pages.png)


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Métricas segmentadas](https://video.tv.adobe.com/v/37935?quality=12&learn=on&captions=spa){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]


## Porcentaje del total de métricas {#percent-total}

Puede llevar el ejemplo anterior un paso más allá comparando el segmento con una población total. Para ello, cree dos métricas: “% de visitantes alemanes totales” y “% de visitantes internacionales totales”.

1. Coloque el segmento de Visitantes de Alemania (o internacionales) en el lienzo.
1. Coloque otro segmento de Visitantes de Alemania (o internacionales) a continuación. Sin embargo, en esta ocasión, haga clic en el icono de configuración (el engranaje) para seleccionar “Total” como Tipo de métrica. El formato debe ser “Porcentaje”. El operador debe ser “dividido por”. Al final, tendrá esta definición de métrica:

   ![](assets/cm_metric_total.png)

1. Aplique esta métrica a su proyecto:

   ![](assets/cm_percent_total.png)

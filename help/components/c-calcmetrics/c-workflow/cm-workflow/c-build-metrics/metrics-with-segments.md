---
description: La segmentación de una métrica individual le permite realizar comparaciones de métricas dentro del mismo informe. (Solo métricas derivadas)
seo-description: La segmentación de una métrica individual le permite realizar comparaciones de métricas dentro del mismo informe. (Solo métricas derivadas)
seo-title: Métricas segmentadas
title: Métricas segmentadas
uuid: 88 f 9829 b -76 e 4-4598-9494-084 a 91602 bc 1
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Métricas segmentadas

La segmentación de una métrica individual le permite realizar comparaciones de métricas dentro del mismo informe. (Solo métricas derivadas)

## Comparar segmentos {#section_29A6E0070F084BFDB6228FA9CE106F48}

Digamos que desea comparar distintos aspectos de los segmentos de "Visitantes de EE. UU." para aquellos de un segmento en "Visitantes internacionales". Puede crear métricas que le proporcionarán información como:

* ¿De qué forma se compara el contenido de navegación ente los dos grupos? (Otro ejemplo sería: ¿De qué forma se compara la tasa de conversión entre los dos segmentos?)
* Como un porcentaje de visitantes totales, ¿cuántos visitantes de los EE. UU. navegan por ciertas páginas en comparación con los visitantes internacionales?
* ¿Cuáles son las principales diferencias en términos de a qué contenido se accede desde estos segmentos diferentes?

Vamos a ver la primera pregunta: ¿de qué forma se compara el contenido de navegación ente los dos grupos?

1. Si no tiene ningún segmento comparable, cree un segmento interno en el creador de métricas calculadas que se llame “Visitantes alemanes”, en el que la opción “Países” sea “Alemania”. Arrastre la dimensión de países al lienzo de definición y seleccione que el valor sea Alemania:

   ![](assets/segment-from-dimension.png)

   >[!NOTE]
   >
   >You can also do this in the [Segment Builder](https://marketing.adobe.com/resources/help/en_US/analytics/segment/seg_build.html), but we have simplified the workflow by making dimensions available in the Calculated Metric Builder.

   >[!NOTE]
   >
   >"Internal" means that the segment is not visible in the **[!UICONTROL Segments]** list in the left rail. Sin embargo, puede hacerlo público si pasa el ratón por el icono “i”, que se sitúa junto a ella, y hace clic en **[!UICONTROL Hacer público]**.

1. Si no tiene ningún segmento comparable, cree un segmento que se llame “Visitantes internacionales” en el que “Países” no sea igual a “Alemania”.
1. Cree y guarde una métrica llamada “Visitantes de Alemania” arrastrando el segmento de Alemania al lienzo Definición y la métrica de Visitantes únicos dentro de este:

   ![](assets/german-visitors.png)

1. Repita el paso 3 con el segmento de Visitantes internacionales y la métrica de Visitantes únicos para crear una métrica de Visitantes internacionales.
1. En Analysis Workspace, arrastre la dimensión **[!UICONTROL Página]a una tabla de formato libre y, luego, las dos métricas calculadas nuevas en paralelo en la parte superior:**

   ![](assets/workspace-pages.png)

1. Or, in [!UICONTROL Reports &amp; Analytics], open the [!UICONTROL Pages] report and click **[!UICONTROL Show Metrics]**, then apply the new US Visitors and International Visitors segmented metrics to see how their content browsing behavior compares.

   ![](assets/pages-report.png)

## Comparar porcentajes de totales {#section_846CB89725F04388AE0352DB20189EE8}

Puede introducir otro nivel de consulta al comparar el comportamiento de exploración de visitantes en porcentajes normalizados. Para ello, cree dos métricas: “% de visitantes de Alemania totales” y “% de visitantes internacionales totales”.

1. Coloque el segmento de Visitantes de Alemania (o internacionales) en el lienzo.
1. Coloque otro segmento de Visitantes de Alemania (o internacionales) a continuación. Sin embargo, en esta ocasión, haga clic en el icono de configuración (el engranaje) para seleccionar “Total” como Tipo de métrica. El formato debe ser “Porcentaje”. El operador debe ser “dividido por”. Al final, tendrá esta definición de métrica:

   ![](assets/cm_metric_total.png)

1. Aplique esta métrica a su proyecto:

   ![](assets/cm_percent_total.png)

## Comparar diferencias en porcentajes (mediante Contenedores) {#section_13D6353259B74C09B37BA6378A501938}

Si desea ver las principales diferencias entre el comportamiento de exploración de EE. UU. e Internacional de un vistazo, puede crear otra métrica que reste los porcentajes entre sí. Para ello, puede utilizar la función de Contenedor que funciona de forma efectiva como paréntesis rodeando 2 conjuntos de métricas.

1. In the [!UICONTROL Definition] canvas, click **[!UICONTROL Add]** &gt; **[!UICONTROL Container]**:

   ![](assets/cm_add_container.png)

1. Coloque la métrica de "% de visitantes de EE. UU. totales" que ha creado anteriormente en el primer contenedor; se amplía hasta su definición completa:

   ![](assets/cm_container_us.png)

1. Cree otro contenedor a continuación y coloque la métrica "% de visitantes internacionales totales" en él.
1. Cambie el operador entre los 2 contenedores a un signo de resta (-).

   ![](assets/cm_container_intl.png)

1. Guarde la métrica (asegúrese de que le ha dado un nombre similar a "Diferencia en % entre EE. UU y internacionales").
1. Cuando se aplica a su informe, puede observar fácilmente dónde se encuentran las principales diferencias en porcentajes y puede clasificar el informe de forma correspondiente.

   ![](assets/cm_diff_percent.png)


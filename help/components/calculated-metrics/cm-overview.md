---
description: Obtenga información sobre las métricas calculadas que puede crear a partir de métricas existentes.
keywords: Métricas calculadas
title: Información general sobre las métricas calculadas
feature: Calculated Metrics
exl-id: 9bf8239f-cf74-4feb-85e5-d47805e90afb
TQID: https://experienceleague.adobe.com/3bZdi3MZ8Q5MibUfwOlO1CmumXTqlWxBH6hy35M9tUk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 317
ht-degree: 75%

---

# Información general sobre las métricas calculadas

Las métricas calculadas son métricas personalizadas que puede crear a partir de las métricas existentes.

Las métricas calculadas son personalizadas y se pueden crear a partir de métricas existentes. Las métricas calculadas ofrecen una forma flexible de crear, administrar y depurar métricas personalizadas que te permiten analizar los datos sin tener que cambiar la implementación.

Las métricas calculadas están disponibles en cada paquete [!DNL Analytics], pero el paquete de Adobe Analytics Foundation para Experience Cloud se limita a métricas calculadas básicas que incluyen [tipos de formato (decimal, tiempo, porcentaje, moneda)](/help/components/calculated-metrics/workflow/c-build-metrics/cm-build-metrics.md), [cambios de asignación (predeterminada, lineal, de participación, etc.)](/help/components/calculated-metrics/workflow/c-build-metrics/m-metric-type-alloc.md), [tipos de métrica (estándar, total)](/help/components/calculated-metrics/workflow/c-build-metrics/m-metric-type-alloc.md) y [operadores básicos](workflow/c-build-metrics/cm-build-metrics.md#operators) (sumar, restar, multiplicar y dividir).


Consulte la [Descripción del producto Adobe Analytics](https://helpx.adobe.com/es/legal/product-descriptions/adobe-analytics.html) para obtener más información.

<!--
Here is a comparison of calculated metrics and advanced calculated metrics capabilities: 

| [Format types (decimal, time, percent, currency)](/help/components/calculated-metrics/workflow/c-build-metrics/cm-build-metrics.md)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  |
| [Attribution changes (default, linear, participation, etc.)](/help/components/calculated-metrics/workflow/c-build-metrics/m-metric-type-alloc.md)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  |
| [Metric types (standard, total)](/help/components/calculated-metrics/workflow/c-build-metrics/m-metric-type-alloc.md)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  |
|  Basic operators (add, subtract, multiply, divide)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  |
| [Apply segments](/help/components/calculated-metrics/workflow/c-build-metrics/metrics-with-segments.md)  | ![StopCircle](/help/assets/icons/StopCircle.svg)  | Yes  |
| [Basic functions (count, abs value, mean, etc)](/help/components/calculated-metrics/cm-reference/cm-functions.md)  | No  | Yes  |
| [Advanced functions (regression, if/then, t-score, etc)](/help/components/calculated-metrics/cm-reference/cm-adv-functions.md)  | No  | Yes  |

-->

## Competencias {#section_A0A5C275B68A4D628950BBB0B1EE631F}

Puede

* [Crear métricas](/help/components/calculated-metrics/workflow/cm-workflow.md) en [!UICONTROL Analysis Workspace], [!UICONTROL Report Builder], [!UICONTROL Detección de anomalías] y [!UICONTROL Análisis de contribución].
* [Crear métricas segmentadas](/help/components/calculated-metrics/workflow/c-build-metrics/metrics-with-segments.md) que se derivan durante el tiempo de ejecución de un informe, sin tener que cambiar la implementación. Por ejemplo, puede crear una métrica para *Visitantes nuevos*, con un recuento de personas para las cuales esta es la primera sesión.

* [Compartir métricas](/help/components/calculated-metrics/workflow/cm-sharing.md) entre grupos de informes. Esto significa que todas las métricas de reciente creación se aplican a todos los grupos de informes en la misma empresa de inicio de sesión.

* [Incorporar funciones estadísticas](/help/components/calculated-metrics/cm-reference/cm-adv-functions.md) para ayudarle a describir mejor los datos. Por ejemplo, haga recuentos del número de elementos de un informe o agregue el número de desviaciones estándar para cada elemento.

## Limitaciones

Algunas funciones de [!DNL Analytics] no permiten el uso de métricas calculadas:

* [!UICONTROL Secuelas] en [!UICONTROL Analysis Workspace]
* [!UICONTROL Análisis de cohortes] en Analysis Workspace
* [!UICONTROL Data Warehouse]
* [!UICONTROL Segmentos]
* [!DNL Analytics] para [!DNL Target]


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Métricas calculadas](https://experienceleague.adobe.com/es/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-implementationless-metrics){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]

>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Métricas calculadas segmentadas en segmentos](https://experienceleague.adobe.com/es/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-segmented-metrics){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]

<!--

Here is a short overview of the [!UICONTROL Calculated metrics] tools: 

|Tool|Capabilities|
|--- |--- |
| [Calculated metric builder](workflow/c-build-metrics/cm-build-metrics.md)| The capabilities are: <ul><li>Create calculated and advanced calculated metrics using advancmd allocation models.</li><li>Add segments inline to metric formulas</li><li>Compare segments in the same report. For example, compare local visitors vs. international visitors.</li><li>Use statistical functions</li><li>Provide detailed metric descriptions (show what it does, where to use it, where NOT to use it)</li><li>Copy definitions into new metrics</li><li>Provide an inline metric preview</li><li>Set metric polarity, which indicates whether it's good or bad if a given custom event (metric) goes up</li><li>Tag metrics</li></ul>|
|Calculated Metric Manager|<ul><li>Share metrics with others</li<li>Approve and curate metrics</li><li>Organize (tag) your metrics so people can find them</li><li>Delete metrics</li><li>Rename metrics</li></ul>|
|Metric Selector rail|Lets you search for and add/apply metrics to the report. You can also change the  sort order (options are: alphabetical, recommended, frequently used, recently used.) In addition, you can filter on Report Suites to show only metrics created in a specific report suite.  To access this Metric Selector, click the Metrics icon  to the left of a report. |
|API for Calculated Metrics|Part of the Adobe Analytics 2.0 API set.|

-->

>[!MORELIKETHIS]
>
>[Crear métricas](/help/components/calculated-metrics/workflow/cm-workflow.md)
>[Crear métricas](/help/components/calculated-metrics/workflow/c-build-metrics/cm-build-metrics.md)
>[Usar funciones](/help/components/calculated-metrics/workflow/c-build-metrics/cm-using-functions.md)
>

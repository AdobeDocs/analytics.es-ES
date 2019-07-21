---
description: 'null'
seo-description: 'null'
seo-title: Limitaciones de espacio de trabajo, limitaciones conocidas en Analysis Workspace
title: Limitaciones conocidas en Analysis Workspace
translation-type: tm+mt
source-git-commit: 9d6b35c7c6de6fcb49fea3b662ff8bc9044b5e29

---


# Limitaciones conocidas en Analysis Workspace

Esta es una lista de limitaciones conocidas en Analysis Workspace y sus componentes relacionados:

## Tablas

* No se pueden agregar columnas de comparación de fechas cuando se utilizan intervalos de fechas o métricas como filas de una tabla.
* Crear métrica a partir de selección se desactiva cuando los segmentos se utilizan como filas de una tabla. Además, Crear métrica a partir de selección no debe aplicarse a las columnas alineadas por fecha.
* El formato condicional de las filas de desglose no puede utilizar intervalos personalizados.
* Las filas totales de tabla no se pueden medir cuando se aplica Calcular totales al sumar la configuración de valores de la fila (generalmente se utiliza con elementos de fila estáticos).
* [!UICONTROL El análisis de contribución] solo se puede ejecutar [!UICONTROL en] la granularidad _diaria_. It cannot be run against [!UICONTROL hourly], [!UICONTROL weekly], etc., data.

## Visualizaciones

* Visualizations that leverage segmentation, such as [!UICONTROL Fallout], [!UICONTROL Flow], [!UICONTROL Cohort], and [!UICONTROL Histogram], cannot accept calculated metrics as inputs.
* [!UICONTROL Flujo]: Las dimensiones de entrada/salida, por ejemplo, página [!UICONTROL de entrada], no se pueden utilizar en Flujo.
* [!UICONTROL Cohorte]: Los números no enteros no se pueden utilizar como criterios de Cohorte.

## Paneles

* Segment Comparison: The [!UICONTROL Everyone Else] segment does not get created if a segment template is used in the initial drop zone.

## Componentes &gt; Segmentos

* Certain metrics and dimensions are not segmentable, such as [!UICONTROL Occurrences], [!UICONTROL Unique Visitors], etc.
* Certain components and operators are unavailable if a segment is created from Workspace (as opposed to being created from [!UICONTROL Components &gt; Segments]). Por ejemplo, Dirección IP.

## Componentes &gt; Métricas calculadas

* Las métricas calculadas no se pueden utilizar en ciertas visualizaciones. Consulte «Visualizaciones» arriba.
* Calculated metrics cannot be used in the [!UICONTROL Attribution] panel, since calculated metrics themselves can include separate attribution models.
* Certain components and operators are unavailable if a calculated metric is created from Workspace (as opposed to being created from [!UICONTROL Components &gt; Segments]). For example, [!UICONTROL IP Address].

## Componentes &gt; Intervalos de fechas

* Custom date ranges do not support [!UICONTROL This day last year], [!UICONTROL This day last month], etc.

## Componentes &gt; Grupos de informes virtuales

* Cuando se habilita el procesamiento de intervalo de tiempo, algunos componentes no son compatibles. For a full list, see [Report Time Processing](/help/components/vrs/vrs-report-time-processing.md).

## Componentes &gt; Configuración de informes

* Some of the settings on the [!UICONTROL Report Settings] page do not apply. Analysis Workspace uses only the [!UICONTROL Language/Currency/Encoding] settings at the bottom: [!UICONTROL Thousands separator], [!UICONTROL Scheduled Report Encoding], and [!UICONTROL CSV Separator Character].

## Attribution IQ

* A subset of metrics is not supported in [!UICONTROL Attribution IQ]. For a full list, see the [Attribution IQ FAQ](/help/analyze/analysis-workspace/attribution-iq/attribution-faq.md).
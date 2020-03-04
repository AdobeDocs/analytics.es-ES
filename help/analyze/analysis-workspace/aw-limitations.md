---
description: Lista de limitaciones conocidas en Adobe Analysis Workspace y componentes relacionados
title: Limitaciones conocidas en Analysis Workspace
translation-type: tm+mt
source-git-commit: 06d2e64fc72c911828f089de5c487117251e060e

---


# Limitaciones conocidas en Analysis Workspace

Esta es una lista de limitaciones conocidas en Analysis Workspace y sus componentes relacionados:

## Tablas

* No se pueden agregar columnas de comparación de fechas cuando se utilizan intervalos de fechas o métricas como filas de una tabla.
* La creación de métricas a partir de una selección se desactiva cuando los segmentos se utilizan como filas de una tabla. Además, la creación de una métrica a partir de una selección no debe aplicarse a columnas alineadas con la fecha.
* El formato condicional de las filas de desglose no puede utilizar intervalos personalizados.
* Las filas totales de la tabla no pueden incluir tendencias cuando se calculan los totales sumando la configuración de valores de fila (generalmente se utiliza con elementos de fila estáticos).
* [!UICONTROL Contribution Analysis] puede ejecutarse con la [!UICONTROL daily] granularidad _solamente_. It cannot be run against [!UICONTROL hourly], [!UICONTROL weekly], etc., data.

## Visualizaciones

* Visualizations that leverage segmentation, such as [!UICONTROL Fallout], [!UICONTROL Flow], [!UICONTROL Cohort], and [!UICONTROL Histogram], cannot accept calculated metrics as inputs.
* [!UICONTROL Flow]:: Dimensiones de entrada y salida, por ejemplo: [!UICONTROL Entry page], no se puede usar en Flujo.
* [!UICONTROL Cohort]:: Los no enteros no se pueden usar como criterios de cohorte.

## Paneles

* Segment Comparison: The [!UICONTROL Everyone Else] segment does not get created if a segment template is used in the initial drop zone.

## Componentes > Segmentos

* Certain metrics and dimensions are not segmentable, such as [!UICONTROL Occurrences], [!UICONTROL Unique Visitors], etc.
* Certain components and operators are unavailable if a segment is created from Workspace (as opposed to being created from [!UICONTROL Components > Segments]). Por ejemplo, Dirección IP.

## Componentes > Métricas calculadas

* Las métricas calculadas no se pueden usar en determinadas visualizaciones. Consulte “Visualizaciones”.
* Las métricas calculadas no se pueden usar en el panel de [!UICONTROL Attribution], ya que las métricas calculadas pueden incluir modelos de atribución independientes.
* Certain components and operators are unavailable if a calculated metric is created from Workspace (as opposed to being created from [!UICONTROL Components > Segments]). Por ejemplo: [!UICONTROL IP Address].

## Componentes > Intervalos de fechas

* Los intervalos de fechas personalizados no son compatibles [!UICONTROL This day last year], [!UICONTROL This day last month]etc.

## Componentes > Grupos de informes virtuales

* Cuando se habilita el procesamiento del tiempo del informe, no se admiten determinados componentes. Para obtener una lista completa, consulte [Procesamiento de intervalo de tiempo](/help/components/vrs/vrs-report-time-processing.md).

## Componentes > Configuración de informes

* Some of the settings on the [!UICONTROL Report Settings] page do not apply. Analysis Workspace solo utiliza los [!UICONTROL Language/Currency/Encoding] ajustes de la parte inferior: [!UICONTROL Thousands separator], [!UICONTROL Scheduled Report Encoding], y [!UICONTROL CSV Separator Character].

## Attribution IQ

* A subset of metrics is not supported in [!UICONTROL Attribution IQ]. Para obtener una lista completa, consulte las preguntas más frecuentes sobre [Attribution IQ](c-panels/attribution/attribution-faq.md).

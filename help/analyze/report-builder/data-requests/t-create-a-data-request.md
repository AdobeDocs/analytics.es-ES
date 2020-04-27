---
description: Pasos para crear una solicitud de datos básica de Report Builder.
title: Crear una solicitud de datos
topic: Report builder
uuid: 5d0151f1-e23d-43eb-84a4-96ae06c3a564
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Crear una solicitud de datos de Report Builder

Pasos para crear una solicitud de datos básica.

1. In Excel, click **[!UICONTROL Create]**.
1. En la [!UICONTROL Request Wizard: Step 1] ventana, seleccione un grupo [de](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md)informes.
1. (Opcional) Seleccione un segmento que aplicar a la solicitud. Cuando haya seleccionado uno o más segmentos, se moverán al principio de la lista.

   Report Builder utiliza los segmentos de la misma forma que lo hace Adobe Analytics. Consulte la [Guía de segmentación de Analytics](https://marketing.adobe.com/resources/help/es_ES/analytics/segment/). 1. (Opcional) Seleccione una [lista de publicaciones](/help/analyze/report-builder/data-requests/allow-publishing-list-overrides.md) para su distribución.
1. Seleccione un [tipo de informe](/help/analyze/report-builder/data-requests/c-report-types/select-report-types.md).
1. Especifique un [intervalo de fechas](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md) y una [granularidad](/help/analyze/report-builder/data-requests/configuring-report-dates/granularity.md) para el informe.
1. Haga clic en **[!UICONTROL Next]**.
1. En la ventana [Diseño del asistente para solicitudes: Paso 2](/help/analyze/report-builder/layout/layout.md), especifique un diseño:

   | Elemento | Descripción |
   |---|---|
   | Diseño de tabla dinámica | Proporciona una fila, una columna y una cuadrícula de métrica para el diseño, similar a las tablas estándar de Excel. Utilizando este diseño, se pueden añadir solicitudes de desglose a una solicitud original. |
   | Diseño personalizado | Provides most of the functionality of the [!UICONTROL Pivot Layout] but lets you choose where each item in the grid should be located in the spreadsheet. Este diseño proporciona la flexibilidad disponible en versiones anteriores. |

1. On the [!UICONTROL Metrics] tab, double-click (or drag) metrics in the tree to add them to the [!UICONTROL Metrics] grid.
1. On the [!UICONTROL Dimensions] tab, double-click (or drag) dimensions to the [!UICONTROL Row Labels] grid.

   Las [dimensiones](https://marketing.adobe.com/resources/help/es_ES/reference/dimensions.html) disponibles en el Paso 2 dependen de qué informe base se ha seleccionado en el Paso 1, así como de la configuración de su grupo de informes. The dimensions are items that correlate, sub-relate, or are a classification of the original report type metric you selected on the [!UICONTROL Request Wizard: Step 1] window. La adición de varias dimensiones en el Paso 2 es el modo en que se crea un desglose en la solicitud de datos.

   Consulte [Agregar métricas y dimensiones](/help/analyze/report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md) para obtener más información.

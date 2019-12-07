---
description: Pasos para crear una solicitud de datos básica del Creador de informes.
title: Creación de una solicitud de datos
topic: Report builder
uuid: 5d0151f1-e23d-43eb-84a4-96ae06c3a564
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Crear una solicitud de datos del Creador de informes

Pasos para crear una solicitud de datos básica.

1. In Excel, click **[!UICONTROL Create]**.
1. In the [!UICONTROL Request Wizard: Step 1] window, select a [report suite](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md).
1. (Opcional) Seleccione un segmento que aplicar a la solicitud. Cuando haya seleccionado uno o más segmentos, se moverán al principio de la lista.

   El Creador de informes utiliza los segmentos de la misma forma que lo hace Adobe Analytics. Consulte la [Guía de segmentación de Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/segment/). 1. (Opcional) Seleccione una lista [de](/help/analyze/report-builder/data-requests/allow-publishing-list-overrides.md) publicaciones para su distribución.
1. Select a [report type](/help/analyze/report-builder/data-requests/c-report-types/select-report-types.md).
1. Especifique un intervalo [de](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md) fechas y una [granularidad](/help/analyze/report-builder/data-requests/configuring-report-dates/granularity.md)de informe.
1. Haga clic en **[!UICONTROL Siguiente]**.
1. In the [Layout - Request Wizard Step 2](/help/analyze/report-builder/layout/layout.md) window, specify a layout:

   | Elemento | Descripción |
   |---|---|
   | Diseño de tabla dinámica | Proporciona una fila, una columna y una cuadrícula de métrica para el diseño, similar a las tablas estándar de Excel. Utilizando este diseño, se pueden añadir solicitudes de desglose a una solicitud original. |
   | Diseño personalizado | Proporciona la mayor parte de la funcionalidad del [!UICONTROL diseño de la tabla dinámica], pero permite seleccionar el sitio donde se debe situar cada elemento de la cuadrícula en la hoja de cálculo. Este diseño proporciona la flexibilidad disponible en versiones anteriores.  |

1. En la ficha [!UICONTROL Métrica], haga doble clic (o arrastre) la métrica del árbol para añadirla a la cuadrícula [!UICONTROL Métrica.]
1. En la ficha [!UICONTROL Dimensiones], haga doble clic (o arrastre) en las dimensiones a la cuadrícula [!UICONTROL Rótulos de fila.]

   Las [dimensiones](https://marketing.adobe.com/resources/help/en_US/reference/dimensions.html) disponibles en el Paso 2 dependen de qué informe base se ha seleccionado en el Paso 1, así como de la configuración de su grupo de informes. Las dimensiones son elementos que se correlacionan, subrelacionan o son una clasificación de la métrica del tipo de informe original que se seleccionó en la ventana [!UICONTROL Asistente para solicitudes: Paso 1]. La adición de varias dimensiones en el Paso 2 es el modo en que se crea un desglose en la solicitud de datos.

   Consulte [Agregar métricas y dimensiones](/help/analyze/report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md) para obtener más información.

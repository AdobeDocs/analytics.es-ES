---
description: Pasos para crear una solicitud de datos básica de Report Builder.
title: Crear una solicitud de datos
uuid: 5d0151f1-e23d-43eb-84a4-96ae06c3a564
feature: Report Builder
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 95%

---


# Crear una solicitud de datos de Report Builder

Pasos para crear una solicitud de datos básica.

1. En Excel, haga clic en **[!UICONTROL Crear]**.
1. En la ventana [!UICONTROL Asistente para solicitudes: Paso 1], seleccione un [Grupo de informes](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md).
1. (Opcional) Seleccione un segmento que aplicar a la solicitud. Cuando haya seleccionado uno o más segmentos, se moverán al principio de la lista.

   Report Builder utiliza los segmentos de la misma forma que lo hace Adobe Analytics. Consulte la [Guía de segmentación de Analytics](https://docs.adobe.com/content/help/es-ES/analytics/components/segmentation/seg-home.html). 1. (Opcional) Seleccione una [lista de publicaciones](/help/analyze/report-builder/data-requests/allow-publishing-list-overrides.md) para su distribución.
1. Seleccione un [tipo de informe](/help/analyze/report-builder/data-requests/c-report-types/select-report-types.md).
1. Especifique un [intervalo de fechas](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md) y una [granularidad](/help/analyze/report-builder/data-requests/configuring-report-dates/granularity.md) para el informe.
1. Haga clic en **[!UICONTROL Siguiente]**.
1. En la ventana [Diseño del asistente para solicitudes: Paso 2](/help/analyze/report-builder/layout/layout.md), especifique un diseño:

   | Elemento | Descripción |
   |---|---|
   | Diseño de tabla dinámica | Proporciona una fila, una columna y una cuadrícula de métrica para el diseño, similar a las tablas estándar de Excel. Utilizando este diseño, se pueden añadir solicitudes de desglose a una solicitud original. |
   | Diseño personalizado | Proporciona la mayor parte de la funcionalidad del [!UICONTROL diseño de la tabla dinámica], pero permite seleccionar el sitio donde se debe situar cada elemento de la cuadrícula en la hoja de cálculo. Este diseño proporciona la flexibilidad disponible en versiones anteriores. |

1. En la ficha [!UICONTROL Métrica], haga doble clic (o arrastre) la métrica del árbol para añadirla a la cuadrícula [!UICONTROL Métrica].
1. En la ficha [!UICONTROL Dimensiones], haga doble clic (o arrastre) en las dimensiones a la cuadrícula [!UICONTROL Rótulos de fila].

   Las [dimensiones](https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/layout/filter-dimenson/filter-dimensions.html) disponibles en el Paso 2 dependen de qué informe base se ha seleccionado en el Paso 1, así como de la configuración de su grupo de informes. Las dimensiones son elementos que se correlacionan, subrelacionan o son una clasificación de la métrica del tipo de informe original que se seleccionó en la ventana [!UICONTROL Asistente para solicitudes: Paso 1]. La adición de varias dimensiones en el Paso 2 es el modo en que se crea un desglose en la solicitud de datos.

   Consulte [Agregar métricas y dimensiones](/help/analyze/report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md) para obtener más información.

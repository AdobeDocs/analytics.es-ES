---
description: Pasos para crear una solicitud de datos básica del Creador de informes.
seo-description: Pasos para crear una solicitud de datos básica del Creador de informes.
seo-title: Crear una solicitud de datos del Creador de informes
solution: Analytics
title: Creación de una solicitud de datos
topic: Creador de informes
uuid: 5 d 0151 f 1-e 23 d -43 eb -84 a 4-96 ae 06 c 3 a 564
translation-type: tm+mt
source-git-commit: 65b3c25288060b1b6d0b9590a8fdca4087f416a0

---


# Crear una solicitud de datos del Creador de informes

Pasos para crear una solicitud de datos básica.

1. In Excel, click **[!UICONTROL Create]**.
1. In the [!UICONTROL Request Wizard: Step 1] window, select a [report suite](../../../analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md#task_59444416F6F042D1998217AE91580913).
1. (Opcional) Seleccione un segmento que aplicar a la solicitud. Cuando haya seleccionado uno o más segmentos, se moverán al principio de la lista.

   El Creador de informes utiliza los segmentos de la misma forma que lo hace Adobe Analytics. Consulte la [Guía de segmentación de Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/segment/). 1. (Optional) Select a [publishing list](../../../analyze/report-builder/data-requests/allow-publishing-list-overrides.md#concept_BCB19A20DC4B4B8D984F9670EE018D8C) to use for distribution.
1. Select a [report type](../../../analyze/report-builder/data-requests/c-report-types/select-report-types.md#concept_C711B27E6FB64C18AC564EE142FC7EFC).
1. Specify a [date range](../../../analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md) and report [granularity](../../../analyze/report-builder/data-requests/configuring-report-dates/granularity.md#concept_A13CBA2962E24FF882456135431B7ADB).
1. Click **[!UICONTROL Next]**.
1. In the [Layout - Request Wizard Step 2](../../../analyze/report-builder/layout/layout.md#concept_D66E1C2217E24E1F837AC064C61919DB) window, specify a layout:

   | Elemento | Descripción |
   |---|---|
   | Diseño de tabla dinámica | Proporciona una fila, una columna y una cuadrícula de métrica para el diseño, similar a las tablas estándar de Excel. Utilizando este diseño, se pueden añadir solicitudes de desglose a una solicitud original. |
   | Diseño personalizado | Proporciona la mayor parte de la funcionalidad del [!UICONTROL diseño de la tabla dinámica], pero permite seleccionar el sitio donde se debe situar cada elemento de la cuadrícula en la hoja de cálculo. Este diseño proporciona la flexibilidad disponible en versiones anteriores.  |

1. En la ficha [!UICONTROL Métrica], haga doble clic (o arrastre) la métrica del árbol para añadirla a la cuadrícula [!UICONTROL Métrica.]
1. En la ficha [!UICONTROL Dimensiones], haga doble clic (o arrastre) en las dimensiones a la cuadrícula [!UICONTROL Rótulos de fila.]

   Las [dimensiones](https://marketing.adobe.com/resources/help/en_US/reference/index.html?f=dimensions) disponibles en el Paso 2 dependen de qué informe base se ha seleccionado en el Paso 1, así como de la configuración de su grupo de informes. Las dimensiones son elementos que se correlacionan, subrelacionan o son una clasificación de la métrica del tipo de informe original que se seleccionó en la ventana [!UICONTROL Asistente para solicitudes: Paso 1]. La adición de varias dimensiones en el Paso 2 es el modo en que se crea un desglose en la solicitud de datos.

   Consulte [Agregar métricas y dimensiones](../../../analyze/report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md#task_E3F520C020F64C5A96DC5C96FEF71FC4) para obtener más información.
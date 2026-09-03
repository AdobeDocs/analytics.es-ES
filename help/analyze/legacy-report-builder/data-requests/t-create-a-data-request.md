---
description: Pasos para crear una solicitud de datos básica de Report Builder.
title: Crear una solicitud de datos
feature: Report Builder
role: User, Admin
exl-id: 21d552a0-7a58-4217-ba8a-7c87eb4757f6
TQID: https://experienceleague.adobe.com/w-oiIfs1qFMoQbaN8YrNIn1TRNHeN97lQOlkLeXdLb0
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 284
ht-degree: 53%

---

# Crear una solicitud de datos de Report Builder

{{legacy-arb}}

Pasos para crear una solicitud de datos básica.

1. En Excel, haga clic en **[!UICONTROL Crear]**.
1. En la ventana [!UICONTROL Asistente para solicitudes: Paso 1], seleccione un [Grupo de informes](/help/analyze/legacy-report-builder/data-requests/selecting-report-suites/t-select-report-suites.md).
1. (Opcional) Seleccione un segmento que aplicar a la solicitud. Cuando haya seleccionado uno o más segmentos, se moverán al principio de la lista.

   Report Builder utiliza los segmentos de la misma forma que lo hace Adobe Analytics. Consulte la [guía de segmentación de Analytics](/help/components/segmentation/seg-home.md).
1. Seleccione un [tipo de informe](/help/analyze/legacy-report-builder/data-requests/c-report-types/select-report-types.md).
1. Especifique un [intervalo de fechas](/help/analyze/legacy-report-builder/data-requests/configuring-report-dates/custom-calendar.md) y una [granularidad](/help/analyze/legacy-report-builder/data-requests/configuring-report-dates/granularity.md) para el informe.
1. Haga clic en **[!UICONTROL Siguiente]**.
1. En la ventana [Diseño del asistente para solicitudes: Paso 2](/help/analyze/legacy-report-builder/layout/layout.md), especifique un diseño:

   | Elemento | Descripción |
   |---|---|
   | Diseño dinámico | Proporciona una cuadrícula de fila, columna y métrica para el diseño, similar a las tablas estándar de Excel. Con este diseño, puede añadir solicitudes de desglose dentro de una solicitud original. |
   | Diseño personalizado | Proporciona la mayor parte de la funcionalidad del [!UICONTROL diseño de tabla dinámica], pero le permite elegir dónde debe ubicarse cada elemento de la cuadrícula en la hoja de cálculo. Este diseño proporciona la flexibilidad disponible en versiones anteriores. |

1. En la ficha [!UICONTROL Métrica], haga doble clic (o arrastre) la métrica del árbol para añadirla a la cuadrícula [!UICONTROL Métrica].
1. En la ficha [!UICONTROL Dimensiones], haga doble clic (o arrastre) en las dimensiones a la cuadrícula [!UICONTROL Rótulos de fila].

   Las [dimensiones](/help/analyze/report-builder/filter-dimensions.md) disponibles en el paso 2 dependen del informe base seleccionado en el paso 1 y de la configuración del grupo de informes. Las dimensiones son elementos que se correlacionan, subrelacionan o son una clasificación de la métrica original del tipo de informe seleccionada en la ventana [!UICONTROL Asistente para solicitudes: Paso 1]. Añadir más de una dimensión en el paso 2 es la forma de crear un desglose en la solicitud de datos.

   Consulte [Agregar métricas y dimensiones](/help/analyze/legacy-report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md) para obtener más información.

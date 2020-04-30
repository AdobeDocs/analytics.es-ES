---
description: Instrucciones sobre cómo configurar eventos de éxito.
title: Configurar eventos de éxito
topic: Admin tools
uuid: ca3d3f46-5fad-4481-aef6-04cad6bc6e2d
translation-type: tm+mt
source-git-commit: 327fdfd6a6d6bfe1c7bae9825fc8812b5ac7d095

---


# Configurar eventos de éxito

Instrucciones sobre cómo configurar eventos de éxito.

1. Haga clic **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. Selección de un grupo de informes.
1. Haga clic **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL Success Events]**.

   ![Resultado](assets/success_event_page.png)

1. In the **[!UICONTROL Name]** column, select the checkbox next each item to enable editing, then specify the desired name.
1. In the **[!UICONTROL Type]** column, select the checkbox next each item to enable the drop-down list, then select the desired type.

   >[!NOTE]
   >
   >Antes de cambiar un tipo de evento, consulte [Cambiar tipo de evento](/help/admin/admin/c-success-events/event-type.md).

   Consulte [Página Eventos de éxito: descripciones](/help/admin/admin/c-success-events/success-event.md) para obtener más información sobre estos elementos.

1. In the **[!UICONTROL Polarity]** column, specify whether an upward trend for this metric is good or bad.
1. In the **[!UICONTROL Visibility]** column, you can hide standard (built-in) metrics, custom events, and built-in events in the Menu, Metric Selectors, Calculated Metrics Builder, and the Segment Builder.

   Esta configuración no afecta a la recopilación de datos de esa métrica o evento. Solo afecta a su visibilidad en la interfaz de usuario. [Más...](/help/admin/admin/metric-visibility.md)
1. Proporcione una descripción.
1. Compruebe si desea registrar siempre el evento.
1. Habilite o deshabilite las [métricas de participación](/help/components/c-variables/c-metrics/metrics-participation.md).

   >[!NOTE]
   >
   >Puede habilitar la participación de hasta un máximo de 100 eventos personalizados. Una vez superada esa cifra, puede crear métricas de participación en el creador [Métricas calculadas](https://docs.adobe.com/content/help/en/analytics/components/calculated-metrics/calcmetric-workflow/participation-metric.html).

1. Haga clic en **[!UICONTROL Save]**.


---
description: Instrucciones sobre cómo configurar eventos de éxito.
title: Configurar eventos de éxito
feature: Event
role: Admin
exl-id: 0e9a6d8f-2ce7-4551-885d-bd77ff131da0
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 100%

---

# Configurar eventos de éxito

Para configurar eventos de éxito:

1. Haga clic en **[!UICONTROL Analytics]** > **[!UICONTROL Administración]** > **[!UICONTROL Grupos de informes]**.
1. Selección de un grupo de informes.
1. Haga clic en **[!UICONTROL Editar configuración]** > **[!UICONTROL Conversión]** > **[!UICONTROL Eventos de éxito]**.

   ![Resultado](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/assets/success_event_page.png)

1. En la columna **[!UICONTROL Nombre]**, active la casilla que hay junto a cada elemento para activar la edición y, a continuación, especifique el nombre que desee.
1. En la columna **[!UICONTROL Tipo]**, active la casilla que hay junto a cada elemento para activar la lista desplegable y, a continuación, seleccione el tipo que desee.

   >[!NOTE]
   >
   >Antes de cambiar un tipo de evento, consulte [Cambiar tipo de evento](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/event-type.md).

   Consulte [Página Eventos de éxito: descripciones](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) para obtener más información sobre estos elementos.

1. En la columna **[!UICONTROL Polaridad]**, especifique si una tendencia al alza para esta métrica es positiva o negativa.
1. En la columna **[!UICONTROL Visibilidad]**, puede ocultar las métricas (integradas), los eventos personalizados y los eventos incorporados en el menú, los selectores de métricas, el Creador de métricas calculadas y el Generador de segmentos.

   Esta configuración no afecta a la recopilación de datos de esa métrica o evento. Solo afecta a su visibilidad en la interfaz de usuario, como se indica a continuación:


   | Configuración | Visible en | No visible en |
   |---------|----------|---------|
   | [!UICONTROL **Visible en todas partes**] | <ul><li>Reports &amp; Analytics (menú y selector de métricas)</li><li>Analysis Workspace</li><li>Generador de segmentos</li><li>Creador de métricas calculadas</li></ul> | N/A |
   | [!UICONTROL **Generadores**] | <ul><li>Generador de segmentos</li><li>Creador de métricas calculadas</li></ul> | <ul><li>Reports &amp; Analytics (menú y selector de métricas)</li><li>Analysis Workspace</li></ul> |
   | [!UICONTROL **Oculto en todas partes**] | N/A | <ul><li>Reports &amp; Analytics (menú y selector de métricas)</li><li>Analysis Workspace</li><li>Generador de segmentos</li><li>Creador de métricas calculadas</li></ul> |

1. Proporcione una descripción.
1. Compruebe si desea registrar siempre el evento.
1. Habilite o deshabilite las métricas de participación.

   >[!NOTE]
   >
   >Puede habilitar la participación de hasta un máximo de 100 eventos personalizados. Una vez superada esa cifra, puede crear métricas de participación en el creador [Métricas calculadas](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/participation-metric.md).

1. Haga clic en **[!UICONTROL Guardar]**.

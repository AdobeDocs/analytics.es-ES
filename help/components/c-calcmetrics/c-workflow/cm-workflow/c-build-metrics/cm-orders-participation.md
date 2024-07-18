---
description: Explica cómo crear una métrica que muestre los canales de marketing asistidos al realizar pedidos. Esto puede adaptarse a cualquier otro evento de éxito o dimensión que resulte de interés.
title: Métrica Asistencia para pedidos
feature: Calculated Metrics
exl-id: 33cb441d-d003-408d-ba67-1bcdd0e821ff
source-git-commit: 7722a2f01ff77dfec8ce110fd04fe977f6c627c6
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 59%

---

# Crear una métrica de &quot;Asistencias de pedidos&quot;

La siguiente información explica cómo crear una métrica que muestre qué canales de marketing ayudan a dirigir las órdenes. Esto puede adaptarse a cualquier otro evento de éxito o dimensión que resulte de interés.

1. Comience a crear una métrica calculada, tal como se describe en [Generar métricas](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md).

1. En el Creador de métricas calculadas, asigne a la métrica el nombre &quot;Pedidos asistidos&quot; o algo similar.

1. En el lienzo Definición, arrastre una métrica de Pedidos. A continuación, para ajustar el modelo de atribución mediante el engranaje de configuración, active la casilla **[!UICONTROL Usar modelos de atribución no predeterminados]**.

   ![](assets/attr-model.png)

1. Seleccione **[!UICONTROL Personalizado]** como el modelo de atribución. Cambie las ponderaciones a 0 (inicial), 100 (reproductor) y 0 (más próximo).

   ![](assets/custom-attr-model.png)

1. Seleccione [!UICONTROL **Aplicar**] > [!UICONTROL **Guardar**].

1. En Analysis Workspace, cree una tabla de forma libre con la dimensión Canal de marketing, Pedidos y la nueva métrica Pedidos asistidos.

   ![](assets/mktg-channel-assists.png)

   Esta es una forma sencilla de indicar los canales de marketing asistidos al realizar pedidos. Como alternativa, desde una tabla de forma libre, puede hacer clic con el botón derecho en cualquier métrica y ajustar el modelo de atribución directamente desde la tabla.

1. (Opcional) Comparta la métrica con otros usuarios de su organización, tal como se describe en [Compartir métricas calculadas](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-sharing.md).

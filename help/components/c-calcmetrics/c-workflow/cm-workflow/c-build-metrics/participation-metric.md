---
description: Gracias al Creador de métricas calculadas, todo el mundo puede crear una métrica de participación.
title: Métrica de participación
feature: Calculated Metrics
exl-id: bef185d6-72c0-4068-80f8-57261369573f
source-git-commit: 4bf8397ee979614539baf21b36363eb03357567a
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 37%

---

# Generar una métrica de “participación”

La siguiente información explica cómo crear una métrica que muestre qué páginas contribuyeron a las visitas que contenían un pedido (o participaron en ellas).

Este tipo de información podría ser útil para cualquier propietario de contenido.

>[!NOTE]
>
>Puede habilitar métricas de participación en las Herramientas de administración, pero solo para los eventos personalizados 1-100.

1. Comience a crear una métrica calculada, tal como se describe en [Generar métricas](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md).

1. En el Creador de métricas calculadas, asigne a la métrica el nombre &quot;Participación&quot;.

1. Arrastre el evento de éxito “Pedidos” al lienzo Definición.

1. Cambie el [modelo de atribución](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) de ese evento a **[!UICONTROL Participación]** en el icono de engranajes de **[!UICONTROL Configuración]**. Seleccione **[!UICONTROL Visita]** retrospectiva. La definición debería tener un aspecto parecido al siguiente:

   ![](assets/participation.png)

1. Seleccione [!UICONTROL **Guardar**] para guardar la métrica.

1. Utilice la métrica calculada en un informe **[!UICONTROL Páginas]**.

   ![](assets/participation-pages.png)

1. (Opcional) Comparta la métrica con otros usuarios de su organización, tal como se describe en [Compartir métricas calculadas](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-sharing.md).

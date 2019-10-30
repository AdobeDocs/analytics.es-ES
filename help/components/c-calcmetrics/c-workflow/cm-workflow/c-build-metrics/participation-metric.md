---
description: Gracias al Creador de métricas calculadas, todo el mundo puede crear una métrica de participación.
seo-description: Gracias al Creador de métricas calculadas, todo el mundo puede crear una métrica de participación.
seo-title: Métrica de participación
title: Métrica de participación
uuid: 7cb191be-bc4e-46ef-8a20-ccba5355e253
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Métrica de participación

Este es un caso de uso sencillo: Usted es el propietario de un contenido y desea ver qué páginas contribuyeron (es decir, participaron en) las visitas que contenían un pedido. A continuación se muestra cómo:

> [!NOTE] Solía hacerlo a través de las Herramientas de administración. Aún puede habilitar métricas de participación en Herramientas de administración, pero solo para los eventos personalizados 1-100.

Veamos un caso de uso sencillo. Usted es el propietario de cierto contenido y quiere averiguar las páginas que han contribuido a obtener visitas que contenían un registro por correo electrónico. A continuación se muestra cómo:

1. Cree una nueva métrica en el Creador de métricas calculadas.
1. Arrastre los "Pedidos" del evento de éxito al lienzo Definición.
1. Cambie el modelo [de](../../../../../components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#concept_B7A1FCFEFA9D4C4883208ACE8C9C8E5E) atribución de ese evento a **[!UICONTROL Participación]** en el engranaje **[!UICONTROL Configuración]** . Seleccione **[!UICONTROL Visita]** retrospectiva. La definición debería tener un aspecto parecido al siguiente:

   ![](assets/participation.png)

1. Guarde la métrica.
1. Utilice la métrica calculada en un informe **[!UICONTROL Páginas]** .

   ![](assets/participation-pages.png)

1. (Opcional) Comparta la métrica con otros usuarios de su organización.


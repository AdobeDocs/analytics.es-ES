---
description: Con el Creador de métricas calculadas, cualquier persona puede crear una métrica de participación.
title: Métrica de participación
uuid: 7cb191be-bc4e-46ef-8a20-ccba5355e253
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Métrica de participación

Veamos un caso de uso sencillo. Usted es el propietario de cierto contenido y quiere averiguar las páginas que han contribuido (es decir, participado) a obtener visitas que contenían un registro por correo electrónico. A continuación se muestra cómo:

>[!NOTE] Anteriormente, este procedimiento se realizaba mediante Herramientas de administración. Aún puede habilitar las métricas de participación en las Herramientas de administración, pero solo para los eventos personalizados 1 a 100.

Veamos un caso de uso sencillo. Usted es el propietario de cierto contenido y quiere averiguar las páginas que han contribuido a obtener visitas que contenían un registro por correo electrónico. A continuación se muestra cómo:

1. Cree una nueva métrica en el Creador de métricas calculadas.
1. Arrastre el evento de éxito “Pedidos” al lienzo Definición.
1. Change the [attribution model](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) of that event to **[!UICONTROL Participation]** under the **[!UICONTROL Settings]** gear. Seleccione **[!UICONTROL Visit]** retrospectiva. La definición debería ser similar a esta:

   ![](assets/participation.png)

1. Guarde la métrica.
1. Use the calculated metric in a **[!UICONTROL Pages]** report.

   ![](assets/participation-pages.png)

1. (Opcional) Comparta la métrica con otros usuarios de su organización.


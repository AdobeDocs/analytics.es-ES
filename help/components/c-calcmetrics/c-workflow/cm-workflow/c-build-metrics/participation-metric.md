---
description: Gracias al Creador de métricas calculadas, todo el mundo puede crear una métrica de participación.
title: Métrica de participación
uuid: 7cb191be-bc4e-46ef-8a20-ccba5355e253
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Métrica de participación

Veamos un caso de uso sencillo. Usted es el propietario de cierto contenido y quiere averiguar las páginas que han contribuido (es decir, participado) a obtener visitas que contenían un registro por correo electrónico. A continuación se muestra cómo:

> [!NOTE] Anteriormente, este procedimiento se realizaba mediante Herramientas de administración. Aún puede habilitar métricas de participación en Herramientas de administración, pero solo para los eventos personalizados 1-100.

Veamos un caso de uso sencillo. Usted es el propietario de cierto contenido y quiere averiguar las páginas que han contribuido a obtener visitas que contenían un registro por correo electrónico. A continuación se muestra cómo:

1. Cree una nueva métrica en el Creador de métricas calculadas.
1. Arrastre el evento de éxito “Pedidos” al lienzo Definición.
1. Cambie el [modelo de atribución](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) de ese evento a **[!UICONTROL Participación]** en el icono de engranajes de **[!UICONTROL Configuración]**. Seleccione **[!UICONTROL Visita]** retrospectiva. La definición debería tener un aspecto parecido al siguiente:

   ![](assets/participation.png)

1. Guarde la métrica.
1. Utilice la métrica calculada en un informe **[!UICONTROL Páginas]**.

   ![](assets/participation-pages.png)

1. (Opcional) Comparta la métrica con otros usuarios de su organización.


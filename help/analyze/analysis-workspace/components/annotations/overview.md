---
title: Descripción general de anotaciones
description: Cómo utilizar anotaciones en Workspace.
role: User, Admin
solution: Analytics
exl-id: 722d7636-f619-479a-97f1-3da23e8f7f83
source-git-commit: 38170806d0fbf6ae373ae089872f8d25306f416e
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 2%

---

# Descripción general de anotaciones

>[!NOTE]
>
>Actualmente, esta función está en prueba limitada.

Las anotaciones le permiten comunicar de forma eficaz los matices y perspectivas de datos contextuales a su organización. Permiten enlazar eventos de calendario con dimensiones/métricas específicas. Puede anotar una fecha o un intervalo de fechas con problemas de datos conocidos, días festivos, lanzamientos de campañas, etc. A continuación, puede mostrar gráficamente los eventos y ver si las campañas u otros eventos han afectado al tráfico del sitio, los ingresos o cualquier otra métrica.

Por ejemplo, supongamos que comparte proyectos con su organización. Si tuvo un pico importante en el tráfico debido a un evento de venta, podría crear una anotación &quot;Fecha de inicio de la campaña&quot; y ampliarla para todo el grupo de informes. Cuando los usuarios vieran cualquier conjunto de datos que incluyera esa fecha, verían la anotación dentro de sus proyectos, junto con sus datos.

![](assets/multi-day.png)

Recuerde:

* Las anotaciones se pueden asociar a una sola fecha o a un intervalo de fechas.

* Pueden aplicarse a todo el conjunto de datos o a métricas, dimensiones o segmentos especificados.

* Pueden aplicarse al proyecto en el que se crearon (predeterminado) o a todos los proyectos.

* Pueden aplicarse al grupo de informes en el que se crearon (predeterminado) o a todos los grupos de informes.

## Permisos

De forma predeterminada, solo los administradores pueden crear anotaciones. Los usuarios tienen derechos para ver anotaciones como lo tienen con otros componentes de Analytics (como segmentos, métricas calculadas, etc.).

Sin embargo, los administradores pueden especificar [!UICONTROL Creación de anotaciones] permiso (Herramientas de Analytics) para los usuarios a través del [Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/analytics-tools.html?lang=en).

## Activar o desactivar anotaciones

Las anotaciones se pueden activar o desactivar en varios niveles:

* En el nivel de visualización: [!UICONTROL Visualización] configuración > [!UICONTROL Mostrar anotaciones]

* A nivel de proyecto: [!UICONTROL Información y configuración del proyecto] > [!UICONTROL Mostrar anotaciones]

* A nivel de usuario: [!UICONTROL Componentes] > [!UICONTROL Preferencias de usuario] > [!UICONTROL Datos] > [!UICONTROL Mostrar anotaciones]

![](assets/show-ann.png)

![](assets/show-ann2.png)

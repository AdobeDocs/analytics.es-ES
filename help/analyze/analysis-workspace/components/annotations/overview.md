---
title: Descripción general de anotaciones
description: Aprenda a utilizar las anotaciones en Analysis Workspace.
role: User, Admin
solution: Analytics
feature: Annotations
exl-id: 722d7636-f619-479a-97f1-3da23e8f7f83
TQID: https://experienceleague.adobe.com/kVm6VfN3c-u3V2GHMz59QuB2uGi4DEozs1i-h4pJZOg
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 320
ht-degree: 82%

---

# Descripción general de anotaciones

Las anotaciones le permiten comunicar de forma eficaz los matices y perspectivas de datos contextuales a su organización. Las anotaciones le permiten enlazar los eventos de calendario con dimensiones y métricas específicas. Puede anotar una fecha o un intervalo de fechas con problemas de datos conocidos, días festivos, lanzamientos de campañas, etc. A continuación, puede mostrar gráficamente los eventos y ver si las campañas u otros eventos han afectado al tráfico del sitio, el uso de la aplicación móvil, los ingresos o cualquier otra métrica.

Por ejemplo, supongamos que comparte proyectos con su organización. Si hubiera experimentado una disminución notable en el número de visitantes únicos, podría crear una anotación **Disminución de visitantes** y aplicarla a todo el grupo de informes. Cuando los usuarios ven cualquier grupo de informes que incluya esa fecha, ven la anotación dentro de sus proyectos, junto con sus datos.

![Gráfico de líneas con anotación resaltada.](assets/annotation-example.png)

Las anotaciones se pueden aplicar a:

* Una sola fecha o un intervalo de fechas.

* Todo el conjunto de datos o métricas, dimensiones o segmentos específicos.

* Proyecto en el que se crean las anotaciones (predeterminado) para todos los proyectos.

* El grupo de informes en el que se crean las anotaciones (predeterminado) o todos los grupos de informes.

Consulte [Crear anotaciones](create-annotations.md) para ver las distintas opciones disponibles para crear anotaciones. A continuación, puede generar, modificar y guardar anotaciones en [Generador de anotaciones](create-annotations.md#annotation-builder).

Utilice [Administrador de anotaciones](manage-annotations.md) para administrar anotaciones.

## Activación o desactivación de anotaciones

Las anotaciones se pueden activar o desactivar en varios niveles:

| Nivel | Cómo... |
|---|---|
| **Visualización** | Habilitar o deshabilitar ![Configuración](/help/assets/icons/Setting.svg) > **[!UICONTROL Configuración]** > **[!UICONTROL Mostrar anotaciones]**.<br/>![Habilitar anotaciones deshabilitadas para una visualización](assets/annotations-visualization.png) |
| **Proyecto** | En el menú de un proyecto de Workspace, seleccione **[!UICONTROL Proyecto]** > **[!UICONTROL Información y configuración del proyecto]** y habilite o deshabilite **[!UICONTROL Mostrar anotaciones]**.<br/>![Habilitar anotaciones deshabilitadas para un proyecto](assets/annotations-project.png) |
| **Usuario** | En la pestaña **[!UICONTROL Componentes]**, seleccione **[!UICONTROL Preferencias]** o, en el menú de un proyecto de Workspace, seleccione **[!UICONTROL Proyecto]** > **[!UICONTROL Preferencias de usuario]**. <br/>En **[!UICONTROL Preferencias]**, seleccione **[!UICONTROL Proyectos y análisis]**. En la barra de pestaña de la izquierda, seleccione **[!UICONTROL Datos]**. En la parte inferior, habilite o deshabilite **[!UICONTROL Mostrar anotaciones]** debajo del encabezado de **[!UICONTROL Tabla de forma libre]**.<br/>![Habilitar anotaciones de deshabilitación para un usuario](assets/annotations-user.png) |

<!--
# Annotations overview

Annotations in Workspace enable you to effectively communicate contextual data nuances and insights to your organization. They let you tie calendar events to specific dimensions/metrics. You can annotate a date or date range with known data issues, public holidays, campaign launches, etc. You can then graphically display events and see whether campaigns or other events have affected your site traffic, revenue, or any other metric.

For example, let's say you are sharing projects with your organization. If you had a major spike in traffic due to a marketing campaign, you could create a "Campaign launch date" annotation and scope it for your whole report suite. When your users view any data sets that included that date, they see the annotation within their projects, alongside their data.

![Annotation example](assets/annotation-example.png)

Keep this in mind:

* Annotations can be tied to a single date or to a date range.

* They can apply to your entire data set or to specified metrics, dimensions, or segments.

* They can apply to the project in which they were created (default) or to all projects.

* They can apply to the report suite in which they were created (default) or to all report suites.

## Permissions {#permissions}

By default, only Admins can create annotations. Users have rights to view annotations like they do with other other Analytics components (such as segments, calculated metrics, etc.).

However, Admins can give the [!UICONTROL Annotation Creation] permission (Analytics Tools) to users via the [Adobe Admin Console](/help/admin/admin-console/permissions/analytics-tools.md).

## Turn annotations on or off {#annotations-on-off}

Annotations can be turned on or off at several levels:

* At the Visualization level: [!UICONTROL Visualization] settings > [!UICONTROL Show annotations]

* At the Project level: [!UICONTROL Project info & settings] > [!UICONTROL Show annotations]

* At the User level: [!UICONTROL Components] > [!UICONTROL User preferences] > [!UICONTROL Data] > [!UICONTROL Show annotations]

![](assets/show-ann.png)

![](assets/show-ann2.png)
-->
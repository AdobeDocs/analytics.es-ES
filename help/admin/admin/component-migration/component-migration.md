---
description: Explica cómo migrar componentes y proyectos de Adobe Analytics a Customer Journey Analytics.
title: Migrar componentes y proyectos de Adobe Analytics a Customer Journey Analytics
feature: Admin Tools
exl-id: 49c7e47a-464b-4465-9b30-d77f886ca6dc
source-git-commit: b8d47e8802198365b348f94efc3f71ff424e83d1
workflow-type: tm+mt
source-wordcount: '1398'
ht-degree: 5%

---

# Migrar componentes y proyectos de Adobe Analytics a Customer Journey Analytics

Los administradores de Adobe Analytics pueden migrar los proyectos de Adobe Analytics y sus componentes asociados a Customer Journey Analytics.

El proceso de migración incluye:

* Creación de nuevo de los proyectos de Adobe Analytics en Customer Journey Analytics.

* Asignación de dimensiones y métricas de grupos de informes de Adobe Analytics a dimensiones y métricas en vistas de datos de Customer Journey Analytics.

  Algunas dimensiones y métricas se asignan automáticamente, mientras que otras se deben asignar manualmente como parte del proceso de migración. Los segmentos también se migran, pero no es necesario asignarlos como parte del proceso de migración.

  Todos los componentes migrados se muestran en el resumen de la migración cuando esta se completa.

## Preparación para una migración

Antes de migrar proyectos a Customer Journey Analytics, obtenga más información sobre la migración de proyectos en la [Preparación para migrar componentes y proyectos de Adobe Analytics a Customer Journey Analytics](/help/admin/admin/component-migration/prepare-component-migration.md).

## Migrar proyectos de Adobe Analytics a Customer Journey Analytics

>[!IMPORTANT]
>
>Antes de migrar proyectos a Customer Journey Analytics como se describe en esta sección, obtenga más información sobre la migración de proyectos en la [Preparación para migrar componentes y proyectos de Adobe Analytics a Customer Journey Analytics](/help/admin/admin/component-migration/prepare-component-migration.md).
>
>**Cualquier dimensión o métrica que asigne es permanente, tanto para este proyecto como para todos los proyectos futuros que se migren en toda la organización de IMS, independientemente de qué usuario realice la migración. Estas asignaciones no se pueden modificar ni deshacer excepto poniéndose en contacto con el Servicio de atención al cliente.**

1. En Adobe Analytics, seleccione la pestaña [!UICONTROL **Administración**] y, a continuación, seleccione [!UICONTROL **Todos los administradores**].

1. En [!UICONTROL **Configuración y recopilación de datos**], seleccione [!UICONTROL **Migración de componentes**].

1. Busque el proyecto que desea migrar. Puede filtrar, ordenar o buscar en la lista de proyectos.

   De forma predeterminada, solo se muestran los proyectos compartidos con usted. Para ver todos los proyectos de su organización, seleccione la **Filtrar** y, a continuación, expanda [!UICONTROL **Otros filtros**] y seleccione [!UICONTROL **Mostrar todo**]. (Para obtener más información sobre cómo filtrar, ordenar y buscar en la lista de proyectos, consulte [Filtrar, ordenar y buscar la lista de proyectos](#filter-sort-and-search-the-list-of-projects).)

1. Pase el ratón sobre el proyecto que quiere migrar y, a continuación, seleccione la **Migrar** icono ![Migrar proyecto](assets/migrate.svg).

   O

   Seleccione el proyecto que desea migrar y, a continuación, seleccione [!UICONTROL **Migrar a Customer Journey Analytics**].

   Solo puede seleccionar un proyecto a la vez para migrar.

   El [!UICONTROL **Migrar nombre_proyecto a Customer Journey Analytics**] Cuadro de diálogo.

   <!-- add screenshot -->

1. En el [!UICONTROL **Propietario del proyecto**] , empiece a escribir el nombre del usuario que desea establecer como propietario del proyecto en Customer Journey Analytics y, a continuación, seleccione su nombre en el menú desplegable.

   El propietario que especifique tendrá derechos de administración completos del proyecto.

1. En el [!UICONTROL **Esquema de asignación para grupos de informes**] , seleccione un grupo de informes.

1. En el [!UICONTROL **Vista de datos**] en el menú desplegable, seleccione la vista de datos del Customer Journey Analytics en la que desea migrar el proyecto y los componentes.

1. Seleccionar [!UICONTROL **Asignar esquema**].

1. En el [!UICONTROL **Asignar esquema**] , expanda la [!UICONTROL **Dimension**] y [!UICONTROL **Métricas**] secciones.

   Algunas dimensiones y métricas en Adobe Analytics se asignan automáticamente a una dimensión o métrica en Customer Journey Analytics. Otros deben asignarse manualmente.

   **Asignar automáticamente dimensiones y métricas**

   >[!NOTE]
   >
   >   Si ha utilizado el SDK web para introducir datos en Adobe Experience Platform, las dimensiones y las métricas no se pueden asignar automáticamente. Para obtener más información, consulte [Requisitos previos](/help/admin/admin/component-migration/prepare-component-migration.md#prerequisites) in [Preparación para migrar componentes y proyectos de Adobe Analytics a Customer Journey Analytics](/help/admin/admin/component-migration/prepare-component-migration.md).

   Algunas dimensiones y métricas en Adobe Analytics se asignan automáticamente a una dimensión o métrica en Customer Journey Analytics. No se puede tomar ninguna decisión de asignación para estas dimensiones y métricas.

   Por ejemplo, la variable **Visitas** en Adobe Analytics se asigna automáticamente con la variable **Sesiones** métrica en Customer Journey Analytics.

   Puede seleccionar cualquier dimensión o métrica para ver sus ID asociados.

   <!-- update screenshot after I can see the Status column -->

   ![Esquema de migración del proyecto](assets/project-migration-schema.png)

   **Asignación manual de dimensiones y métricas**

   Algunas dimensiones y métricas en Adobe Analytics no se pueden asignar automáticamente a una dimensión o métrica en Customer Journey Analytics.

   Cuando una dimensión o métrica no se puede asignar automáticamente, aparece un contador naranja junto a [!UICONTROL **Dimension**] o [!UICONTROL **Métricas**] encabezado de sección, que indica el número de dimensiones o métricas que deben asignarse manualmente. En la tabla, un icono de advertencia ![icono de advertencia](assets/schema-warning.png) se muestra junto a cada dimensión o métrica que debe asignarse manualmente.

   Además, la variable [!UICONTROL **Estado**] la columna dice [!UICONTROL **No asignado**].

   <!-- update screenshot after I can see the Status column -->

   ![Asignación manual del esquema de migración](assets/schema-manual-map.png)

1. Para asignar manualmente dimensiones y métricas, seleccione una dimensión o métrica que contenga un icono de advertencia ![icono de advertencia](assets/schema-warning.png), luego en el [!UICONTROL **Métrica de Customer Journey Analytics asignada**] (o el [!UICONTROL **Dimensión de Customer Journey Analytics asignada**] campo (si va a asignar una dimensión), seleccione la dimensión o métrica del Customer Journey Analytics que desee asignar a la dimensión o métrica que haya seleccionado.

   ![asignación de dimensiones y métricas](assets/schema-manual-map-drop-down.png)

   Una vez asignada una dimensión o métrica, el icono de advertencia desaparece y la variable [!UICONTROL **Estado**] cambios de columna en [!UICONTROL **Asignado**] con un punto verde. (Un estado de [!UICONTROL **Asignado**] con un punto gris indica que la dimensión o métrica se asignó durante una migración anterior; las asignaciones anteriores no se pueden actualizar.)

   Repita este proceso para cada dimensión o métrica que contenga el icono de advertencia.

   Una vez que todas las dimensiones y métricas del grupo de informes de Adobe Analytics se hayan asignado a una dimensión o métrica en la vista de datos del Customer Journey Analytics, aparecerá una marca de verificación verde ![marca de verificación](assets/report-suite-check.png) aparece junto al nombre del grupo de informes en la [!UICONTROL **Esquema de asignación para grupos de informes**] sección.

1. (Condicional) Si el proyecto que está migrando contiene más de un grupo de informes, seleccione otro grupo de informes en la [!UICONTROL **Esquema de asignación para grupos de informes**] y, a continuación, repita los pasos del 6 al 10. <!-- double-check that the step numbers are still correct -->

1. Seleccionar [!UICONTROL **Migrar**].

   >[!WARNING]
   >
   >   Aparece un mensaje de advertencia en pantalla después de seleccionar [!UICONTROL **Migrar**]. Antes de elegir continuar, es necesario que entienda que cualquier dimensión o métrica que asigne es permanente, tanto para este proyecto como para todos los proyectos futuros que se migren en toda la organización. Si continúa, las asignaciones que realice no se podrán modificar.

   Una vez finalizada la migración, la variable [!UICONTROL **Estado de migración**] proporciona un resumen de lo que se ha migrado.

   Si la migración falla, consulte la [Reintento de una migración fallida](#retry-a-failed-migration) para obtener más información.

## Reintento de una migración fallida

Si falla una migración, puede volver a intentar la migración.

Antes de reintentar una migración fallida, asegúrese de eliminar cualquier [elementos no compatibles](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html#understand-unsupported-elements-that-cause-errors) del proyecto.

>[!NOTE]
>
>Si la migración sigue fallando después de volver a intentarlo, póngase en contacto con el Servicio de atención al cliente con el ID de proyecto. Puede encontrar el ID del proyecto en la página de estado de la migración. <!-- when does this page display? How can they get there -->

Para reintentar una migración fallida:

1. En Adobe Analytics, seleccione la pestaña [!UICONTROL **Administración**] y, a continuación, seleccione [!UICONTROL **Todos los administradores**].

1. En [!UICONTROL **Configuración y recopilación de datos**], seleccione [!UICONTROL **Migración de componentes**].

1. Seleccionar [!UICONTROL **Error**] en el [!UICONTROL **Estado de migración**] al lado del proyecto que desea volver a intentar.

   ![error de columna de estado de migración](assets/migration-failed.png)

   El [!UICONTROL **Estado de migración**] página muestra.

   Esta página también se muestra inmediatamente después de completar los pasos de migración descritos en la sección [Migrar proyectos de Adobe Analytics a Customer Journey Analytics](#migrate-adobe-analytics-projects-to-customer-journey-analytics) arriba.

1. Seleccionar [!UICONTROL **Reintentar migración**].

## Filtrar, ordenar y buscar la lista de proyectos

Puede filtrar, ordenar y buscar la lista de proyectos en la página Migración de componentes.

### Filtrado de la lista de proyectos

Puede filtrar por los siguientes criterios:

| Filtro | Descripción |
|---------|----------|
| [!UICONTROL **Estado**] | El estado de la migración: <ul><li>[!UICONTROL **Sin iniciar**]</li><li>[!UICONTROL **Iniciado**]</li><li>[!UICONTROL **Completado**]</li><li>[!UICONTROL **Fallido**]</li></ul>. |
| [!UICONTROL **Etiquetas**] | Seleccione cualquier etiqueta de la lista de etiquetas. Solo se muestran los proyectos que tienen las etiquetas seleccionadas aplicadas. |
| [!UICONTROL **Grupo de informes**] | Seleccione cualquier grupo de informes de la lista de grupos de informes. Solo se muestran los proyectos que utilizan los grupos de informes seleccionados. |
| [!UICONTROL **Propietarios**] | Seleccione cualquier propietario de la lista de propietarios. Solo se muestran los proyectos que son propiedad de los usuarios que seleccione. |
| [!UICONTROL **Otros filtros**] | Los filtros adicionales disponibles son los siguientes: <ul><li>[!UICONTROL **Mío**]: muestra solo los proyectos en los que está establecido como propietario.</li><li>[!UICONTROL **Compartido conmigo**]: muestra solo los proyectos que se han compartido con usted.</li><li>[!UICONTROL **Favoritos**]: Muestra solo los proyectos marcados como favoritos. (Puede marcar un proyecto como favorito desde el menú [página de aterrizaje del proyecto](/help/analyze/landing.md).)</li><li>[!UICONTROL **Mensual**]</li><li>[!UICONTROL **Anual**]</li></ul> |

{style="table-layout:auto"}

### Ordenar la lista de proyectos

Puede ordenar la lista de proyectos por cualquier columna.

Para ordenar la lista de proyectos:

1. Seleccione el encabezado de la columna por la que desea ordenar.

1. (Opcional) Vuelva a seleccionar el mismo encabezado de columna para invertir el orden.

### Buscar un proyecto

Puede buscar en la lista de proyectos de la página Migración de componentes para encontrar el proyecto que desea migrar.

1. En el campo de búsqueda que se encuentra en la parte superior de la página Migración de componentes, empiece a escribir el nombre del proyecto que desea migrar.

1. Seleccione el proyecto cuando aparezca en el menú desplegable.

<!-- is there going to be a way to customize the columns that are displayed? -->

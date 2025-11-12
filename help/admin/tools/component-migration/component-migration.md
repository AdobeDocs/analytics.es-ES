---
description: Explica cómo migrar componentes y proyectos de Adobe Analytics a Customer Journey Analytics.
title: Migración de componentes y proyectos de Adobe Analytics a Customer Journey Analytics
feature: Admin Tools
exl-id: 49c7e47a-464b-4465-9b30-d77f886ca6dc
source-git-commit: ca84a5f807545d7196e2e0e90d3209c32d3fd789
workflow-type: tm+mt
source-wordcount: '1641'
ht-degree: 4%

---

# Migración de componentes y proyectos de Adobe Analytics a Customer Journey Analytics

Los administradores de Adobe Analytics pueden migrar los proyectos de Adobe Analytics y sus componentes asociados a Customer Journey Analytics.

El proceso de migración incluye:

* Creación de nuevo de los proyectos de Adobe Analytics en Customer Journey Analytics.

* Asignación de dimensiones y métricas de grupos de informes de Adobe Analytics a dimensiones y métricas en vistas de datos de Customer Journey Analytics.

  Algunas dimensiones y métricas se asignan automáticamente, mientras que otras se deben asignar manualmente como parte del proceso de migración. Los segmentos también se migran, pero no es necesario asignarlos como parte del proceso de migración.

  Todos los componentes migrados se muestran en el resumen de la migración cuando esta se completa.

>[!NOTE]
>
>En la información de esta página se describe cómo migrar proyectos y sus componentes asociados a la interfaz de usuario.
>
>También puede realizar la migración mediante las API. Para obtener más información, consulte las [API de Adobe Analytics](https://adobedocs.github.io/analytics-2.0-apis/?urls.primaryName=Analytics%202.0%20APIs). Todas las definiciones de API están disponibles en el menú desplegable **[!UICONTROL Seleccionar una definición]**.


## Preparación para una migración

Antes de migrar proyectos a Customer Journey Analytics, obtenga más información sobre la migración de proyectos en [Prepararse para migrar componentes y proyectos de Adobe Analytics a Customer Journey Analytics](/help/admin/tools/component-migration/prepare-component-migration.md).

Además, haga un [inventario de Adobe Analytics](/help/admin/tools/analytics-inventory.md) con la herramienta disponible para los administradores de Analytics.

## Migración de proyectos de Adobe Analytics a Customer Journey Analytics

>[!NOTE]
>
>Antes de migrar proyectos a Customer Journey Analytics como se describe en esta sección, obtenga más información sobre la migración de proyectos en [Prepararse para migrar componentes y proyectos de Adobe Analytics a Customer Journey Analytics](/help/admin/tools/component-migration/prepare-component-migration.md).
>
>**Todas las dimensiones o métricas que asigne se aplican a este proyecto y a todos los proyectos futuros en toda la organización de IMS, independientemente del usuario que realice la migración. Estas asignaciones se pueden actualizar al migrar proyectos futuros.**

1. En Adobe Analytics, seleccione la pestaña [!UICONTROL **Administración**] y, a continuación, seleccione [!UICONTROL **Todos los administradores**].

1. En [!UICONTROL **Configuración y recopilación de datos**], seleccione [!UICONTROL **Migración de componentes**].

1. Busque todos los proyectos que desee migrar. Puede filtrar, ordenar o buscar en la lista de proyectos.

   De forma predeterminada, solo se muestran los proyectos compartidos con usted. Para ver todos los proyectos de su organización, seleccione el icono **Filtrar**, expanda [!UICONTROL **Otros filtros**] y seleccione [!UICONTROL **Mostrar todo**]. (Para obtener más información sobre cómo filtrar, ordenar y buscar en la lista de proyectos, vea [Filtrar, ordenar y buscar en la lista de proyectos](#filter-sort-and-search-the-list-of-projects).)

1. (Condicional) Para migrar varios proyectos al mismo tiempo, active la casilla de verificación situada a la izquierda de cada proyecto que desee migrar y, a continuación, seleccione [!UICONTROL **Migrar a Customer Journey Analytics**].

   Tenga en cuenta lo siguiente al migrar varios proyectos:

   * Puede seleccionar hasta 20 proyectos para migrar al mismo tiempo.

   * El estado de migración debe ser el mismo para todos los proyectos que esté migrando.

     Por ejemplo, si selecciona un proyecto para migrar que tiene un estado de migración de **[!UICONTROL No iniciado]**, no podrá seleccionar otro proyecto que tenga un estado de migración de **[!UICONTROL Error]**.

   * Debe designar el mismo propietario para todos los proyectos que esté migrando.

   * Las dimensiones y métricas deben asignarse a la misma vista de datos para todos los proyectos que esté migrando.

   Se muestra el cuadro de diálogo [!UICONTROL **Migrar nombre_proyecto a Customer Journey Analytics**].

   <!-- add screenshot -->

1. (Condicional) Para migrar un solo proyecto, pasa el ratón sobre el proyecto que deseas migrar y, a continuación, selecciona el icono **Migrar** ![Migrar proyecto](assets/migrate.svg).

   Se muestra el cuadro de diálogo [!UICONTROL **Migrar nombre_proyecto a Customer Journey Analytics**].

   <!-- add screenshot -->

1. En el campo [!UICONTROL **Propietario del proyecto**], empiece a escribir el nombre del usuario que desea establecer como propietario de los proyectos que se están migrando en Customer Journey Analytics y, a continuación, seleccione su nombre en el menú desplegable.

   El propietario que especifique tiene derechos de administración completos para los proyectos migrados. El propietario debe ser un administrador en Customer Journey Analytics. Puede cambiar la propiedad de los proyectos en un paso posterior.

1. En la sección [!UICONTROL **Asignar esquema a grupos de informes**], seleccione un grupo de informes.

1. En el menú desplegable [!UICONTROL **Vista de datos**], seleccione la vista de datos de Customer Journey Analytics donde desee migrar los proyectos y componentes.

   Cuando migre varios proyectos, todos los proyectos que está migrando se combinan en la asignación de vista de datos única.

1. Seleccione [!UICONTROL **Asignar esquema**].

1. En la sección [!UICONTROL **Asignar esquema**], expanda las secciones [!UICONTROL **Dimensiones**] y [!UICONTROL **Métricas**].

   Algunas dimensiones y métricas en Adobe Analytics se asignan automáticamente a una dimensión o métrica en Customer Journey Analytics. Otros deben asignarse manualmente.

   **Asignar dimensiones y métricas automáticamente**

   >[!NOTE]
   >
   >   Si ha utilizado el SDK web para introducir datos en Adobe Experience Platform, las dimensiones y las métricas no se pueden asignar automáticamente. Para obtener más información, consulte [Requisitos previos](/help/admin/tools/component-migration/prepare-component-migration.md#prerequisites) en [Preparación para migrar componentes y proyectos de Adobe Analytics a Customer Journey Analytics](/help/admin/tools/component-migration/prepare-component-migration.md).

   Algunas dimensiones y métricas en Adobe Analytics se asignan automáticamente a una dimensión o métrica en Customer Journey Analytics. No se puede tomar ninguna decisión de asignación para estas dimensiones y métricas.

   Por ejemplo, la métrica **Visitas** de Adobe Analytics se asigna automáticamente con la métrica **Sesiones** de Customer Journey Analytics.

   Puede seleccionar cualquier dimensión o métrica para ver sus ID asociados.

   <!-- update screenshot after I can see the Status column -->

   ![Esquema de migración del proyecto](assets/project-migration-schema.png)

   **Asignar dimensiones y métricas manualmente**

   Algunas dimensiones y métricas de Adobe Analytics no se pueden asignar automáticamente a una dimensión o métrica en Customer Journey Analytics.

   Cuando una dimensión o métrica no se puede asignar automáticamente, aparece un contador naranja junto al encabezado de sección [!UICONTROL **Dimensiones**] o [!UICONTROL **Métricas**], que indica el número de dimensiones o métricas que deben asignarse manualmente. En la tabla, aparece un icono de advertencia ![icono de advertencia](assets/schema-warning.png) junto a cada dimensión o métrica que debe asignarse manualmente.

   Además, la columna [!UICONTROL **Estado**] indica [!UICONTROL **No asignado**].

   <!-- update screenshot after I can see the Status column -->

   ![Asignación manual del esquema de migración](assets/schema-manual-map.png)

1. Para asignar manualmente dimensiones y métricas, seleccione una dimensión o métrica que contenga un icono de advertencia ![icono de advertencia](assets/schema-warning.png) y, a continuación, en el campo [!UICONTROL **Métrica de Customer Journey Analytics asignada**] (o en el campo [!UICONTROL **Dimensión de Customer Journey Analytics asignada**] si asigna una dimensión), seleccione la dimensión o métrica en Customer Journey Analytics que desee asignar a la dimensión o métrica que haya seleccionado.

   ![asignar dimensiones y métricas](assets/schema-manual-map-drop-down.png)

   Después de asignar una dimensión o métrica, el icono de advertencia desaparece y la columna [!UICONTROL **Estado**] cambia a [!UICONTROL **Asignado**] con un punto verde. (El estado de [!UICONTROL **Asignado**] con un punto gris indica que la dimensión o métrica se asignó durante una migración anterior; no se puede actualizar ninguna asignación anterior).

   Repita este proceso para cada dimensión o métrica que contenga el icono de advertencia.

   Una vez que todas las dimensiones y métricas del grupo de informes de Adobe Analytics se hayan asignado a una dimensión o métrica del grupo de informes de Customer Journey Analytics, aparecerá la marca de verificación verde ![check mark](assets/report-suite-check.png) junto al nombre del grupo de informes en la sección [!UICONTROL **Asignar esquema para grupos de informes**].

1. (Condicional) Si los proyectos que está migrando contienen más de un grupo de informes, seleccione otro grupo de informes en la sección [!UICONTROL **Asignar esquema para grupos de informes**] y, a continuación, repita los pasos del 6 al 10. <!-- double-check that the step numbers are still correct -->

1. Seleccione [!UICONTROL **Migrar**].

   >[!WARNING]
   >
   >Aparece un mensaje de advertencia en pantalla después de seleccionar [!UICONTROL **Migrar**]. Antes de elegir continuar, debe comprender que cualquier dimensión o métrica que asigne se aplica a este proyecto y a todos los proyectos futuros de toda la organización de IMS, independientemente de qué usuario realice la migración. Estas asignaciones se pueden actualizar al migrar proyectos futuros.

   Una vez finalizada la migración, la página [!UICONTROL **Estado de la migración**] proporciona un resumen de lo que se ha migrado.

   Si la migración falla, consulte la sección [Reintentar una migración fallida](#retry-a-failed-migration) a continuación para obtener más información.

1. (Opcional) Una vez migrados los proyectos, puede transferir su propiedad a cualquier usuario de Customer Journey Analytics. Para obtener más información, consulte [Transferir recursos](https://experienceleague.adobe.com/es/docs/analytics-platform/using/tools/asset-transfer/transfer-assets) en la Guía de Customer Journey Analytics.

## Reintento de una migración fallida

Si falla una migración, puede volver a intentar la migración.

Antes de reintentar una migración fallida, asegúrese de eliminar [elementos no compatibles](/help/admin/tools/component-migration/prepare-component-migration.md#understand-unsupported-elements-that-cause-errors) del proyecto.

>[!NOTE]
>
>Si la migración sigue fallando después de volver a intentarlo, póngase en contacto con el Servicio de atención al cliente con el ID de proyecto. Puede encontrar el ID del proyecto en la página de estado de la migración. <!-- when does this page display? How can they get there -->

Para reintentar una migración fallida:

1. En Adobe Analytics, seleccione la pestaña [!UICONTROL **Administración**] y, a continuación, seleccione [!UICONTROL **Todos los administradores**].

1. En [!UICONTROL **Configuración y recopilación de datos**], seleccione [!UICONTROL **Migración de componentes**].

1. Seleccione [!UICONTROL **Error**] en la columna [!UICONTROL **Estado de la migración**] junto al proyecto que desea reintentar.

   ![error en la columna de estado de migración](assets/migration-failed.png)

   Se muestra la página [!UICONTROL **Estado de la migración**].

   Esta página también se muestra inmediatamente después de completar los pasos de migración descritos en la sección [Migrar proyectos de Adobe Analytics a Customer Journey Analytics](#migrate-adobe-analytics-projects-to-customer-journey-analytics) anterior.

1. Seleccione [!UICONTROL **Reintentar migración**].

## Filtrar, ordenar y buscar la lista de proyectos

Puede filtrar, ordenar y buscar la lista de proyectos en la página Migración de componentes.

### Filtrado de la lista de proyectos

Puede filtrar por los siguientes criterios:

| Filtrar | Descripción |
|---------|----------|
| [!UICONTROL **Estado**] | El estado de la migración: <ul><li>[!UICONTROL **No iniciado**]</li><li>[!UICONTROL **Iniciado**]</li><li>[!UICONTROL **Completado**]</li><li>[!UICONTROL **Fallido**]</li></ul>. |
| [!UICONTROL **Etiquetas**] | Seleccione cualquier etiqueta de la lista de etiquetas. Solo se muestran los proyectos que tienen las etiquetas seleccionadas aplicadas. |
| [!UICONTROL **Grupo de informes**] | Seleccione cualquier grupo de informes de la lista de grupos de informes. Solo se muestran los proyectos que utilizan los grupos de informes seleccionados. |
| [!UICONTROL **Propietarios**] | Seleccione cualquier propietario de la lista de propietarios. Solo se muestran los proyectos que son propiedad de los usuarios que seleccione. |
| [!UICONTROL **Otros filtros**] | Los filtros adicionales disponibles son los siguientes: <ul><li>[!UICONTROL **Míos**]: muestra solamente los proyectos donde usted es el propietario.</li><li>[!UICONTROL **Compartido conmigo**]: Muestra solamente los proyectos que se han compartido con usted.</li><li>[!UICONTROL **Favoritos**]: muestra solamente los proyectos que están marcados como favoritos. (Puede marcar un proyecto como favorito desde la [página de aterrizaje del proyecto](/help/analyze/landing.md)).</li><li>[!UICONTROL **Mensual**]</li><li>[!UICONTROL **Anual**]</li></ul> |

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

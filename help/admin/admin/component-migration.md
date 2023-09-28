---
description: Explica cómo migrar componentes y proyectos de Adobe Analytics a Customer Journey Analytics.
title: Migrar componentes y proyectos de Adobe Analytics a Customer Journey Analytics
feature: Admin Tools
source-git-commit: 8a9c3b4d6c7a59582a6fd8bdc5464c2dbed3ad1b
workflow-type: tm+mt
source-wordcount: '1018'
ht-degree: 5%

---

# Migrar componentes y proyectos de Adobe Analytics a Customer Journey Analytics

Los administradores de Adobe Analytics pueden migrar componentes y proyectos de Adobe Analytics a Customer Journey Analytics.

El proceso de migración incluye lo siguiente:

* Volver a crear proyectos de Adobe Analytics en Customer Journey Analytics.

* Hacer coincidir dimensiones y métricas de grupos de informes de Adobe Analytics con dimensiones y métricas en vistas de datos de Customer Journey Analytics.

  Algunas dimensiones y métricas coinciden automáticamente; otras deben coincidir manualmente como parte del proceso de migración.

## Requisitos previos

Antes de que sus proyectos y sus dimensiones y métricas asociadas estén listos para migrar, primero debe:

* Utilice el conector de origen de Analytics para ver los datos del grupo de informes de Adobe Analytics en Customer Journey Analytics. Para ello, debe hacer lo siguiente:

   * [Configurar grupos de informes para su incorporación a Adobe Experience Platform y Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html?lang=en#set-up-report-suites-for-ingestion-into-the-adobe-experience-platform-and-customer-journey-analytics)

   * [Ingesta y uso de los datos](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/analytics.html?lang=es)

* Asegúrese de que los usuarios de Customer Journey Analytics estén aprovisionados en las vistas de datos en las que coinciden los datos.

  Para obtener más información, consulte [Permisos de Customer Journey Analytics en el Admin Console](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html?lang=en#customer-journey-analytics-permissions-in-admin-console) in [control de acceso de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html).

  La pestaña Permisos forma parte de cada perfil de producto en Admin Console. Puede añadir usuarios a perfiles de producto específicos. A continuación, asigne derechos a vistas de datos específicas y especifique los permisos que tienen los usuarios en un perfil de producto.

## Creación de un plan de migración como organización

Dado que cualquier componente que coincida con una migración de proyecto determinada se aplica a cualquier migración de proyecto futura de toda la organización, es importante que la organización planifique todas las migraciones de proyecto por adelantado.

Como organización, debe decidir qué dimensiones y métricas coinciden con qué, a fin de evitar que los administradores individuales tomen decisiones en un silo en el momento de la migración de un proyecto.

## Migrar proyectos de Adobe Analytics a Customer Journey Analytics

>[!IMPORTANT]
>
>Antes de migrar proyectos a Customer Journey Analytics como se describe en esta sección, obtenga más información sobre la migración de proyectos en la [Planificación de la migración](#plan-the-migration) sección anterior.
>
>Cualquier dimensión o métrica que coincida es permanente, tanto para este proyecto como para todos los proyectos futuros que se migren en toda la organización. Si continúa, las coincidencias que realice no se podrán modificar.



1. En Adobe Analytics, seleccione [!UICONTROL **Administrador**] pestaña, luego seleccione [!UICONTROL **Todos los administradores**].

1. En [!UICONTROL **Configuración y recopilación de datos**], seleccione [!UICONTROL **Migración de componentes**].

1. (Condicional) Para encontrar rápidamente el proyecto que desea migrar, puede hacer lo siguiente:

   * Filtre la lista de proyectos seleccionando el icono Filtrar.

     Puede filtrar por los siguientes criterios:

      * Estado

      * Etiquetas

      * Grupo de informes

      * Propietarios

      * Otros filtros

   * Utilice el campo de búsqueda para buscar el proyecto que desea migrar.

1. Pase el ratón sobre el proyecto que quiere migrar y, a continuación, seleccione la **Migrar** icono ![Migrar proyecto](assets/migrate.svg).

   o

   Seleccione el proyecto que desea migrar y, a continuación, seleccione [!UICONTROL **Migrar a Customer Journey Analytics**].

   Solo puede seleccionar un proyecto a la vez para migrar.

   El [!UICONTROL **Migrar nombre_proyecto a Customer Journey Analytics**] Cuadro de diálogo.

   <!-- add screenshot -->

1. En el [!UICONTROL **Propietario del proyecto**] , empiece a escribir el nombre del usuario que desea establecer como propietario del proyecto en Customer Journey Analytics y, a continuación, seleccione su nombre en el menú desplegable.

   El propietario que especifique tendrá derechos de administración completos del proyecto.

1. En el [!UICONTROL **Coincidir esquema para grupos de informes**] , seleccione un grupo de informes.

1. En el [!UICONTROL **Vista de datos**] en el menú desplegable, seleccione la vista de datos del Customer Journey Analytics en la que desea migrar el proyecto y los componentes.

1. Seleccionar [!UICONTROL **Coincidir esquema**].

1. En el [!UICONTROL **Coincidir esquema**] , expanda la [!UICONTROL **Dimension**] y [!UICONTROL **Métricas**] secciones.

   Algunas dimensiones y métricas de Adobe Analytics coinciden automáticamente con una dimensión o métrica de Customer Journey Analytics. Otros deben coincidir manualmente.

   **Dimensiones y métricas coincidentes automáticamente**

   Algunas dimensiones y métricas de Adobe Analytics coinciden automáticamente con una dimensión o métrica de Customer Journey Analytics. No se puede tomar ninguna decisión que coincida con estas dimensiones y métricas.

   Por ejemplo, la variable **Visitas** La métrica de Adobe Analytics coincide automáticamente con el **Sesiones** métrica en Customer Journey Analytics.

   Puede seleccionar cualquier dimensión o métrica para ver sus ID asociados.

   <!-- update screenshot after I can see the Status column -->

   ![Esquema de migración del proyecto](assets/project-migration-schema.png)

   **Coincidir manualmente dimensiones y métricas**

   Otras dimensiones y métricas de Adobe Analytics no se pueden hacer coincidir automáticamente con una dimensión o métrica de Customer Journey Analytics.

   Cuando una dimensión o métrica no se puede hacer coincidir automáticamente, aparece un contador naranja junto a la variable [!UICONTROL **Dimension**] o [!UICONTROL **Métricas**] encabezado de sección, que indica el número de dimensiones o métricas que deben coincidir manualmente. En la tabla, un icono de advertencia ![icono de advertencia](assets/schema-warning.png) se muestra junto a cada dimensión o métrica que debe coincidir manualmente.

   <!-- update screenshot after I can see the Status column -->

   ![Coincidencia manual del esquema de migración](assets/schema-manual-map.png)

1. Para hacer coincidir manualmente dimensiones y métricas, seleccione una dimensión o métrica que contenga un icono de advertencia ![icono de advertencia](assets/schema-warning.png), luego en el [!UICONTROL **Métrica de Customer Journey Analytics coincidente**] (o el [!UICONTROL **Dimensión de Customer Journey Analytics coincidente**] campo (si desea hacer coincidir una dimensión), seleccione la dimensión o métrica del Customer Journey Analytics que desee hacer coincidir con la dimensión o métrica que haya seleccionado.

   ![dimensiones y métricas coincidentes](assets/schema-manual-map-drop-down.png)

   Repita este proceso para cada dimensión o métrica que contenga el icono de advertencia.

   Una vez que todas las dimensiones y métricas del grupo de informes de Adobe Analytics coinciden con una dimensión o métrica en la vista de datos del Customer Journey Analytics, active la marca de verificación verde ![marca de verificación](assets/report-suite-check.png) aparece junto al nombre del grupo de informes en la [!UICONTROL **Coincidir esquema para grupos de informes**] sección.

1. (Condicional) Si el proyecto que está migrando contiene más de un grupo de informes, seleccione otro grupo de informes en la [!UICONTROL **Coincidir esquema para grupos de informes**] y, a continuación, repita los pasos del 6 al 10. <!-- double-check that the step numbers are still correct -->

1. Seleccionar [!UICONTROL **Migrar**].

   >[!WARNING]
   >
   >   Aparece un mensaje de advertencia en pantalla después de seleccionar [!UICONTROL **Migrar**]. Antes de elegir continuar, es necesario que entienda que cualquier dimensión o métrica que coincida es permanente, tanto para este proyecto como para todos los proyectos futuros que se migran en toda la organización. Si continúa, las coincidencias que realice no se podrán modificar.

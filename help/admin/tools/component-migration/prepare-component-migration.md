---
description: Explica los preparativos necesarios para preparar la migración de componentes y proyectos de Adobe Analytics a Customer Journey Analytics.
title: Preparación para migrar componentes y proyectos de Adobe Analytics a Customer Journey Analytics
feature: Admin Tools
exl-id: a9ff98dc-6568-428d-a8a8-faca5bc76a29
source-git-commit: 665319bdfc4c1599292c2e7aea45622d77a291a7
workflow-type: tm+mt
source-wordcount: '872'
ht-degree: 10%

---

# Preparación para migrar componentes y proyectos de Adobe Analytics a Customer Journey Analytics

Antes de que alguien en su organización empiece a migrar proyectos como se describe en [Migrar componentes y proyectos de Adobe Analytics a Customer Journey Analytics](/help/admin/tools/component-migration/component-migration.md), complete las secciones siguientes.

## Requisitos previos

Antes de que tus proyectos y sus componentes asociados estén listos para migrar, primero debes seguir los pasos de [Evolución desde Adobe Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/aa-to-cja.html?lang=es) en la Guía de Adobe Customer Journey Analytics. Estos pasos incluyen:

1. Utilice cualquiera de los siguientes métodos para introducir datos en Adobe Experience Platform para ver los datos del grupo de informes de Adobe Analytics en Customer Journey Analytics:

   >[!NOTE]
   >
   >  Al utilizar el SDK web para la ingesta de datos, todos los campos de esquema deben asignarse manualmente. (Para obtener más información sobre el proceso de asignación, consulte [Migrar componentes y proyectos de Adobe Analytics a Customer Journey Analytics](/help/admin/tools/component-migration/component-migration.md))


   * Para utilizar el conector de origen de Adobe Analytics, debe:

      1. [Configurar grupos de informes para su ingesta en Adobe Experience Platform y Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html#set-up-report-suites-for-ingestion-into-the-adobe-experience-platform-and-customer-journey-analytics)

      1. [Ingresar y usar los datos](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/analytics.html?lang=es)

   * Para utilizar el SDK web, debe:

      1. [Configurar grupos de informes para su ingesta en Adobe Experience Platform y Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html#set-up-report-suites-for-ingestion-into-the-adobe-experience-platform-and-customer-journey-analytics)

      1. [Ingesta de datos mediante Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk.html)

1. Cree una [conexión](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/overview.html) y [vista de datos](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=es) con los datos ingeridos.

1. Asegúrese de que los usuarios de Customer Journey Analytics estén aprovisionados en las vistas de datos donde se asignan los datos.

   Para obtener más información, consulte [Permisos de Customer Journey Analytics en Admin Console](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html#customer-journey-analytics-permissions-in-admin-console) en [Control de acceso de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html).

   La pestaña Permisos forma parte de cada perfil de producto en Admin Console. Puede añadir usuarios a perfiles de producto específicos. A continuación, asigne derechos a vistas de datos específicas y especifique los permisos que tienen los usuarios en un perfil de producto.

1. Decida, como organización, cómo asignará los componentes.

   Para obtener más información, vea la sección siguiente, [Decida como organización cómo asignará los componentes](#decide-as-an-organization-how-you-will-map-components).

## Comprender lo que se incluye en una migración

En las tablas siguientes se describen los elementos de un proyecto y de un componente que se incluyen en una migración:

### Elementos de componente que se migran

Las dimensiones y métricas se migran como parte del proceso de asignación que se describe en [Migrar proyectos de Adobe Analytics a Customer Journey Analytics](#migrate-adobe-analytics-projects-to-customer-journey-analytics).

Los segmentos, los intervalos de fechas y las métricas calculadas que aún no existen en Customer Journey Analytics se vuelven a crear allí en función de las dimensiones y métricas asignadas.

|  | Migrado |
|---------|---------|
| **[Propietario](/help/components/calculated-metrics/workflow/cm-manager.md)** | Dimensiones y métricas: No<p>Segmentos e intervalos de fechas: ![marca de verificación](assets/Smock_Checkmark_18_N.svg)</p> |
| **[Compartir](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)** | Dimensiones y métricas: No<p>Segmentos e intervalos de fechas: No</p> |
| **[Descripciones](/help/analyze/analysis-workspace/components/add-component-descriptions.md)** | Dimensiones y métricas: No<p>Segmentos e intervalos de fechas: ![marca de verificación](assets/Smock_Checkmark_18_N.svg)</p> |
| **[Etiquetas](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)** | Dimensiones y métricas: No<p>Segmentos e intervalos de fechas: No</p> |
| **[Atribución (en dimensiones)](/help/analyze/analysis-workspace/attribution/overview.md)** | Dimensiones y métricas: No<p>Segmentos e intervalos de fechas: No</p> |

{style="table-layout:auto"}

### Elementos de proyecto migrados

|  | Migrado |
|---------|----------|
| **[Intervalos de fechas](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md)** | ![marca de verificación](assets/Smock_Checkmark_18_N.svg) |
| **[Segmentos](/help/components/segmentation/seg-overview.md)** | ![marca de verificación](assets/Smock_Checkmark_18_N.svg) |
| **[Segmentos rápidos](/help/analyze/analysis-workspace/components/segments/quick-segments.md)** | ![marca de verificación](assets/Smock_Checkmark_18_N.svg) |
| **[Dimensiones](/help/components/dimensions/overview.md)** | ![marca de verificación](assets/Smock_Checkmark_18_N.svg) asignada automática o manualmente |
| **[Métricas](/help/components/metrics/overview.md)** | ![marca de verificación](assets/Smock_Checkmark_18_N.svg) asignada automática o manualmente |
| **[Paneles](/help/analyze/analysis-workspace/c-panels/panels.md)** | ![marca de verificación](assets/Smock_Checkmark_18_N.svg) |
| **[Visualizaciones](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)** | ![marca de verificación](assets/Smock_Checkmark_18_N.svg) |
| **[Propietario](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)** | ![marca de verificación](assets/Smock_Checkmark_18_N.svg) definida por el usuario que realiza la migración |
| **[Revisión](/help/analyze/analysis-workspace/curate-share/curate.md)** | No |
| **[Compartir](/help/analyze/analysis-workspace/curate-share/share-projects.md)** | No |
| **[Anotaciones](/help/analyze/analysis-workspace/components/annotations/overview.md)** | No |
| **[Estructura de carpetas](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)** | No |
| **[Descripciones](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)** | ![marca de verificación](assets/Smock_Checkmark_18_N.svg) |
| **[Etiquetas](/help/analyze/landing.md)** | No |
| **[Favoritos](/help/analyze/landing.md)** | No |
| **[Horarios](/help/components/scheduled-projects-manager.md)** | No |
| **[Detección de anomalías](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md)** | ![marca de verificación](assets/Smock_Checkmark_18_N.svg) |

{style="table-layout:auto"}

## Comprender los elementos no compatibles que causan errores

Customer Journey Analytics no admite las siguientes visualizaciones y paneles. Si estos elementos se incluyen en un proyecto antes de la migración, pueden provocar el fallo de la migración o errores una vez migrado el proyecto.

Elimine estos elementos del proyecto de Adobe Analytics antes de migrar el proyecto a Customer Journey Analytics. Si una migración falla, elimine estos elementos antes de reintentar la migración.

### Visualizaciones no admitidas

* [Mapa](/help/analyze/analysis-workspace/visualizations/map-visualization.md)

### Paneles no admitidos

* [Analytics for Target (A4T)](/help/analyze/analysis-workspace/c-panels/a4t-panel.md)

* [Comparación de segmentos](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md)

* [Público medio por minuto de medios](/help/analyze/analysis-workspace/c-panels/average-minute-audience-panel.md)

* [Elemento siguiente o anterior](/help/analyze/analysis-workspace/c-panels/next-previous.md)

* [Resumen de página](/help/analyze/analysis-workspace/c-panels/page-summary.md)

* [Análisis de contribución](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md#contribution-analysis)

## Decida, como organización, cómo asignará los componentes

>[!IMPORTANT]
>
>El proceso de migración identifica los componentes del proyecto de Adobe Analytics que no se pueden asignar automáticamente a los componentes de Customer Journey Analytics y le permite asignarlos manualmente.
>
>**Todas las asignaciones realizadas en un proyecto se aplican a todos los proyectos futuros en toda la organización de IMS, independientemente del usuario que realice la migración. Estas asignaciones no se pueden modificar ni deshacer excepto poniéndose en contacto con el Servicio de atención al cliente.**
>
>Por ello, es importante que su organización decida cómo se asignarán las dimensiones y métricas antes de migrar cualquier proyecto. Al hacerlo, se evita que los administradores individuales tomen decisiones en un silo al considerar solo un proyecto.
>
>A continuación se muestra una lista de dimensiones y métricas que debe asignar manualmente si existen en el proyecto. Se recomienda revisar esta lista antes de la migración. Si alguno de estos componentes existe en el proyecto, decida ahora a qué componentes de Customer Journey Analytics los asignará.


### Dimensiones que se deben asignar manualmente

* averagepagetime
* pagetimeseconds
* singlepagevisits
* visitnumber
* timeprior
* timespent
* Categoría
* connectiontype
* customerloyalty
* customlink
* downloadlink
* exitlink
* hitdepth
* hittype
* pathlength
* daysbeforefirstpurchase
* dayssincelastpurchase
* dayssincelastvisit
* identificationstate
* optoutreason
* persistentcookie
* returnfrequency
* searchenginenatural
* searchenginenaturalkeyword
* mobilecarrier
* monitorresolution
* surveybase
* mcaudiences
* tntbase
* targetraw


### Métricas que deben asignarse manualmente

* timespentvisit
* timespentvisitor
* recargas
* bounces
* botar
* pageevents
* pageviewspervisit
* orderspervisit
* averagepagedepth
* averagetimespentonsite
* exitlinkinstances
* customlinkinstances
* downloadlinkinstances
* darkvisitors
* singlepagevisits
* singlevaluevisits
* visitorhomepage
* visitorsmcvisid
* pagesnotfound
* nuevos compromisos
* time_granularity
* concurrentes_visores_visitantes
* concurrentes_visores_ocurrencias
* dispositivos
* personas estimadas
* playback_time_spent_seconds
* playback_time_spent_minutes
* average_minute_audience_time_based
* average_minute_audience_media_time
* average_minute_audience_content_time
* video_length
* targetconversion
* targetimpression

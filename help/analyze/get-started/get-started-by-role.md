---
description: Información general sobre Adobe Analytics, incluida la información sobre la interfaz de Analytics, así como información de introducción para administradores, analistas, usuarios y desarrolladores.
title: Introducción para administradores, analistas, usuarios finales y desarrolladores
feature: Analytics Basics
hide: true
hidefromtoc: true
source-git-commit: f23e0c74072d38d5c6559288b2ced60d98634fac
workflow-type: tm+mt
source-wordcount: '1812'
ht-degree: 34%

---

# Introducción para administradores, analistas, usuarios finales y desarrolladores

Existen tres tipos de usuarios de Adobe Analytics en una organización típica: administradores, analistas y usuarios finales.

Los administradores implementan y configuran Adobe Analytics, los analistas configuran proyectos y crean análisis con Analysis Workspace y los usuarios finales obtienen perspectivas procesables sobre sus clientes, ya sea creando sus propios análisis o trabajando con los analistas para crearlos.

La siguiente información describe cómo cada uno de estos usuarios puede empezar a trabajar con Adobe Analytics.

## Introducción para administradores

Los administradores de Analytics son responsables de elegir el método de implementación más adecuado para su organización.

Una vez implementado Adobe Analytics, los administradores deben realizar varias tareas de configuración para garantizar que los analistas y los usuarios finales obtengan todo el valor de Adobe Analytics. Los administradores también deben monitorizar regularmente su entorno de Analytics para garantizar que el sistema se esté ejecutando de forma eficaz.

### Determinar los tipos de datos que se deben recopilar

Adobe Analytics le permite recopilar datos de varios tipos de canales y reunirlos para ofrecer perspectivas de clientes significativas en tiempo real.

A continuación se indican algunos de los canales admitidos para recopilar datos:

* Teléfonos móviles

* El Internet de las cosas

* TV

* Asistentes de voz

* Coches conectados

* Y más (regularmente se añaden nuevos canales admitidos)

El [método de implementación](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=es) usted elige determina el tipo de datos que se pueden recopilar.

### Implementación de Adobe Analytics

Hay varios métodos de implementación disponibles al implementar Adobe Analytics en el sitio web o la aplicación móvil.

Para obtener información sobre cada método disponible, consulte [Implementación de Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=es).

| | Métodos de implementación |
|---------|---------|
| **Sitios web** | <ul><li>Extensión del SDK web (recomendada)</li><li>SDK web</li><li>Extensión de Analytics</li><li>JavaScript heredado</li></ul> |
| **Aplicaciones móviles** | <ul><li>Extensión del SDK móvil (recomendada)</li><li>Extensión de Analytics</li></ul> |

{style="table-layout:auto"}

### Configuración de Adobe Analytics

Los administradores de Analytics deben completar las siguientes tareas antes de poner Adobe Analytics a disposición de los usuarios de la organización:

| Tarea | Uso previsto | Más información |
|---------|----------|---------|
| Definición de funciones de administrador | Adobe Analytics admite varios tipos de administradores | [Funciones de administrador en Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/admin-roles-in-analytics.html?lang=en) |
| Definición de permisos | Los administradores de Analytics deben asignar perfiles de producto en el Admin Console para Adobe Analytics, Herramientas de grupos de informes y Herramientas de Analytics. | [Permisos de Analytics en Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/summary-tables.html?lang=es) |
| Configure grupos de informes y defina la configuración para su empresa | Un grupo de informes es un silo de datos que Adobe Analytics utiliza para generar informes.<p>Los administradores también pueden configurar [grupos de informes virtuales](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=es) para segmentar más datos.</p> | <ul><li>[Crear un grupo de informes](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/c-new-report-suite/t-create-a-report-suite.html?lang=en)</li><li>[Información general de configuración de empresa](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/company-settings/c-company-settings.html?lang=en)</li></ul> |
| Importar datos | Las fuentes de datos de Adobe Analytics le permiten importar datos adicionales en línea o sin conexión para crear informes. | [Resumen de fuentes de datos](https://experienceleague.adobe.com/docs/analytics/import/data-sources/overview.html?lang=en) |
| Clasificar datos con clasificaciones | Las clasificaciones permiten clasificar los datos para utilizar mejor las variables, lo que permite incluir más contenido en una sola variable. | |
| Administrar componentes | Utilice el diccionario de datos y las áreas de administración para cada tipo de componente para definir qué componentes están disponibles en la implementación de Analytics, así como cuáles están aprobados para su organización.<p>Debe ser una actividad continua para garantizar que los componentes se utilizan correctamente en su organización. </p> | <ul><li>[Información general del diccionario de datos](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.html?lang=es)</li><li>[Administrador de métricas calculadas](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager.html?lang=en)</li><li>[Administración de segmentos](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-manage.html?lang=es)</li><li>[Crear intervalos de fechas](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html?lang=es)</li></ul> |
| Detección de anomalías | La Detección de anomalías constituye un método estadístico para determinar el cambio experimentado en una métrica determinada respecto a los datos anteriores. | [Resumen de la Detección de anomalías](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html?lang=es) |
| Análisis de contribución | Análisis de contribución descubre patrones ocultos en sus datos para explicar las anomalías estadísticas e identificar correlaciones tras acciones de cliente inesperadas, valores que sobrepasan el límite y picos o caídas repentinos de métricas seleccionadas en segmentos de audiencia convergentes. | [Resumen de los análisis de contribución](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.html?lang=es) |
| Segmentación de Analytics | Le permite generar, administrar, compartir y aplicar a sus informes poderosos segmentos centrados en la audiencia utilizando las funcionalidades de Analytics, Adobe Experience Cloud, Adobe Target y otros productos de Adobe integrados. | [Segmentación de Analytics](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html?lang=es) |
| Publicar audiencias en el Audience Manager | | |
| Integraciones | Puede obtener información de otras aplicaciones en Adobe Analytics. <p>A continuación se indican algunas integraciones comunes:</p><ul><li><a href="https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html?lang=en">Analytics for Target</a></li><li><a href="https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html?lang=es">Media Analytics</a></li> | |

{style="table-layout:auto"}

### Monitorización de Adobe Analytics

Hay varias funciones disponibles para ayudarle a monitorizar su entorno de Adobe Analytics.

Los administradores de Analytics deben tener en cuenta las siguientes funciones disponibles para ayudarle a monitorizar aspectos importantes de su entorno de Analytics:

| Tarea | Uso previsto | Más información |
|---------|----------|---------|
| Administrador de actividades de creación de informes | El Administrador de actividades de creación de informes le permite ver la capacidad de creación de informes de cada grupo de informes de su organización. Proporciona una visibilidad detallada del consumo de creación de informes y le ayuda a diagnosticar y corregir problemas de capacidad fácilmente durante las horas de mayor actividad de la creación de informes. | [Administrador de actividades de creación de informes](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/reporting-activity.html?lang=en) |
| Uso de llamadas de servidor | Una llamada al servidor, también conocida como “visita individual” o “solicitud de imagen” es una instancia en la que se envían datos a servidores de Adobe para su procesamiento. Hay disponible un panel Uso de llamadas al servidor que rastrea los datos de consumo de llamadas al servidor y lo compara con su límite contractual. Puede configurar alertas para evitar sobrecargas. | [Resumen de Uso de llamadas al servidor](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-call-usage/overage-overview.html?lang=en) |
| Archivos de registro | Los archivos de registro ayudan a ver cuándo los usuarios inician la sesión, su uso, los accesos, los grupos de informes y los cambios del administrador. | [Registros](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/logs.html?lang=es) |

{style="table-layout:auto"}

## Introducción para analistas

Aunque cualquier persona de una organización puede utilizar Adobe Analytics para obtener perspectivas procesables sobre el comportamiento de los clientes en sitios web y aplicaciones, Adobe Analytics se ha diseñado teniendo en cuenta a los analistas de datos.

A continuación se indican las tareas y funciones clave con las que los analistas deben estar familiarizados para aprovechar toda la potencia de Adobe Analytics y Analysis Workspace.

| Funcionalidad | Uso previsto | Más información |
|---------|----------|---------|
| Generar y compartir proyectos en Analysis Workspace | Analysis Workspace es una herramienta de navegador flexible que le permite crear análisis y compartir perspectivas rápidamente. Mediante la interfaz de arrastrar y soltar, puede crear su análisis, agregar visualizaciones para dar vida a los datos, depurar un conjunto de datos, compartir y programar proyectos con cualquier persona de su organización.<p>Los analistas de datos suelen ser responsables de crear proyectos en Analysis Workspace para usuarios dentro de su organización.</p><p>Una vez creados los proyectos, los analistas los comparten con el [usuarios finales](#end-users)(no analistas) en sus organizaciones que solicitaron los datos y les ayudan a comprender cómo interpretarlos.</p> | <ul><li>[Crear proyectos](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md)</li><li>[Compartir proyectos](/help/analyze/analysis-workspace/curate-share/share-projects.md)</li></ul> |
| Atribución | Los analistas pueden personalizar la forma en que los elementos de dimensión obtienen crédito por los eventos de éxito empleando varios modelos de atribución y ventanas retrospectivas en Analysis Workspace.<p>Los modelos de atribución lineal dan el mismo crédito a cada punto de contacto que conduce a una conversión, mientras que Primer contacto da crédito total al primer punto de contacto. Hay muchos otros modelos de atribución disponibles, incluido el modelo algorítmico, que utiliza técnicas estadísticas para determinar dinámicamente la asignación óptima de crédito. </p> | [Modelos de atribución y ventanas retroactivas](/help/analyze/analysis-workspace/attribution/models.md) |
| Detección de anomalías | El modelado estadístico en Analysis Workspace encuentra automáticamente tendencias inesperadas en los datos analizando métricas y determinando un límite inferior, límite superior y rango esperado de valores. Cuando hay un pico o una caída inesperados, el sistema le alerta en el informe. | [Resumen de la Detección de anomalías](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) |
| Análisis de contribución | Utilice Analysis Workspace para descubrir patrones ocultos en los datos a fin de explicar las anomalías estadísticas e identificar correlaciones tras acciones de cliente inesperadas, valores que sobrepasan el límite y caídas o picos repentinos de métricas entre segmentos de audiencia. | [Resumen de los análisis de contribución](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.md) |
| Alertas inteligentes | Crear y administrar alertas basadas en anomalías de datos y alertas &quot;apiladas&quot; que capturan varias métricas en una sola alerta. | [Resumen de las alertas inteligentes](/help/analyze/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md) |
| Exportación de datos | Las fuentes de datos y Data Warehouse le permiten exportar datos a varios destinos de nube, como Google Cloud Platform, Azure RBAC, Azure SAS y Amazon S3. | [Guía de exportación de Analytics](https://experienceleague.adobe.com/docs/analytics/export/home.html?lang=es) |
| Activity Map | Activity Map es una aplicación de Adobe Analytics diseñada para clasificar la actividad de los vínculos usando superposiciones visuales y que ofrece un tablero de análisis en tiempo real para supervisar la participación de la audiencia en las páginas web.<p>Activity Map permite configurar distintas vistas para identificar visualmente la aceleración de la actividad del cliente, cuantificar las iniciativas de marketing y responder a las necesidades y los comportamientos de la audiencia.</p> | [Activity Map](https://experienceleague.adobe.com/docs/analytics/analyze/activity-map/activity-map.html?lang=es) |
| Report Builder | El Report Builder es un complemento para Microsoft Excel. Report Builder permite crear solicitudes personalizadas a partir de datos de Adobe Analytics que se insertan en hojas de cálculo de Excel. Las solicitudes pueden hacer referencia de forma dinámica a las celdas de las hojas de cálculo y es posible actualizar y personalizar el modo en el que Report Builder presenta los datos. | [Report Builder](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/home.html?lang=es) |

{style="table-layout:auto"}

<!-- * Realtime reporting? -->

## Introducción para usuarios finales

Los usuarios finales que no son analistas profesionales pueden trabajar con analistas de su organización para aprovechar todo el poder de Adobe Analytics y Analysis Workspace, o pueden aprender los conceptos básicos de Analysis Workspace para empezar a obtener perspectivas procesables sobre sus clientes.

### Trabajo con analistas

Normalmente, los usuarios de una organización interesados en obtener más información sobre el comportamiento de los clientes en sus distintos sitios no son analistas profesionales.

Lo ideal es que estos usuarios trabajen con [analistas](#analysts) dentro de una organización para:

1. Defina los requisitos para los análisis explicando al analista lo que espera aprender acerca de los clientes.

1. Revise los análisis para asegurarse de que cumplen los objetivos.

1. Analizar los datos obtenidos de los análisis.

1. Modifique los análisis según sea necesario a lo largo del tiempo.

### Creación de análisis en Analysis Workspace

No es necesario ser analista de datos para obtener perspectivas procesables de Adobe Analytics.

A algunos usuarios les puede resultar útil trabajar con un analista de datos para configurar un proyecto en Analysis Workspace y explicar cómo interpretar los datos, tal como se describe en [Trabajo con analistas](#work-with-analysts); otros usuarios podrían sentirse cómodos creando el proyecto e interpretando los datos ellos mismos.

Analysis Workspace le permite crear análisis rápidamente para recopilar información y luego compartirlas con otros. Mediante la interfaz del explorador arrastrar y soltar, puede crear su análisis, añadir visualizaciones para que los datos cobren vida, depurar un conjunto de datos, compartir y programar proyectos con cualquier persona de su organización.

Para obtener información sobre cómo crear análisis en Analysis Workspace, consulte [Información general de Analysis Workspace](/help/analyze/analysis-workspace/home.md).

## Introducción para desarrolladores

[Las API de Analytics le permiten llamar directamente a los servidores de Adobe para realizar casi cualquier acción que pueda hacer en la interfaz de usuario.](https://developer.adobe.com/analytics-apis/docs/2.0/)

Puede crear informes para explorar, obtener perspectivas o responder a preguntas importantes acerca de sus datos. También puede administrar componentes de Adobe Analytics, como la creación de segmentos o métricas calculadas.
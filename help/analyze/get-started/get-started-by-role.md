---
description: Información general acerca de Adobe Analytics, incluida información acerca de la interfaz de Analytics, así como información de introducción para usuarios y funciones de administrador, analista y desarrollador.
title: Introducción para personas usuarias y personal de administración, análisis y desarrollo
feature: Analytics Basics
exl-id: 11800de5-224a-4bd2-8cb1-a6318925db71
source-git-commit: 4633225cc35658a7de39a40cd77df00137a54461
workflow-type: ht
source-wordcount: '1694'
ht-degree: 100%

---

# Introducción para personas usuarias y personal de administración, análisis y desarrollo

Existen cuatro tipos de usuarios de Adobe Analytics en una organización típica:

* **Administradores:** implemente y configure Adobe Analytics.

* **Analistas:** configure proyectos y cree análisis mediante Analysis Workspace

* **Usuarios finales:** obtenga información procesable sobre sus clientes, ya sea creando sus propios análisis o trabajando con analistas para crearlos

* **Desarrolladores:** utilice las API de Adobe Analytics 2.0 para llamar directamente a los servidores de Adobe y realizar casi cualquier acción que se pueda realizar en la interfaz de usuario, como crear informes para explorar, obtener información o responder preguntas importantes acerca de los datos.

La siguiente información describe cómo cada uno de estos grupos puede empezar a utilizar Adobe Analytics.

## Introducción para roles de administrador

En Analytics, este rol se ocupa de seleccionar el método de implantación más adecuado para la organización.

Una vez implementado Adobe Analytics, se tienen que realizar varias tareas de configuración para garantizar que tanto analistas como personas usuarias finales saquen el máximo partido de Adobe Analytics. Este rol también debería monitorizar regularmente su entorno Analytics para asegurarse de que el sistema funciona de forma eficaz.

### Determinar los tipos de datos que se deben recopilar

Adobe Analytics le permite recopilar datos de varios tipos de canales y reunirlos para ofrecer datos de clientes significativos y en tiempo real.

A continuación se indican algunos de los canales admitidos en los que se pueden recopilar datos:

* Teléfonos móviles

* El Internet de las cosas

* TV

* Asistentes de voz

* Coches conectados

* Y más (periódicamente se añaden nuevos canales admitidos)

El [método de implementación](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=es) que elija determina el tipo de datos que se pueden recopilar.

### Implementación de Adobe Analytics

Existen varios métodos de implementación disponibles para implementar Adobe Analytics en su sitio web o aplicación móvil.

Para obtener información acerca de cada método disponible, consulte [Implementar Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=es).

| | Métodos de implementación |
|---------|---------|
| **Sitios web** | <ul><li>Extensión de SDK web (recomendada)</li><li>SDK web</li><li>Extensión de Analytics</li><li>JavaScript heredado</li></ul> |
| **Aplicaciones móviles** | <ul><li>Extensión de SDK para móviles (recomendada)</li><li>Extensión de Analytics</li></ul> |

{style="table-layout:auto"}

### Configurar Adobe Analytics

Los roles de administrador de Analytics deberían realizar las siguientes tareas antes de poner Adobe Analytics a disposición de la organización:

| Tarea | Uso previsto | Más información |
|---------|----------|---------|
| Definir funciones de administración | Adobe Analytics admite varios tipos de roles de administrador | [Funciones de administrador en Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/admin-roles-in-analytics.html?lang=es) |
| Definir permisos | Los roles de administrador de Analytics tienen que asignar perfiles de producto en Admin Console para Adobe Analytics, Herramientas de grupos de informes y Herramientas de Analytics. | [Permisos de Analytics en Admin Console](/help/admin/admin-console/permissions/analytics-tools.md) |
| Configure grupos de informes y defina la configuración de su compañía | Un grupo de informes es un silo de datos que Adobe Analytics utiliza para generar informes.<p>Los roles de administrador también pueden configurar [grupos de informes virtuales](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=es) para segmentar todavía más los datos.</p> | <ul><li>[Crear un grupo de informes](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/c-new-report-suite/t-create-a-report-suite.html?lang=es)</li><li>[Información general de configuración de compañía](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/company-settings/c-company-settings.html?lang=es)</li></ul> |
| Importación de datos | Las fuentes de datos de Adobe Analytics le permiten importar datos adicionales en línea o sin conexión para la creación de informes. | [Información general de fuentes de datos](https://experienceleague.adobe.com/docs/analytics/import/data-sources/overview.html?lang=es) |
| Clasificar datos con Clasificaciones | Las clasificaciones le permiten clasificar los datos para hacer un mejor uso de las variables, permitiéndole incluir más contenido en una sola variable. | [Resumen general de las clasificaciones](https://experienceleague.adobe.com/docs/analytics/components/classifications/c-classifications.html?lang=es) |
| Administrar componentes | Utilice el diccionario de datos y las áreas de administración de cada tipo de componente para definir qué componentes están disponibles en su implementación de Analytics, así como cuáles están aprobados para su organización.<p>Esta actividad debería ser constante para garantizar que los componentes se utilizan de forma eficaz en su organización. </p> | <ul><li>[Información general del diccionario de datos](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.html?lang=es)</li><li>[Administrador de métricas calculadas](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager.html?lang=es)</li><li>[Administrar segmentos](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-manage.html?lang=es)</li><li>[Crear intervalos de fechas personalizados](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html?lang=es)</li></ul> |
| Detección de anomalías | La Detección de anomalías constituye un método estadístico para determinar el cambio experimentado en una métrica determinada respecto a los datos anteriores. | [Resumen de la Detección de anomalías](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html?lang=es) |
| Análisis de contribución | Análisis de contribución descubre patrones ocultos en sus datos para explicar las anomalías estadísticas e identificar correlaciones tras acciones de cliente inesperadas, valores que sobrepasan el límite y picos o caídas repentinos de métricas seleccionadas en segmentos de público convergentes. | [Resumen de los análisis de contribución](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md#contribution-analysis) |
| Segmentación de Analytics | Le permite crear, administrar, compartir y aplicar potentes segmentos centrados en el público a sus informes mediante las capacidades de Analytics, Adobe Experience Cloud, Adobe Target y otros productos integrados de Adobe. | [Segmentación de Analytics](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html?lang=es) |
| Publicar audiencias en Audience Manager | Adobe Audience Manager es una potente plataforma de administración de datos que le ayuda a crear perfiles de audiencia únicos a partir de integraciones de datos de origen, secundarias o de socio, y de terceros. | [Resumen de Audience Analytics](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/mc-audiences-aam.html?lang=es) |
| Integraciones | Puede mostrar información de otras aplicaciones en Adobe Analytics. <p>A continuación se indican algunas integraciones comunes:</p><ul><li><a href="https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html?lang=es">Analytics for Target</a></li><li><a href="https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html?lang=es">El complemento de colección Streaming Media</a></li> | [Integración de Analytics](https://experienceleague.adobe.com/docs/analytics/integration/home.html?lang=es) |

{style="table-layout:auto"}

### Monitorizar Adobe Analytics

Existen varias características disponibles para ayudarle a monitorizar su entorno de Adobe Analytics.

Los roles de administrador de Analytics deberían estar al tanto de las siguientes características disponibles para ayudar a monitorizar aspectos importantes del entorno de Analytics:

| Tarea | Uso previsto | Más información |
|---------|----------|---------|
| Administrador de actividades de creación de informes | El Administrador de actividades de creación de informes le permite ver la capacidad de creación de informes de cada grupo de informes de su organización. Proporciona una visibilidad detallada del consumo de creación de informes y le ayuda a diagnosticar y corregir fácilmente los problemas de capacidad durante las horas de mayor actividad de creación de informes. | [Administrador de actividades de creación de informes](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/reporting-activity.html?lang=es) |
| Uso de llamadas al servidor | Una llamada al servidor, también conocida como “visita individual” o “solicitud de imagen”, es una instancia en la que se envían datos a servidores de Adobe para su procesamiento. Dispone de un panel de uso de llamadas al servidor que realiza un seguimiento de los datos de consumo de llamadas al servidor y los compara con su límite contractual. Puede configurar alertas para evitar exceder el límite. | [Información general sobre Uso de llamadas al servidor](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-call-usage/overage-overview.html?lang=es) |
| Archivos de registro | Los archivos de registro le permiten ver cuándo la gente inicia sesión, su uso, los accesos, los grupos de informes y los cambios de administración. | [Registros](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/logs.html?lang=es) |

{style="table-layout:auto"}

## Introducción para analistas

Aunque cualquier persona de una organización puede utilizar Adobe Analytics para obtener información procesable sobre el comportamiento de clientes en sitios web y aplicaciones, Adobe Analytics se ha diseñado pensando en analistas de datos.

A continuación se indican las tareas y características principales que debería conocer cada analista para aprovechar al máximo todo el potencial de Adobe Analytics y Analysis Workspace.

| Funcionalidad | Uso previsto | Más información |
|---------|----------|---------|
| Generar y compartir proyectos en Analysis Workspace | Analysis Workspace es una herramienta de navegador flexible que le permite crear análisis y compartir perspectivas rápidamente. Mediante la interfaz de arrastrar y soltar, puede crear su análisis, agregar visualizaciones para dar vida a los datos, depurar un conjunto de datos, compartir y programar proyectos con cualquier persona de su organización.<p>Quienes se dedican al análisis de datos suelen encargarse de crear proyectos en Analysis Workspace para las personas usuarias de la organización.</p><p>Una vez creados los proyectos, estos se comparten con las [personas usuarias finales](#end-users) (no analistas) de las organizaciones que solicitaron los datos, y se les ayuda a aprender a interpretarlos.</p> | <ul><li>[Crear proyectos](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md)</li><li>[Compartir proyectos](/help/analyze/analysis-workspace/curate-share/share-projects.md)</li></ul> |
| Atribución | Cada analista puede personalizar la forma en que los elementos de dimensión se consideran responsables de los eventos de éxito empleando varios modelos de atribución y ventanas retrospectivas en Analysis Workspace.<p>Los modelos de atribución lineal otorgan el mismo mérito a todos los puntos de contacto que llevan a una conversión, mientras que el modelo de primer contacto otorga todo el mérito al primer punto de contacto. Existen muchos otros modelos de atribución, incluido el modelo algorítmico, que utiliza técnicas estadísticas para determinar de forma dinámica la asignación óptima del mérito. </p> | [Modelos de atribución y ventanas retroactivas](/help/analyze/analysis-workspace/attribution/models.md) |
| Detección de anomalías | El modelado estadístico en Analysis Workspace encuentra automáticamente tendencias inesperadas en sus datos analizando métricas y determinando un límite inferior, un límite superior y un rango esperado de valores. Cuando hay un pico o una caída inesperados, el sistema le alerta en el informe. | [Resumen de la Detección de anomalías](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md) |
| Análisis de contribución | Utilice Analysis Workspace para descubrir patrones ocultos en sus datos con el fin de explicar anomalías estadísticas e identificar correlaciones entre acciones inesperadas de clientes, valores fuera de los límites y picos o caídas repentinos de las métricas en todos los segmentos de público. | [Análisis de contribución](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md#contribution-analysis) en [Información general de la detección de anomalías](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md) |
| Alertas inteligentes | Cree y administre alertas basadas en anomalías de los datos y alertas &quot;apiladas&quot; que capturan múltiples métricas en una sola alerta. | [Resumen de las alertas inteligentes](/help/analyze/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md) |
| Exportación de datos | Las fuentes de datos y Data Warehouse le permiten exportar datos a varios destinos en la nube, como Google Cloud Platform, Azure RBAC, Azure SAS y Amazon S3. | [Guía de exportación de Analytics](https://experienceleague.adobe.com/docs/analytics/export/home.html?lang=es) |
| Activity Map | Activity Map es una aplicación de Adobe Analytics diseñada para clasificar la actividad de los vínculos usando superposiciones visuales y que ofrece un tablero de análisis en tiempo real para supervisar la participación de la audiencia en las páginas web.<p>Activity Map permite configurar distintas vistas para identificar visualmente la aceleración de la actividad del cliente, cuantificar las iniciativas de marketing y responder a las necesidades y los comportamientos de la audiencia.</p> | [Activity Map](https://experienceleague.adobe.com/docs/analytics/analyze/activity-map/activity-map.html?lang=es) |
| Report Builder | El Report Builder es un complemento para Microsoft Excel. Report Builder permite crear solicitudes personalizadas a partir de datos de Adobe Analytics que se insertan en hojas de cálculo de Excel. Las solicitudes pueden hacer referencia de forma dinámica a las celdas de las hojas de cálculo y es posible actualizar y personalizar el modo en el que Report Builder presenta los datos. | [Report Builder](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/home.html?lang=es) |

{style="table-layout:auto"}

<!-- * Realtime reporting? -->

## Introducción para personas usuarias finales

Los personas usuarias finales que no sean analistas profesionales pueden trabajar con analistas de su organización para sacar el máximo partido de Adobe Analytics y Analysis Workspace, o bien pueden aprender los conceptos básicos de Analysis Workspace para empezar a obtener información procesable acerca de sus clientes.

### Trabajar con analistas

Normalmente, las personas de una organización interesadas en conocer mejor el comportamiento de los clientes en sus distintos sitios no son analistas profesionales.

Lo ideal sería que estas personas trabajaran con [analistas](#analysts) dentro de la organización para:

1. Definir los requisitos de los análisis explicando a cada analista lo que espera aprender acerca de sus clientes.

1. Revisar los análisis para asegurarse de que cumplen los objetivos.

1. Comentar los datos obtenidos de los análisis.

1. Modificar los análisis en función de las necesidades a lo largo del tiempo.

### Crear análisis en Analysis Workspace

No hace falta ser analista de datos para obtener información procesable de Adobe Analytics.

A algunas personas les puede resultar útil trabajar con analistas de datos para configurar un proyecto en Analysis Workspace y explicar cómo interpretar los datos, tal y como se describe en [Trabajar con analistas](#work-with-analysts), mientras que a otras les puede resultar cómodo generar el proyecto e interpretar los datos por sí mismas.

Analysis Workspace le permite crear análisis rápidamente para recopilar información y luego compartirlas con otros. Mediante la interfaz del explorador arrastrar y soltar, puede crear su análisis, añadir visualizaciones para que los datos cobren vida, depurar un conjunto de datos, compartir y programar proyectos con cualquier persona de su organización.

Para obtener información acerca de cómo crear análisis en Analysis Workspace, consulte [Información general de Analysis Workspace](/help/analyze/analysis-workspace/home.md).

## Introducción para el equipo de desarrollo

[Las API de Analytics le permiten llamar directamente a los servidores de Adobe para realizar casi cualquier acción que pueda hacer en la interfaz de usuario.](https://developer.adobe.com/analytics-apis/docs/2.0/)

Puede crear informes para explorar, obtener perspectivas o responder a preguntas importantes acerca de sus datos. También puede administrar componentes de Adobe Analytics, como la creación de segmentos o métricas calculadas.

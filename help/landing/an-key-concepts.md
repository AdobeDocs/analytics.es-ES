---
description: Esta sección contiene conceptos clave de Adobe Analytics, una breve descripción del concepto y un vínculo a documentación específica con información adicional sobre el tema.
title: 'Adobe Analytics: conceptos clave'
exl-id: 359c6663-33fd-4491-8ea0-55cd9ae31859
source-git-commit: f3eb3c024a80d0b65729929960173f8b3a4267b0
workflow-type: tm+mt
source-wordcount: '1834'
ht-degree: 99%

---

# Adobe Analytics: conceptos clave

Esta sección contiene conceptos clave de Adobe Analytics, una breve descripción del concepto y un vínculo a documentación específica con información adicional sobre el tema.

## Herramientas de Analytics {#concept_833EDD4EB056491DA1BC5A3A45FE285B}

| Product | Descripción | Vínculo de documentación |
| --- | --- | --- |
| Analysis Workspace | Solución de navegador para crear proyectos de análisis sólidos y personalizados y democratizar las perspectivas. Ofrece una mayor flexibilidad para los informes que Reports &amp; Analytics. | [Página de inicio de Analysis Workspace](/help/analyze/analysis-workspace/home.md) |
| Reports &amp; Analytics (antiguamente SiteCatalyst) | Solución de navegador para informes y análisis. Herramienta inicial en el paquete de Analytics. | [Página de inicio de Reports &amp; Analytics](/help/analyze/reports-analytics/getting-started.md) |
| Report Builder | El complemento de Excel le permite crear solicitudes personalizadas de datos de Adobe Analytics y visualizarlas en Microsoft Excel. | [Inicio de Report Builder](/help/analyze/report-builder/home.md) |
| Data Workbench (anteriormente Insight) | Diseñado para recopilar, procesar, analizar y visualizar datos desde interacciones del usuario, tanto en línea como sin conexión, en múltiples canales. | [Cliente de Data Workbench](https://docs.adobe.com/content/help/es-ES/data-workbench/using/client/t-open-ins.html) |
| Data Warehouse | Datos sin procesar para informes personalizados y de almacenamiento, que se pueden ejecutar mediante el filtrado de datos. Sin nivel de visita. | [Inicio de Data Warehouse](/help/export/data-warehouse/data-warehouse.md) |
| Adobe Mobile Services | Agrupa funciones de marketing móvil para aplicaciones móviles pertenecientes a Adobe Experience Cloud, lo que le permite comprender y mejorar la participación del usuario en sus aplicaciones. | [Inicio de Mobile Services](https://docs.adobe.com/content/help/es-ES/mobile-services/using/home.html) |
| Data Connectors de Adobe Exchange (anteriormente Genesis) | Permite importar datos de seguimiento de aplicaciones de terceros en Analytics, para proporcionar una visibilidad completa sobre el rendimiento desde una ubicación centralizada. A partir del 1 de agosto de 2021, Adobe tiene la intención de interrumpir las integraciones de Data Connectors. | [Inicio de Data Connectors](/help/import/data-connectors/data-connectors-eol.md) |
| Adobe Experience Platform Launch | La nueva generación de funcionalidades de administración de etiquetas de sitios web y SDK móvil de Adobe. | [Inicio de Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/launch/using/home.html) |

## Terminología clave {#concept_E473ACBB8E4A42B4AC005538AC12F154}

Haga clic [aquí](/help/technotes/terms.md) para ver un glosario ampliado de términos de Adobe Analytics.

| Término | Descripción | Vínculo de documentación |
| --- | --- | --- |
| Props (tráfico personalizado) | Dimensiones que se utilizan para realizar un seguimiento de la actividad de tráfico del sitio página por página. Las propiedades no se conservan de una página a otra. Aplicaciones clave de las variables de tráfico: <ul> <li>Recuento simple para encontrar el valor “más popular” de un valor específico.</li> <li>Para ver cuántos usuarios pasan por su sitio.</li> </ul> <br> Ejemplos de variables de tráfico: Nombre de página, Secciones de sitio, Navegadores. | [Props](/help/admin/admin/c-traffic-variables/traffic-var.md) |
| eVar (conversión personalizada) | Dimensiones que se conservan durante un período de tiempo personalizado por el usuario. Las opciones de caducidad incluyen la caducidad del evento, la caducidad de la visita o la caducidad a los X días y debe elegirse según el tipo de análisis que se realiza en dicha variable. <br> Diferencias clave entre eVars y props: <ul> <li>Las props suelen utilizarse para el análisis de rutas porque se elimina la persistencia.</li> <li>Las eVars suelen utilizarse para el análisis de conversión.</li> </ul> <br> Ejemplos de variables de conversión: términos de búsqueda internos, promociones internas, campañas externas (s.campaign). | [eVars](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) |
| Eventos/métricas (s.events) | Métricas que miden acciones clave que queremos que nuestros visitantes realicen en nuestro sitio. Existen 3 tipos de eventos: contador, numérico y moneda. Los eventos son más útiles cuando se añaden a informes de variables de conversión (eVar). La eVar proporciona información cualitativa acerca de lo que ha sucedido y el evento proporciona información cuantitativa sobre qué ha sucedido. <br> Diferencias clave entre las eVars y los eventos: <ul> <li>Las eVars nos indican a quién o a qué ha afectado la conversión.</li> <li>Los eventos miden cuántas conversiones han tenido lugar.</li> </ul> <br> Ejemplos de eventos de conversión: pedidos, inicios de aplicación, posibles clientes, ingresos. | [Eventos](/help/admin/admin/c-success-events/success-event.md) |
| Componentes | Dimensiones, métricas, segmentos y granularidades de tiempo (intervalos de fechas) que se pueden arrastrar y soltar en un proyecto. | [Componentes](/help/analyze/analysis-workspace/components/analysis-workspace-components.md) |
| Dimensiones | Recopilación de eVars, propiedades, clasificaciones y valores recopilados estándar de Adobe. | [Dimensiones](/help/components/dimensions/overview.md) |
| Métricas | Recopilación de eventos implementados y métricas calculadas. | [Métricas](/help/analyze/analysis-workspace/components/apply-create-metrics.md) |
| Métricas calculadas | Capacidad para derivar métricas personalizadas de métricas existentes recopiladas mediante la implementación. | [Métricas calculadas](/help/components/c-calcmetrics/cm-overview.md) |
| Segmentos | La capacidad de crear, gestionar, compartir y aplicar segmentos de audiencia eficaces y centrados a sus informes de Analytics. Los segmentos se comparten entre los productos de Analytics y se pueden compartir en Experience Cloud. | [Segmentación](/help/components/segmentation/seg-home.md) |
| Hora (intervalos de fechas) | Posibilidad de filtrar la fecha a cualquier periodo de tiempo y crear intervalos de fechas personalizados que se puedan reutilizar en el análisis. | [Intervalos de fechas](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md) |
| Visualizaciones | Imágenes enriquecidas que pueden ayudar a dar vida a los datos en sus proyectos. | [Visualizaciones](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) |
| Gestión de datos | Capacidad para limitar los componentes accesibles en un proyecto o grupo de informes virtuales. | [Revisión de VRS](/help/components/vrs/vrs-components.md) <br> [Revisión del proyecto](/help/analyze/analysis-workspace/curate-share/curate.md) |

## Informes clave

| Información general de la tienda de aplicaciones | Descripción | Vínculo de documentación |
| --- | --- | --- |
| Lista completa de informes y dimensiones | Definición de todos los informes y dimensiones disponibles en Adobe Analytics. | [Dimensiones](/help/components/dimensions/overview.md) |
| Advertising Analytics | Analice todos los datos de búsqueda pagada de Google y Bing uno al lado del otro, dentro de Adobe Analytics. Las dimensiones creadas mediante la integración incluyen la plataforma de publicidad, palabras clave, el tipo de coincidencia, etc. Las métricas creadas son Impresiones de AMO, Clics de AMO, Coste de AMO, Promedio. Puntuación de calidad de posición y promedio. | [Advertising Analytics](/help/integrate/c-advertising-analytics/overview.md) |
| Audience Analytics | Enriquezca las visitas de Analytics de entrada con la pertenencia de un usuario a la audiencia en AAM. Puede incorporar datos de audiencia de AAM, como información demográfica (p. ej., sexo o nivel de ingresos), información psicográfica (p. ej., intereses y aficiones), datos CRM o datos de impresión publicitaria a cualquier flujo de trabajo de Analytics. Las dimensiones creadas mediante esta integración son ID de audiencia y Nombre de audiencia. | [Audience Analytics](/help/integrate/c-audience-analytics/mc-audiences-aam.md) |
| Attribution IQ | Permite comprender de qué manera ocurre la interacción significativa a lo largo del recorrido del cliente, identificando con inteligencia los puntos de inflexión que llevan a resultados de destino y optimizando, con eficacia, las iniciativas de marketing. Los modelos incluyen caída primera, última, lineal, de participación, en forma de J, en forma de J invertida, en forma de U, de mismo contacto, personalizada y de tiempo. | [Attribution IQ](/help/analyze/analysis-workspace/c-panels/attribution.md) |
| Detección de anomalías | Un método estadístico para determinar el cambio experimentado en una métrica determinada respecto a los datos anteriores. AD está activada de forma predeterminada para todas las visualizaciones de tendencias en Analysis Workspace. | [Detección de anomalías](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) |
| Análisis de contribución | Explora el “por qué” detrás de las anomalías que se producen ejecutando un análisis automatizado de cada métrica y dimensión a la que tiene acceso. | [Análisis de contribución](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.md) |
| Análisis de cohorte | Una cohorte es un grupo de personas que comparten características en común durante un periodo especificado. El análisis de cohorte ayuda a analizar la retención y la pérdida de los usuarios. | [Análisis de cohorte](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) |
| Informes del recorrido del cliente | Muestra información sobre la ruta que siguen los usuarios a través del sitio o la aplicación. En este análisis se pueden usar props, eVars y eventos en Analysis Workspace. | [Visitas en orden previsto de Analysis Workspace](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md) <br> [Flujo de Analysis Workspace](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) <br> [Rutas de Reports &amp; Analytics](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) |
| Canales de marketing | Informes que le ayudan a descubrir qué canales externos atraen a usuarios a su sitio y cuáles son los más efectivos en la generación de conversión. Se proporcionan las vistas de atribución de primer y último toque. Este es el informe de fuente de tráfico externo preferida de Adobe Analytics (en lugar de las fuentes de Campañas o Tráfico) ya que ofrece la vista más completa tanto de los canales orgánicos como de pago. | [Canales de marketing](/help/components/c-marketing-channels/c-getting-started-mchannel.md) |
| Móvil | Muestra información acerca de los sitios web a los que se accede desde un dispositivo móvil o tableta. | [Informes de dispositivos móviles](/help/components/dimensions/mobile-dimensions.md) |
| Aplicación móvil | Muestra información de uso básica relacionada con sus aplicaciones móviles. Estos informes están disponibles una vez que su SDK haya sido implementado y la generación de informes esté activada.  Además, Adobe Mobile Services ha creado una interfaz de aplicación móvil independiente que proporciona datos de aplicación más completos, lo cual le permite comprender y mejorar la implicación del usuario con sus aplicaciones.  Acceda a la interfaz [aquí](https://mobilemarketing.adobe.com). | [Adobe Mobile Services](https://docs.adobe.com/content/help/en/mobile-services/using/home.html) |
| Productos | Identifica el modo en el que algunos productos individuales y grupos de productos (categorías) contribuyen a las distintas métricas de conversión, como Ingresos o Cierres de compra. | [Informes de productos](/help/components/dimensions/product.md) |
| Comparación de segmentos | Detecta las diferencias más significativas estadísticamente entre segmentos a través de un análisis automatizado de cada métrica y dimensión a la cual tenga acceso. | [Comparación de segmentos](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md) |
| Informes de contenido del sitio | Muestran información sobre las páginas y áreas del sitio más activas y sobre los servidores que más se utilizan. | [Informes de contenido del sitio](/help/components/dimensions/page.md) |
| Informes de métricas del sitio | Muestra información cuantitativa sobre su sitio web, por ejemplo visitantes únicos, pedidos, ingresos, etc. Cada métrica puede colocarse en otros informes basados en elementos. | [Informes de métricas del sitio](/help/components/metrics/overview.md) |
| Perfil del visitante | Informe que ayuda a observar los patrones de compras de los clientes en diferentes categorías de perfiles, como países, estados, códigos postales y dominios. | [Perfil del visitante](/help/components/dimensions/language.md) |
| Retención de visitantes | Muestra información acerca de la lealtad de sus clientes, por ejemplo, cuántos visitantes tiene el sitio y con qué frecuencia regresan. | [Retención de visitantes](/help/components/dimensions/customer-loyalty.md) |
| Vínculo, uso compartido y programación del proyecto | Métodos para guardar o compartir su trabajo con otros en la interfaz de Analytics. | [Envío y programación archivos de proyecto](/help/analyze/analysis-workspace/curate-share/send-schedule-files.md) |

## Métricas clave {#concept_392819DC275C48688E2CE4ABD4C5EE43}

| Nombre de la métrica | Definición | Vínculo de documentación |
| --- | --- | --- |
| Lista de métricas completa | Definición de todas las métricas en Adobe Analytics. | [Resumen de las métricas](/help/components/metrics/overview.md) |
| Visitantes únicos | El número de visitantes del sitio web no duplicados durante el transcurso de un periodo de tiempo especificado. | [Visitantes únicos](/help/components/metrics/unique-visitors.md) |
| Visitas | Secuencia de visitas de la página efectuadas en una sesión. La visita empieza cuando una persona ve por primera vez una página del sitio y finaliza tras 30 minutos de inactividad. | [Visitas](/help/components/metrics/visits.md) |
| Vistas de páginas | Una vista de página se produce cuando un visitante ve una página del sitio web. | [Vistas de páginas](/help/components/metrics/page-views.md) |
| Instancias | El número de veces que se definió una variable. Cada vez que Adobe Analytics ve un valor dentro de una variable, las instancias se incrementan en uno en el informe respectivo. | [Instancias](/help/components/metrics/instances.md) |
| Ocurrencias | El número de veces que se definió o se persistió una variable. | [Ocurrencias](/help/components/metrics/occurrences.md) |

## Importar opciones {#concept_7C6DF03B5F9149E2A77F36C739432059}

| Opción | Descripción | Vínculo de documentación |
| --- | --- | --- |
| Importador de clasificaciones | Importa metadatos de dimensiones capturadas a través de la carga FTP o del navegador. Método manual en comparación con el Generador de reglas. | [Importador de clasificaciones](/help/components/classifications/importer/c-working-with-saint.md) |
| Generador de reglas | Crea automáticamente clasificaciones de metadatos de dimensiones en función de reglas definidas por el usuario. | [Clasificación del Generador de reglas](/help/components/classifications/crb/classification-rule-builder.md) |
| Atributos del cliente | Datos CRM cargados en Experience Cloud para su uso en Adobe Analytics y Adobe Target. | [Atributos del cliente](https://docs.adobe.com/content/help/es-ES/core-services/interface/customer-attributes/attributes.html) |
| Fuentes de datos | Importe métricas sin conexión en Analytics por dimensiones o por día. | [Fuentes de datos](/help/import/c-data-sources/datasrc-home.md) |
| Data Connectors de Adobe Exchange | Consulte [Herramientas de Analytics.](/help/import/data-connectors/data-connectors-eol.md) |  |
| Integraciones nativas | Audience Analytics y Advertising Analytics. | Consulte la sección “Informes clave”. |

## Opciones de exportación {#concept_C62B688E259141CF92C048E8110464BE}

| Opción | Descripción | Vínculo de documentación |
| --- | --- | --- |
| Descargas de interfaz de usuario y programación | Exportación de datos de Analysis Workspace como CSV o PDF. | [Descarga de archivos PDF o CSV](/help/analyze/analysis-workspace/curate-share/download-send.md) |
| Report Builder | Consulte Herramientas de Analytics. |  |
| API de Analytics | Cree sus propias consultas personalizadas de datos de Analytics. | <ul><li>[API 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html)</li><li>[API 1.4](https://github.com/AdobeDocs/analytics-1.4-apis)</li></ul> |
| Data Warehouse | Consulte Herramientas de Analytics. |  |
| Fuente de datos de Analytics | La forma más granular de obtener datos de Analytics. Configure una fuente en el nivel de resultados de Analytics. | [Fuente de datos de Analytics](/help/export/analytics-data-feed/data-feed-overview.md) |

## Recopilación y validación de datos {#concept_E07350D4CA5047DAA7D81F762F29606A}

| Método/Recurso | Descripción | Vínculo de documentación |
| --- | --- | --- |
| Recursos para desarrolladores | Documentación que describe las bibliotecas disponibles para la recopilación de datos de Analytics en todas las plataformas disponibles (web, aplicación móvil, vídeo, flash, etc.). | [Documentación para el desarrollador](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
| Guía de implementación | Una descripción de las variables de recopilación de datos y detalles sobre cómo implementar el código de recopilación de datos en JavaScript. | [Guía de implementación](/help/implement/home.md) |
| AppMeasurement (s_code) | Administración global de variables. | [AppMeasurement](/help/implement/js/migrate-from-hcode.md) |
| SDK de aplicaciones | Paquete personalizado que incluye una versión cargada previamente del archivo de configuración para aplicaciones. | <ul><li>[iOS](https://docs.adobe.com/content/help/es-ES/mobile-services/ios/overview.html)</li><li>[Android](https://docs.adobe.com/content/help/es-ES/mobile-services/android/getting-started-android/requirements.html)</li></ul> |
| Adobe Experience Platform Launch | Consulte Herramientas de Analytics. |  |
| VISTA | Permite aplicar lógica del lado del servidor para alterar o segmentar datos a medida que se recopilan. | [Reglas de VISTA](/help/admin/admin/c-processing-rules/c-processing-rules-configuration/processing-rule-order.md) |
| Reglas de procesamiento | Posibilidad de establecer, modificar y copiar variables en la interfaz de usuario de Analytics para modificar los datos recopilados. | [Reglas de procesamiento](/help/admin/admin/c-processing-rules/processing-rules.md) |
| Opciones de depuración | Hay varios depuradores y detectores de paquetes disponibles para ayudarle a validar la implementación, incluido el depurador de Adobe Experience Cloud. | [Adobe Debugger](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj?hl=es) |
| API de inserción de datos | La API de inserción de datos proporciona un mecanismo para la recopilación y el envío de datos del lado del servidor a los servidores de Experience Cloud. En lugar de utilizar señalizaciones JavaScript en cada página web para transmitir datos de visitantes a los servidores de Experience Cloud, la recopilación de datos del lado del servidor recopila datos basados únicamente en solicitudes del navegador web y respuestas del servidor web. | [Pasos para implementar la API de inserción de datos de Adobe Analytics mediante POST](https://helpx.adobe.com/es/analytics/kb/data-insertion-api-post-method-adobe-analytics.html) |

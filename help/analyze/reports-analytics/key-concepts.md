---
description: Esta sección contiene conceptos clave de Adobe Analytics, una breve descripción del concepto y un vínculo a documentación específica con información adicional sobre el tema.
seo-description: Esta sección contiene conceptos clave de Adobe Analytics, una breve descripción del concepto y un vínculo a documentación específica con información adicional sobre el tema.
seo-title: 'Adobe Analytics: conceptos clave'
title: 'Adobe Analytics: conceptos clave'
uuid: ef 5701 c 5-2 d 3 e -4847-851 f -9312 d 55 db 1 a 8
translation-type: tm+mt
source-git-commit: 998699eb14d40b955cb6ae73ecf1940c8aed15ab

---


# Adobe Analytics: conceptos clave

Esta sección contiene conceptos clave de Adobe Analytics, una breve descripción del concepto y un vínculo a documentación específica con información adicional sobre el tema.

## Analytics tools {#concept_833EDD4EB056491DA1BC5A3A45FE285B}

| Producto | Descripción | Vínculo de documentación |
|--- |--- |--- |
| Analysis Workspace | Solución de explorador para generar proyectos de análisis personalizados y robustos y democratizar perspectivas. Ofrece más flexibilidad de informes que Informes y análisis | [adobe.ly/aaworkspacedocs](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/analysis-workspace-features.html) |
| Informes y análisis (anteriormente SiteCatalyst) | Solución de explorador para informes y análisis. Herramienta inicial en el paquete de Analytics. | [Inicio de Informes y análisis](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/getting-started.html) |
| Report Builder | El complemento de Excel permite crear solicitudes personalizadas desde datos de Adobe Analytics y visualizarlas con Microsoft Excel. | [Página principal del Creador de informes](https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/home.html) |
| Análisis específicos (anteriormente Discover) | Herramienta basada en Java para análisis digitales avanzados. Pendiente para su ciclo de vida en el trimestre de 2019. | [Inicio de Análisis específicos](https://docs.adobe.com/content/help/en/analytics/analyze/ad-hoc-analysis/adhoc-home.html) |
| Área de trabajo de datos (anteriormente Insight) | Diseñado para recopilar, procesar, analizar y visualizar datos desde interacciones del usuario, tanto en línea como sin conexión, en múltiples canales. | [Cliente del área de trabajo de datos](https://marketing.adobe.com/resources/help/en_US/insight/client/) |
| Almacén de datos | Datos sin procesar para informes personalizados y de almacenamiento, que se pueden ejecutar mediante el filtrado de datos. Sin nivel de coincidencia. | [Página principal del almacén de datos](https://docs.adobe.com/content/help/en/analytics/export/data-warehouse/data-warehouse.html) |
| Adobe Mobile Services | Agrupa funciones de marketing móvil para aplicaciones móviles pertenecientes a Adobe Experience Cloud, lo que le permite comprender y mejorar la participación del usuario en sus aplicaciones. | [Inicio de Mobile Services](https://docs.adobe.com/content/help/en/mobile-services/using/home.html) |
| Conectores de datos de Adobe Exchange (anteriormente Genesis) | Importar datos de seguimiento de aplicaciones de terceros en Analytics para proporcionar visibilidad completa sobre el rendimiento en una ubicación central. | [Inicio de Conectores de datos](https://marketing.adobe.com/developer/documentation/genesis/c-overview-how-it-works) |
| Administración dinámica de etiquetas (DTM) | Permite administrar etiquetas de Analytics, Target y otros en todos sus sitios, independientemente del número de dominios. | [Página principal de DTM](https://docs.adobe.com/content/help/en/analytics/implementation/implement-analytics-with-dtm/dtm-implementation-overview.html) |
| Adobe Launch | La próxima generación de funciones de administración de SDK móviles y etiquetas de SDK desde Adobe. | [Inicio de Adobe Launch](https://docs.adobe.com/content/help/en/launch/using/overview.html) |

## Key terminology {#concept_E473ACBB8E4A42B4AC005538AC12F154}

Haga clic [aquí](https://docs.adobe.com/content/help/en/analytics/technotes/terms.html) para ver un glosario ampliado de términos de Adobe Analytics.

| Término | Descripción | Vínculo de documentación |
|--- |--- |--- |
| Props (tráfico personalizado) | Dimensiones utilizadas para rastrear la actividad de tráfico de sitio página por página. Las propiedades no se conservan de una página a otra. Aplicaciones clave de las variables de tráfico: <ul><li>Recuento sencillo de encontrar'más populares'de un valor específico</li><li>Visibilidad sobre cómo los usuarios atraviesan el sitio </li></ul><br>Ejemplos de variables de tráfico: Nombre de página, Secciones de sitio, Navegadores</br> | [Props](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/traffic-variables/traffic-var.html) |
| Evar (conversión personalizada) | Dimensiones que persisten durante un período de tiempo personalizado por usted. Las opciones de caducidad incluyen la caducidad del evento, la caducidad de la visita o la caducidad a los X días y deberán elegirse según el tipo de análisis que se realizará en dicha variable.<br>Diferencias clave entre evars y props:</br><ul><li>Las props se utilizan a menudo para el análisis de rutas porque se elimina la persistencia.</li><li>Las evars generalmente se utilizan para análisis de conversión.</li></ul><br>Ejemplos de variables de conversión: términos de búsqueda internos, promociones internas, campañas externas (s.campaign)</br> | [eVars](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html) |
| Eventos/Métricas (s. events) | Métricas que miden las acciones clave que queremos que nuestros visitantes realicen en el sitio. Existen 3 tipos de eventos: contador, numérico y moneda. Los eventos son más útiles cuando se añaden a informes de variables de conversión (eVar). La eVar proporciona información cualitativa acerca de lo que ha sucedido y el evento proporciona información cuantitativa sobre qué ha sucedido. <br>Diferencias clave entre evars y eventos:</br><ul><li>Las evars nos indican quién, qué o qué ha afectado la conversión</li><li>Los eventos miden cuántas conversiones tuvieron lugar</li></ul><br>Ejemplos de eventos de conversión: pedidos, inicios de aplicación, posibles clientes, ingresos.</br> | [Eventos](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/success-events/success-event.html) |
| Componentes | Dimensiones, métricas, segmentos y granularidades de tiempo (intervalos de fechas) que puede arrastrar y soltar en un proyecto. | [Componentes](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html) |
| Dimensiones | Colección de evars, props, clasificaciones y valores recopilados estándar de Adobe. | [Dimensiones](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-descriptions.html) |
| Métricas | Recopilación de eventos y métricas calculadas implementadas. | [Métricas](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/apply-create-metrics.html) |
| Métricas calculadas | Capacidad para derivar métricas personalizadas de métricas existentes capturadas a través de la implementación. | [Métricas calculadas](https://docs.adobe.com/content/help/en/analytics/components/calculated-metrics/cm-overview.html) |
| Segmentos | La capacidad de crear, gestionar, compartir y aplicar segmentos de audiencia eficaces y centrados a sus informes de Analytics. Los segmentos se comparten entre los productos de Analytics y se pueden compartir en Experience Cloud. | [Segmentación](https://docs.adobe.com/content/help/en/analytics/components/segmentation/seg-home.html) |
| Tiempo (intervalos de fechas) | Capacidad de filtrar la fecha a cualquier período de tiempo y crear intervalos de fechas personalizados que se pueden reutilizar en el análisis. | [Intervalos de fechas](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/calendar-date-ranges/calendar.html) |
| Visualizaciones | Imágenes enriquecidas que pueden ayudar a dar vida a los datos en sus proyectos. | [Visualizaciones](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html) |
| Revisión | Capacidad para limitar los componentes accesibles en un proyecto o Grupo de informes virtuales. | [VRS curationproject](https://docs.adobe.com/content/help/en/analytics/components/virtual-report-suites/vrs-components.html)<br>[curationcomparación](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate.html)</br><br>[](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate-projects-vrs.html) |

## Informes clave

| Informe | Descripción | Vínculo de documentación |
|--- |--- |--- |
| Lista completa de informes y dimensiones | Definición de todos los informes y dimensiones disponibles en Adobe Analytics. | [Dimensiones](https://marketing.adobe.com/resources/help/en_US/reference/reports_descriptions.html) |
| Advertising Analytics | Analice todos los datos de búsqueda paga de Google y Bing en paralelo, en Adobe Analytics. Las dimensiones creadas a través de la integración incluyen Plataforma de publicidad, Palabra clave, Tipo de coincidencia, etc. Las métricas creadas son Impresiones AMO, Clics AMO, Costo AMO, Promedio. Posición y promedio. media de AMO. | [Advertising Analytics](https://docs.adobe.com/help/en/analytics/integration/advertising-analytics/overview.html) |
| Audience Analytics | Enriquece las visitas de Analytics entrantes con la pertenencia de un usuario a AAM. puede incorporar datos de audiencia de AAM, como información demográfica (p. ej., sexo o nivel de ingresos), información psicográfica (p. ej. intereses y aficiones), datos CRM y datos de impresiones de publicidad en cualquier flujo de trabajo de Analytics. Las dimensiones creadas mediante esta integración son ID de audiencia y Nombre de audiencia. | [Audience Analytics](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/mc-audiences-aam.html) |
| Attribution IQ | Permite comprender la relevancia de la participación en el transcurso del viaje del cliente, identificando de forma inteligente los puntos de inflación que llevan a los clientes a los resultados objetivo, optimizando en forma efectiva las iniciativas de mercadotecnia. Los modelos incluyen primero, último, lineal, participación, j-forma, inverso j-shape, u-shape, same touch, custom y time decadencia. | [Attribution IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/attribution.html) |
| Detección de anomalías | Método estadístico para determinar el cambio experimentado en una métrica determinada respecto a los datos anteriores. AD está activado de forma predeterminada para todas las visualizaciones de tendencias en Analysis Workspace. | [Detección de anomalías](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html) |
| Análisis de contribución | Explora el «why» detrás de las anomalías que se producen, ejecutando un análisis automatizado de cada métrica y dimensión a la que tenga acceso. | [Análisis de contribución](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.html) |
| Análisis de cohorte | Una cohorte es un grupo de personas que comparten características comunes durante un período especificado. Análisis de cohorte al analizar la retención y la fatiga de los usuarios. | [Análisis de cohorte](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.html) |
| Informes de viaje del cliente | Muestra información sobre la ruta que siguen los usuarios en el sitio o la aplicación. En Analysis Workspace se pueden usar prop, evars y eventos en Analysis Workspace. | [Analysis Workspace faloutanalysis](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow.html)[Workspace flowinformes](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/flow/flow.html)[y rutas de Analytics](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-paths.html) |
| Canales de marketing | Informes que le ayudan a descubrir qué canales externos atraen a usuarios a su sitio y cuáles son los más efectivos en la generación de conversión. Se proporcionan las vistas de atribución de primer y último toque. Este es el informe de fuente de tráfico externo preferida de Adobe Analytics (en lugar de las fuentes de Campañas o Tráfico) ya que ofrece la vista más completa tanto de los canales orgánicos como de pago. | [Canales de marketing](https://docs.adobe.com/content/help/en/analytics/components/marketing-channels/c-getting-started-mchannel.html) |
| Dispositivos portátiles | Muestra información acerca de los sitios web a los que se accede desde un dispositivo móvil o tableta. | [Informe móvil | (https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-mobile.html) |
| Aplicación móvil | Muestra información de uso básica relacionada con sus aplicaciones móviles. Estos informes están disponibles una vez que su SDK haya sido implementado y la generación de informes esté activada.  Además, Adobe Mobile Services ha creado una interfaz de aplicación móvil independiente que proporciona datos de aplicación más completos, lo cual le permite comprender y mejorar la implicación del usuario con sus aplicaciones.  Acceda a la interfaz [aquí](https://mobilemarketing.adobe.com). | [Servicios Adobe Mobile](https://docs.adobe.com/content/help/en/mobile-services/using/home.html) | Productos | Identifica el modo en el que algunos productos individuales y grupos de productos (categorías) contribuyen a las distintas métricas de conversión, como Ingresos o Cierres de compra. | [Informe Productos](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-products.html) |
| Comparación de segmentos | Descubre las diferencias más significativas estadísticamente entre segmentos a través de un análisis automatizado de cada métrica y dimensión a la que tenga acceso. | [Comparación de segmentos](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/segment-comparison/segment-comparison.html) |
| Informe Contenido del sitio | Muestran información sobre las páginas y áreas del sitio más activas y sobre los servidores que más se utilizan. | [Informe Contenido del sitio](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-site-content.html) |
| Informe Métricas del sitio | Muestra información cuantitativa sobre su sitio web, por ejemplo visitantes únicos, pedidos, ingresos, etc. Cada métrica puede colocarse en otros informes basados en elementos. | [Informe Métricas del sitio](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-site-metrics.html) |
| Perfil del visitante | Informe que ayuda a observar los patrones de compras de los clientes en diferentes categorías de perfiles, como países, estados, códigos postales y dominios. | [Perfil del visitante](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-visitor-profile.html) |
| Retención de visitantes | Muestra información acerca de la lealtad de sus clientes, por ejemplo, cuántos visitantes tiene el sitio y con qué frecuencia regresan. | [Retención de visitantes](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-visitor-retention.html) |
| Vínculo del proyecto, Compartir y programación | Métodos para guardar o compartir su trabajo con otros en la interfaz de Analytics. | [Envío y programación de archivos](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/send-schedule-files.html) |

## Key metrics {#concept_392819DC275C48688E2CE4ABD4C5EE43}

| Nombre de la métrica | Definición | Vínculo de documentación |
|---|---|---|
| Lista de métricas completa | Definición de todas las métricas en Adobe Analytics. | [Información general sobre las métricas](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-overview.html) |
| Visitantes únicos | El número de visitantes del sitio web no duplicados durante el transcurso de un periodo de tiempo especificado. | [Visitantes únicos](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-unique-visitors-v15-dsc.html) |
| Visitas | Secuencia de visitas de la página efectuadas en una sesión. La visita empieza cuando una persona ve por primera vez una página del sitio y finaliza tras 30 minutos de inactividad. | [Visitas](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-visit.html) |
| Vistas de páginas | Una vista de página se produce cuando un visitante ve una página del sitio web. | [Vistas de páginas](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-page-view.html) |
| Instancias | El número de veces que se definió una variable. Cada vez que Adobe Analytics ve un valor dentro de una variable, las instancias se incrementan en uno en el informe respectivo. | [Instancias](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-instance.html) |
| Ocurrencias | El número de veces que se definió o persistió una variable. | [Ocurrencias](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-occurrences.html) |

## Importar opciones {#concept_7C6DF03B5F9149E2A77F36C739432059}

| Opción | Descripción | Vínculo de documentación |
|---|---|---|
| Importador de clasificaciones | Importa metadatos de dimensiones capturadas a través de la carga FTP o del navegador. Método manual en comparación con el Generador de reglas. | [Importador de clasificaciones](https://marketing.adobe.com/resources/help/en_US/reference/c_working_with_saint.html) |
| Generador de reglas | Crea automáticamente clasificaciones de metadatos de dimensiones en función de reglas definidas por el usuario. | [Generador de reglas de clasificación](https://marketing.adobe.com/resources/help/en_US/reference/classification_rule_builder.html) |
| Atributos del cliente | Datos CRM cargados en Experience Cloud para su uso en Adobe Analytics y Adobe Target. | [Atributos del cliente](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/attributes.html) |
| Fuentes de datos | Imprima métricas sin conexión en Analytics con dimensiones o solo por día. | [Fuentes de datos](https://docs.adobe.com/content/help/en/analytics/import/data-sources/datasrc-home.html) |
| Conectores de datos de Adobe Exchange | Consulte [Herramientas de Adobe Analytics](../../analyze/reports-analytics/key-concepts.md#concept_833EDD4EB056491DA1BC5A3A45FE285B). |  |
| Integraciones nativas | Audience Analytics y Advertising Analytics. | Consulte la sección «Informes clave». |

## Export options {#concept_C62B688E259141CF92C048E8110464BE}

| Opción | Descripción | Vínculo de documentación |
|---|---|---|
| Descargas y programación de la interfaz de usuario | Exportar datos de Analysis Workspace como CSV o PDF | [Descarga de archivos PDF o CSV](/help/analyze/analysis-workspace/curate-share/download-send.md) |
| Report Builder | Consulte Herramientas de Analytics. |
| API de Analytics | Cree sus propias consultas personalizadas de datos de Analytics. | <ul><li>[API 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html)</li><li>[API 1.4](https://github.com/AdobeDocs/analytics-1.4-apis)</li></ul> |
| Data Warehouse | Consulte Herramientas de Analytics. |  |
| Fuente de datos de análisis | La forma más granular de obtener datos de Analytics. Configure una fuente en el nivel de resultados de Analytics. | [Fuente de datos de análisis](https://docs.adobe.com/content/help/en/analytics/export/analytics-data-feed/get-started/data-feed-overview.html) |


## Data collection and validation {#concept_E07350D4CA5047DAA7D81F762F29606A}

| Método/Recurso | Descripción | Vínculo de documentación |
|--- |--- |--- |
| Recursos para desarrolladores | Documentación que describe las bibliotecas disponibles para la recopilación de datos de Analytics en todas las plataformas disponibles (web, aplicación móvil, vídeo, flash, etc.) | [Documentos para desarrolladores](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
| Guía de implementación | Una descripción de las variables de recopilación de datos y detalles sobre cómo implementar el código de recopilación de datos en JavaScript. | [Guía de implementación](https://docs.adobe.com/content/help/en/analytics/implementation/home.html) |
| AppMeasurement (s_code) | Administración global de variables | [AppMeasurement](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html) |
| SDK de aplicaciones | Paquete personalizado que incluye una versión cargada previamente del archivo de configuración para aplicaciones. | <ul><li>[iOS](https://docs.adobe.com/content/help/en/mobile-services/ios/overview.html)</li><li>[Android](https://docs.adobe.com/content/help/en/mobile-services/android/getting-started-android/requirements.html)</li></ul> |
| DTM y Adobe Launch | Consulte Herramientas de Analytics. |  |
| VISTA | Permite aplicar lógica del lado del servidor para alterar o segmentar datos a medida que se recopila. | [Reglas de VISTA](https://marketing.adobe.com/resources/help/en_US/reference/VISTA.html) |
| Reglas de procesamiento | Capacidad de configurar, modificar y copiar variables en la interfaz de usuario de Analytics para alterar los datos recopilados. | [Reglas de procesamiento](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/processing-rules/processing-rules.html) |
| Opciones de depuración | Hay varios depuradores y husmeadores de paquetes disponibles para ayudar a validar su implementación, incluido el depurador de Adobe Experience Cloud. | [Adobe Debugger](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj?hl=en) |
| API de inserción de datos | La API de inserción de datos proporciona un mecanismo para la recopilación de datos del lado del servidor y el envío a los servidores de Experience Cloud. En lugar de utilizar señalizaciones JavaScript en cada página Web para transmitir datos de visitantes a servidores de Experience Cloud, la colección de datos de parte del servidor recopila datos basados solamente en solicitudes del explorador Web y respuestas del servidor Web. | [Pasos para implementar la API de inserción de datos de Adobe Analytics mediante POST](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html) |

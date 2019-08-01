---
description: Esta sección contiene conceptos clave de Adobe Analytics, una breve descripción del concepto y un vínculo a documentación específica con información adicional sobre el tema.
seo-description: Esta sección contiene conceptos clave de Adobe Analytics, una breve descripción del concepto y un vínculo a documentación específica con información adicional sobre el tema.
seo-title: 'Adobe Analytics: conceptos clave'
title: 'Adobe Analytics: conceptos clave'
uuid: ef 5701 c 5-2 d 3 e -4847-851 f -9312 d 55 db 1 a 8
translation-type: tm+mt
source-git-commit: d3819975bb65ccf345d60474e268ed9d1b1606a7

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

## Key features {#concept_216E78AD39DD453D940AE857F4C7D4DF}

<table id="table_5CD38BD3BE854E69B6925EA3F02AFC92"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Informe </th> 
   <th colname="col2" class="entry"> Descripción </th> 
   <th colname="col3" class="entry"> Vínculo de documentación </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Lista de informes completa </td> 
   <td colname="col2"> Definición de todos los informes en Adobe Analytics. </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/reports_descriptions.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/es_ES/reference/reports_descriptions.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tráfico personalizado (Propiedades) </td> 
   <td colname="col2">Se utiliza para realizar un seguimiento de la actividad de tráfico del sitio página por página. Las propiedades no se conservan de una página a otra. Aplicaciones clave de las variables de tráfico: 
    <ul id="ul_A935EC5271684B9599F683C7B31400ED"> 
     <li id="li_58E0596050A34ACC821916EA61E946EF">Para capturar un valor que puede asociarse con Vistas de páginas, Visitas, Visitantes o Instancias. </li> 
     <li id="li_2B4C557AAD0544BE8204C0D7CE587175">Para encontrar el "más popular" de un valor específico. </li> 
     <li id="li_7FA62BE657F047459DF439BFB9F332F5">Para ver cuántos usuarios pasan por su sitio. </li> 
    </ul> <p>Ejemplos de variables de tráfico: Nombre de página, Secciones de sitio, Navegadores. </p> </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/traffic_var.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/es_ES/reference/traffic_var.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Conversión personalizada (eVar) </td> 
   <td colname="col2">Se utiliza principalmente para generar informes sobre eventos de conversión y conservarlos durante un periodo de tiempo personalizado por usted. Las opciones de caducidad incluyen la caducidad del evento, la caducidad de la visita o la caducidad a los X días y deberán elegirse según el tipo de análisis que se realizará en dicha variable. <p>Diferencias clave entre las variables de conversión y las variables de tráfico: </p> 
    <ul id="ul_B0A7482A81B94C5F86C06E5507DB393D"> 
     <li id="li_272E414520AA4603AE5EC397B0F93630"> Las variables de tráfico personalizadas están ligadas a métricas de tráfico, no a conversión. A menudo se utilizan para el análisis de rutas. </li> 
     <li id="li_EBBF9A35C64845FE9683540DFA89E7E9">Las variables de conversión personalizadas pueden estar ligadas al tráfico y a la conversión, y a menudo se utilizan para análisis de conversión. </li> 
    </ul> <p>Ejemplos de variables de conversión: términos de búsqueda internos, promociones internas, campañas externas (s.campaign). </p> </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/conversion_var_admin.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/es_ES/reference/conversion_var_admin.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Eventos de éxito (s.events) </td> 
   <td colname="col2"> <p>Miden acciones clave que queremos que nuestros visitantes realicen en nuestro sitio. </p> <p>Existen 3 tipos de eventos: contador, numérico y moneda. Los eventos son más útiles cuando se añaden a informes de variables de conversión (eVar). La eVar proporciona información cualitativa acerca de lo que ha sucedido y el evento proporciona información cuantitativa sobre qué ha sucedido. </p> <p>Diferencias clave entre las variables de conversión y los eventos personalizados: </p> 
    <ul id="ul_2B95D7437DE444DD9618DBFE6A8612D1"> 
     <li id="li_5951858853334EFA931A5BC57E5C933F">Las variables de conversión nos indican a quién o a qué ha afectado la conversión. </li> 
     <li id="li_339755C842714E0DB8DB4DFAA43AB4F7"> Los eventos personalizados miden cuántas conversiones han tenido lugar. </li> 
    </ul> <p>Ejemplos de eventos de conversión: pedidos, inicios de aplicación, posibles clientes, ingresos. </p> </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/success_event.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/es_ES/reference/success_event.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Métrica del sitio </td> 
   <td colname="col2"> Muestra información cuantitativa sobre su sitio web, por ejemplo visitantes únicos, pedidos, ingresos, etc. Cada métrica puede colocarse en otros informes basados en elementos. </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/reports_site_metrics.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/es_ES/reference/reports_site_metrics.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Contenido del sitio </td> 
   <td colname="col2"> Muestran información sobre las páginas y áreas del sitio más activas y sobre los servidores que más se utilizan. </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/reports_site_content.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/es_ES/reference/reports_site_content.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dispositivos portátiles </td> 
   <td colname="col2"> Muestra información acerca de los sitios web a los que se accede desde un dispositivo móvil o tableta. </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/reports_mobile.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/es_ES/reference/reports_mobile.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Aplicación móvil </td> 
   <td colname="col2"> <p>Muestra información de uso básica relacionada con sus aplicaciones móviles. Estos informes están disponibles una vez que su SDK haya sido implementado y la generación de informes esté activada. </p> <p>Además, Adobe Mobile Services ha creado una interfaz de aplicación móvil independiente que proporciona datos de aplicación más completos, lo cual le permite comprender y mejorar la implicación del usuario con sus aplicaciones. </p> <p>Acceda a la interfaz en: </p> <p><a href="https://mobilemarketing.adobe.com" format="https" scope="external"> https://mobilemarketing.adobe.com</a> </p> </td> 
   <td colname="col3"> <p>Adobe Mobile Services: </p> <p><a href="https://marketing.adobe.com/resources/help/en_US/mobile/" format="https" scope="external"> https://marketing.adobe.com/resources/help/es_ES/mobile/</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Informes de ruta </td> 
   <td colname="col2"> Muestra información sobre el orden en que se accede a las páginas del sitio web. </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/reports_paths.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/es_ES/reference/reports_paths.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Productos </td> 
   <td colname="col2"> Identifica el modo en el que algunos productos individuales y grupos de productos (categorías) contribuyen a las distintas métricas de conversión, como Ingresos o Cierres de compra. </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/reports_products.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/es_ES/reference/reports_products.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Retención de visitantes </td> 
   <td colname="col2"> Muestra información acerca de la lealtad de sus clientes, por ejemplo, cuántos visitantes tiene el sitio y con qué frecuencia regresan. </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/reports_visitor_retention.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/es_ES/reference/reports_visitor_retention.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Perfil del visitante </td> 
   <td colname="col2"> Informe que ayuda a observar los patrones de compras de los clientes en diferentes categorías de perfiles, como países, estados, códigos postales y dominios. </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/reports_visitor_profile.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/es_ES/reference/reports_visitor_profile.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Canales de marketing </td> 
   <td colname="col2">Informes que le ayudan a descubrir qué canales externos atraen a usuarios a su sitio y cuáles son los más efectivos en la generación de conversión. Se proporcionan las vistas de atribución de primer y último toque. <p>Este es el informe de fuente de tráfico externo preferida de Adobe Analytics (en lugar de las fuentes de Campañas o Tráfico) ya que ofrece la vista más completa tanto de los canales orgánicos como de pago. </p> </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/mchannel/index.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/es_ES/mchannel/index.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Informes personalizados, vínculo del informe, marcadores y tableros </td> 
   <td colname="col2"> Métodos para guardar o compartir su trabajo con otros en la interfaz de Analytics. </td> 
   <td colname="col3">Informes personalizados: <p><a href="https://marketing.adobe.com/resources/help/en_US/reference/reports_custom.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/es_ES/reference/reports_custom.html</a> </p> <p>Vínculo del informe: </p> <p><a href="https://marketing.adobe.com/resources/help/en_US/sc/user/t_reports_share_link.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/es_ES/sc/user/t_reports_share_link.html</a> </p> <p>Marcadores </p> <p><a href="https://marketing.adobe.com/resources/help/en_US/sc/user/bookmarks.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/es_ES/sc/user/bookmarks.html</a> </p> <p>Tableros </p> <p><a href="https://marketing.adobe.com/resources/help/en_US/sc/user/dashboard.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/es_ES/sc/user/dashboard.html</a> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Key metrics {#concept_392819DC275C48688E2CE4ABD4C5EE43}

| Nombre de la métrica | Definición | Vínculo de documentación |
|---|---|---|
| Lista de métricas completa | Definición de todas las métricas en Adobe Analytics. | [https://marketing.adobe.com/resources/help/es_ES/reference/metrics.html](https://marketing.adobe.com/resources/help/en_US/reference/metrics.html) |
| Visitantes únicos | El número de visitantes del sitio web no duplicados durante el transcurso de un periodo de tiempo especificado. | [https://marketing.adobe.com/resources/help/es_ES/reference/metrics_unique_visitors.html](https://marketing.adobe.com/resources/help/en_US/reference/metrics_unique_visitors.html) |
| Visitas | Secuencia de visitas de la página efectuadas en una sesión. La visita empieza cuando una persona ve por primera vez una página del sitio y finaliza tras 30 minutos de inactividad. | [https://marketing.adobe.com/resources/help/es_ES/reference/metrics_visit.html](https://marketing.adobe.com/resources/help/en_US/reference/metrics_visit.html) |
| Vistas de páginas | Una vista de página se produce cuando un visitante ve una página del sitio web. | [https://marketing.adobe.com/resources/help/es_ES/reference/metrics_page_view.html](https://marketing.adobe.com/resources/help/en_US/reference/metrics_page_view.html) |
| Instancias | El número de veces que se definió una variable. Cada vez que Adobe Analytics ve un valor dentro de una variable, las instancias se incrementan en uno en el informe respectivo. | [https://marketing.adobe.com/resources/help/es_ES/reference/metrics_instance.html](https://marketing.adobe.com/resources/help/en_US/reference/metrics_instance.html) |
| Métricas calculadas | Métricas personalizadas que puede crear a partir de métricas existentes. Por ejemplo, si dispone de los ingresos y del número de visitas, puede crear una métrica personalizada de los ingresos medios por visita o los ingresos divididos por visitas (ingresos/visitas). | [https://marketing.adobe.com/resources/help/es_ES/analytics/calcmetrics/](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/) |

## Importar opciones {#concept_7C6DF03B5F9149E2A77F36C739432059}

| Opción | Descripción | Vínculo de documentación |
|---|---|---|
| Importador de clasificaciones | Importa metadatos de dimensiones capturadas a través de la carga FTP o del navegador. Método manual en comparación con el Generador de reglas. | [https://marketing.adobe.com/resources/help/es_ES/reference/c_working_with_saint.html](https://marketing.adobe.com/resources/help/en_US/reference/c_working_with_saint.html) |
| Generador de reglas | Crea automáticamente clasificaciones de metadatos de dimensiones en función de reglas definidas por el usuario. | [https://marketing.adobe.com/resources/help/es_ES/reference/classification_rule_builder.html](https://marketing.adobe.com/resources/help/en_US/reference/classification_rule_builder.html) |
| Fuentes de datos | Importa métricas sin conexión en Analytics por dimensiones o por día. | [https://marketing.adobe.com/resources/help/en_US/sc/datasources/datasrc_home.html](https://marketing.adobe.com/resources/help/en_US/sc/datasources/datasrc_home.html) |
| Conectores de datos | Consulte [Productos](../../analyze/reports-analytics/key-concepts.md#concept_833EDD4EB056491DA1BC5A3A45FE285B). |  |

## Export options {#concept_C62B688E259141CF92C048E8110464BE}


<table id="table_99867D82082D4756872FC3ABD83A33A1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opciones </th> 
   <th colname="col2" class="entry"> Descripción </th> 
   <th colname="col3" class="entry"> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Descargas del informe de interfaz </td> 
   <td colname="col2"> La forma más sencilla de exportar datos desde Analytics. </td> 
   <td colname="col3">https://microsite.omniture.com/t2/help/en_US/survey/index.html#Downloading_a_Report_Using_ <p>Basic_Options </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Almacén de datos </td> 
   <td colname="col2">Consulte <a href="../../analyze/reports-analytics/key-concepts.md#concept_833EDD4EB056491DA1BC5A3A45FE285B" format="dita" scope="local">Productos</a>. </td> 
   <td colname="col3"> - </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Creador de informes </td> 
   <td colname="col2">Consulte <a href="../../analyze/reports-analytics/key-concepts.md#concept_833EDD4EB056491DA1BC5A3A45FE285B" format="dita" scope="local">Productos</a>. </td> 
   <td colname="col3"> - </td> 
  </tr> 
  <tr> 
   <td colname="col1"> API de Analytics </td> 
   <td colname="col2"> Cree sus propias consultas personalizadas de datos de Analytics. </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/developer/documentation" format="https" scope="external"> https://marketing.adobe.com/developer/es/documentation</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fuentes de datos del flujo de navegación </td> 
   <td colname="col2"> La forma más granular de obtener datos de Analytics. Configurar una fuente a nivel de resultados de Analytics. </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/sc/clickstream/datafeeds_reference.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/es_ES/sc/clickstream/datafeeds_reference.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Programar datos </td> 
   <td colname="col2"> La mayoría de las opciones de exportación de Adobe Analytics cuentan con funciones que le permiten programar la entrega de datos e informes por correo electrónico o en sitios FTP. </td> 
   <td colname="col3"> - </td> 
  </tr> 
 </tbody> 
</table>

## Data collection and validation {#concept_E07350D4CA5047DAA7D81F762F29606A}

<table id="table_53039DCCAC1D47F7A1E3485609D13E4D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Método/Recurso </th> 
   <th colname="col2" class="entry"> Descripción </th> 
   <th colname="col3" class="entry"> Vínculo de documentación </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Recursos para desarrolladores </td> 
   <td colname="col2"> Documentación que describe las bibliotecas disponibles para la recopilación de datos de Analytics en todas las plataformas disponibles (web, aplicación móvil, vídeo, flash, etc.) </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/developer.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/es_ES/reference/developer.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Guía de implementación </td> 
   <td colname="col2"> Una descripción de las variables de recopilación de datos y detalles sobre cómo implementar el código de recopilación de datos en JavaScript. </td> 
   <td colname="col3"> <p><a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/es_ES/sc/implement/index.html</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> AppMeasurement (s_code) </td> 
   <td colname="col2"> Administración global de variables </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/appmeasure_mjs.html#" format="html" scope="external"> https://marketing.adobe.com/resources/help/es_ES/sc/implement/appmeasure_mjs.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SDK de aplicaciones </td> 
   <td colname="col2"> Paquete personalizado que incluye una versión cargada previamente del archivo de configuración para aplicaciones. </td> 
   <td colname="col3">iOS: <p><a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/?f=requirements" format="https" scope="external"> https://marketing.adobe.com/resources/help/es_ES/mobile/ios/?f=requirements</a> </p> <p>Android: </p> <p><a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/requirements.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/en_US/mobile/android/requirements.html</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dynamic Tag Management (DTM) </td> 
   <td colname="col2">Consulte <a href="../../analyze/reports-analytics/key-concepts.md#concept_833EDD4EB056491DA1BC5A3A45FE285B" format="dita" scope="local">Productos</a>. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> VISTA </td> 
   <td colname="col2"> Un método para la rellenar variables de informes desde del lado del servidor. VISTA utiliza reglas de segmentación del visitante para crear segmentación en tiempo real de todos los datos en línea. Estas reglas permiten alterar o segmentar datos prácticamente de cualquier modo que se desee y sin necesidad de implementar lógica compleja en el sitio. </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/VISTA.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/es_ES/reference/VISTA.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Reglas de procesamiento </td> 
   <td colname="col2"> Una forma de simplificar la recopilación de datos y gestionar el contenido a medida que se envía para la generación de informes mediante la sección de herramientas de administración. Las reglas de procesamiento ayudan a simplificar la interacción con los grupos de TI y los desarrolladores Web, porque ofrecen una interfaz para establecer, modificar y copiar variables. </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/processing_rules.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/es_ES/reference/processing_rules.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Opciones de depuración </td> 
   <td colname="col2"> Existen diversos depuradores y husmeadores de paquetes disponibles para ayudar a validar su implementación. Nuestro depurador preferido es Charles. Otros son Adobe Debugger, HTTPFox, Firebug, Omnibug, Fiddler y HTTPWatch. </td> 
   <td colname="col3">Adobe Debugger: <p><a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/debugger.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/es_ES/sc/implement/debugger.html</a> </p> <p>Charles: </p> <p><a href="https://www.charlesproxy.com/" format="http" scope="external"> https://www.charlesproxy.com/</a> </p> </td> 
  </tr> 
 </tbody> 
</table>

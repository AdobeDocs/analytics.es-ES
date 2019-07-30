---
title: Términos utilizados en Adobe Analytics
description: Glosario para Adobe Analytics, definición de términos comunes utilizados.
translation-type: tm+mt
source-git-commit: 5ca51ad6b967687004d9447964ed87b29077b330

---


# Términos utilizados en Adobe Analytics

Utilice este glosario para comprender el contexto de muchos términos que utiliza Adobe Analytics.

* **Consola de administración:** Puede hacer referencia a:
   * Herramientas de administración heredadas, donde se administran la configuración del grupo de informes en Adobe Analytics. En versiones anteriores de Adobe Analytics, los permisos de usuario también se administraban aquí. See [Admin Tools](../admin/admin/c-admin-tools.md) in the Admin user guide.
   * Admin Console de Adobe, donde se aprovisiona el acceso al producto y se administran los permisos de usuario. See [Admin Console](../admin/admin-console/home.md) in the Admin user guide.
* **Asignación:** Si una variable de conversión encuentra más de un valor durante una visita, la configuración de asignación de la variable determina qué valor se conservará. See [Conversion variables](../admin/admin/conversion-var-admin/conversion-var-admin.md) in the Admin user guide.
* **Anomalía:** Se detecta usando modelado estadístico para buscar automáticamente tendencias inesperadas en los datos. El modelo analiza las métricas y determina un límite inferior, límite superior y rango esperado de valores. See [Anomaly Detection](../analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) in the Analyze user guide.
* **Appmeasurement:** Biblioteca de códigos utilizada para recopilar datos y enviarlos a Adobe. See the [Homepage](../implement/home.md) of the Implement user guide.
* **Ranura ASI:** Ya no existe. En versiones anteriores de Adobe Analytics, las ranuras ASI proporcionan un contenedor de grupo de informes temporal para ver los datos segmentados. En la versión actual de Adobe Analytics, los segmentos se pueden aplicar instantáneamente a cualquier informe.
* **Desglose:** Permite ver una dimensión dentro del contexto de otra dimensión. See [Break down dimensions](../analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md) in the Analyze user guide.
* **Devolución:** Visita que consiste en una sola visita. See [Bounces](../components/c-variables/c-metrics/metrics-bounces.md) in the Components user guide. Consulte también Acceso único.
* **Métrica calculada:** Permite la combinación de métricas, funciones estadísticas y fórmulas existentes para su uso en los informes. See [Calculated metrics](../components/c-calcmetrics/cm-overview.md) in the Components user guide.
* **Campaña:** Puede hacer referencia a:
   * La variable Campaign, que rellena la dimensión Código de seguimiento. See [Page variables](../implement/js-implementation/c-variables/page-variables.md) in the Implement user guide.
   * Una clasificación predeterminada de la dimensión Código de seguimiento; se crea automáticamente para todos los grupos de informes.
   * Adobe Campaign, parte de Adobe Experience Cloud. More information on [Adobe.com](https://www.adobe.com/marketing/campaign.html).
* **Canal:** Puede hacer referencia a:
   * La variable Canal, que rellena la dimensión Secciones del sitio. See [Page variables](../implement/js-implementation/c-variables/page-variables.md) in the Implement user guide.
   * Canales de marketing, componente que ayuda a comprender cómo llegan los usuarios al sitio. See [Marketing Channels](../components/c-marketing-channels/c-overview.md) in the Components user guide.
* **Clasificación:** Una función de Adobe Analytics que permite la agrupación de valores de dimensión. See [Classifications](../components/c-classifications2/c-classifications.md) in the Components user guide.
* **Fuente de datos del flujo de navegación:** Consulte Fuente de datos.
* **Variable de conversión:** Se denomina de forma colloquialmente evars. Almacena un valor personalizado y conserva el valor de la variable hasta que caduque. See [Conversion variables](../components/c-variables/dimensionslist/reports-conversion.md) in the Components user guide.
* **Correlación:** Ya no se usa como término; reemplazados por desgloses de dimensión. En versiones anteriores de Adobe Analytics, las correlaciones permitían desglosar las variables de tráfico. See [Break down dimensions](../analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md) in the Analyze user guide.
* **Datos actuales:** Una opción en algunos informes que permite la inclusión de datos recopilados recientemente que aún no se han procesado completamente. See [Current data](../analyze/reports-analytics/current-data.md) in the Analyze user guide.
* **Vínculo personalizado:** Un tipo de visita que contiene datos de vista que no son de página. See the [s.tl() function](../implement/js-implementation/function-tl.md) in the Implement user guide. Consulte también Visita individual.
* **Atributos del cliente:** Una función de Experience Cloud que permite cargar datos de atributos. See [Customer attributes](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/attributes.html) in the Core Services user guide.
* **Delegado de asistencia al cliente:** Usuario designado autorizado para interactuar directamente con el Servicio de atención al cliente de Adobe. See [Customer support delegates](https://helpx.adobe.com/experience-cloud/supported-users.html) in the Experience Cloud Knowledgebase.
* **Conectores de datos:** Solución de desarrollo completa que permite a terceros automatizar la carga de datos en Adobe Analytics. Los clientes de terceros pueden utilizar un conector de datos para enriquecer sus datos en Adobe Analytics. La mayoría de los conectores de datos utiliza un flujo de trabajo similar en las fuentes de datos. Consulte Conectores de datos en la Guía Importar usuario.
* **Fuente de datos:** Exportación de datos sin procesar que enumera cada visita como una fila y variables como columnas separadas. Se utiliza comúnmente para exportar datos de Adobe Analytics a una base de datos de terceros. See [Data feeds](../export/analytics-data-feed/c-getstarted/data-feed-overview.md) in the Export user guide.
* **Fuentes de datos:** Permite al usuario cargar datos desde un archivo en Adobe Analytics. Normalmente, el archivo se extrae de un sitio FTP. See [Data Sources](../import/c-data-sources/datasrc-home.md) in the Import user guide.
* **Almacén de datos:** Una función de Adobe Analytics que le permite solicitar informes más grandes. See [Data Warehouse](../export/data-warehouse/data-warehouse.md) in the Export user guide.
* **Dimensión:** Un tipo de componente que contiene valores de variable, como texto. Algunos ejemplos son Nombre de página, Código de seguimiento o Dominio de referencia. Una métrica suele ser su equivalente.
* **Administración dinámica de etiquetas:** Solución anterior de administración de etiquetas de Adobe. See [DTM implementation overview](../implement/c-implement-with-dtm/dtm-implementation-overview.md) in the Implement user guide. Adobe recomienda utilizar Launch Platform Platform en su lugar.
* **Serialización de eventos:** Proceso de implementación de medidas para evitar la recopilación de eventos duplicados. See [Event serialization](../implement/js-implementation/event-serialization.md) in the Implement user guide.
* **Evar:** Consulte Variable de conversión.
* **Evento:** Consulte Evento de éxito.
* **Excelclient:** Ya no se utiliza como término. Nombre del predecesor del Creador de informes.
* **Caducidad:** En el contexto de una variable de conversión, el tiempo que el valor persiste en el back-end. Esta persistencia permite asociar eventos con valores de variables antes de la visita del evento. See [Conversion variables](../admin/admin/conversion-var-admin/conversion-var-admin.md) in the Admin user guide.
* **Flujo:** Un tipo de visualización en Analysis Workspace que muestra las rutas que tomaron los usuarios en el sitio. See [Flow visualization](../analyze/analysis-workspace/visualizations/c-flow/flow.md) in the Analyze user guide.
* **Genesis:** Ya no se utiliza como término. El nombre anterior de Data Connectors.
* **Grupo de informes globales:** Término informal designado para un grupo de informes que recopila visitas de varios sitios.
* **Código H:** Predecesor a appmeasurement. En versiones anteriores de Adobe Analytics, las versiones de código se midieron por «versión H», como H 24, H 23.1, etc.
* **Visita individual:** Una sola solicitud de imagen enviada a los servidores de recopilación de datos de Adobe. Las vistas de página y los vínculos personalizados pueden conocerse como visitas individuales.
* **Solicitud de imagen:** Imagen transparente de 1 x 1 píxeles utilizada para comunicarse con los servidores de recopilación de datos de Adobe. Un sitio Web solicita esta imagen invisible con una cadena de consulta larga que contiene datos; Adobe devuelve la imagen invisible y analiza la cadena de consultas recibida.
* **Insight:** Puede hacer referencia a:
   * Nombre anterior del Área de trabajo de datos.
   * Perspectiva personalizada, un nombre histórico para la variable de tráfico personalizada.
* **KPI:** Abreviación de indicador de rendimiento clave. Métricas que ayudan a una empresa a comprender el rendimiento de su sitio. Cada organización tiene KPI diferentes que miden distintos aspectos de su negocio. See [Create a solution design document](../implement/prepare/solution-design.md) in the Implement user guide.
* **Latencia:** Retraso entre cuándo se recopilan los datos y cuándo está disponible en los informes. La latencia típica de un grupo de informes es de 30 a 90 minutos. See [Latency](../technotes/latency.md) in the Technotes user guide.
* **Lanzamiento:** Abreviado de Adobe Experience Platform Launch, la solución de implementación actual de Adobe. See [Overview](https://docs.adobe.com/content/help/en/launch/using/overview.html) in the Adobe Experience Platform Launch user guide.
* **Prop de lista:** Una configuración que convierte una variable de tráfico típica para admitir varios valores en la misma visita. Cualquier variable de tráfico personalizada puede convertirse en una prop de lista si la configuración está habilitada. See [Page variables](../implement/js-implementation/c-variables/page-variables.md) in the Implement user guide.
* **Var de lista:** Variable diferente separada de variables de conversión. Las variables de lista admiten varios valores en la misma visita y los valores de variables se conservan en una visita, similar a las variables de conversión. Solo hay tres variables de lista disponibles para una organización. See [Page variables](../implement/js-implementation/c-variables/page-variables.md) in the Implement user guide.
* **Empresa de inicio de sesión:** Recopilación de grupos de informes utilizados por su organización. Algunas organizaciones tienen varias empresas de inicio de sesión que se aplican a distintas partes de su organización.
* **Métrica:** Un tipo de componente que contiene datos cuantitativos. Los valores de las métricas suelen contener números, como Vistas de página, Visitas e Ingresos. Una dimensión suele ser su equivalente.
* **Etiquetado de grupos múltiples:** La práctica de enviar la misma visita a varios grupos de informes. Con la introducción a los grupos de informes virtuales, esta práctica ya no es necesaria. La mayoría de los esfuerzos de etiquetado de grupos múltiples ayudan a dar cabida a un grupo de informes globales.
* **Normalización:** Una manera de organizar una visualización que toma todas las métricas y forzarlas a proporciones iguales, lo que permite comparar las tendencias más fácilmente.
* **Omniture:** Ya no se utiliza como término. Organización que posee Adobe Analytics antes de adquirir Adobe en 2009.
* **Rutas:** Consulte Flujo.
* **Informe clasificado:** Formato de informe que suele seguir una dimensión con una métrica. Este tipo de informe permite ver los artículos principales, como las páginas más visitadas del sitio. Consulte también Informe de tendencias.
* **Tiempo real:** Muestra las variables configuradas tan pronto como se recopila con poco latencia. See [Real-time reports](../admin/admin/realtime/realtime.md) in the Admin user guide.
* **Grupo de informes:** Contenedor global al que envía datos. Todos los informes de Adobe Analytics hacen referencia a un grupo de informes.
* **RSID:** Abreviación del ID de grupo de informes. Un grupo de informes tiene un nombre práctico y una ID de grupo de informes.
* **Vista de página:** Tipo de visita que incrementa las vistas de página. See [Page views](../components/c-variables/c-metrics/metrics-page-view.md) in the Components user guide. Consulte también Visita individual.
* **Reglas de procesamiento:** Puede hacer referencia a:
   * Reglas de procesamiento, una manera de modificar la recopilación de datos utilizando ciertas reglas en la Consola de administración. See [Processing rules](../admin/admin/c-processing-rules/processing-rules.md) in the Admin user guide.
   * Reglas de procesamiento de canal de mercadotecnia, un conjunto de reglas que determina el canal de mercadotecnia en el que pertenece una visita. See [Marketing channel processing rules](../admin/admin/marketing-channels-admin.md) in the Admin user guide.
* **Prop:** Consulte Variable de tráfico.
* **s. t ():** El nombre de la función en una biblioteca appmeasurement que envía una solicitud de imagen de vista de página. Some AppMeasurement libraries use `s.track()` instead. See [s.t()](../implement/js-implementation/function-t.md) in the Implement user guide.
* **s<span>.</span>tl ():** El nombre de la función en una biblioteca appmeasurement que envía una solicitud de imagen de seguimiento de vínculos. Some AppMeasurement libraries use `s.trackLink()` instead. See [s.tl()](../implement/js-implementation/function-tl.md) in the Implement user guide.
* **Satélite:** Ya no se utiliza como término. Nombre del producto anterior para la administración dinámica de etiquetas.
* **Segmento:** Permite centrarse en un subconjunto específico de los datos. See [Segmentation](../components/c-segmentation/seg-overview.md) in the Components user guide.
* **Contenedor de segmentos:** Parte de un segmento que determina cuántos datos introducen. Los contenedores pueden basarse en vistas de página, visitas o visitantes. See [Segmentation](../components/c-segmentation/seg-overview.md) in the Components user guide.
* **Serialización:** Consulte Serialización de eventos.
* **Llamada al servidor:** Nombre alternativo para una solicitud de imagen o visita, utilizada principalmente en contexto de facturación.
* **Acceso único:** Visita donde una dimensión tenía un solo valor único. La visita puede tener varias visitas, siempre y cuando no haya varios valores únicos. See [Single access](../components/c-variables/c-metrics/metrics-single-access.md) in the Components user guide. Consulte también Devolución.
* **Sitecatalyst:** Ya no se utiliza como término. Nombre del producto anterior para Adobe Analytics.
* **Subrelación:** Ya no se usa como término; reemplazados por desgloses de dimensión. En versiones anteriores de Adobe Analytics, las subrelaciones permitían desglosar las variables de conversión. See [Break down dimensions](../analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md) in the Analyze user guide.
* **Evento de éxito:** Acción rastreada por un usuario. Su organización determina qué eventos se rastrearán y qué variables de evento de éxito utiliza para rastrearlo. See [Custom events](../components/c-variables/c-metrics/metrics-custom.md) in the Components user guide.
* **Usuario admitido:** Consulte Delegado de asistencia al cliente.
* **Variable de tráfico:** Se denomina de forma colloquialmente props. Almacena un valor personalizado para una sola visita. Las versiones anteriores de Adobe Analytics proporcionan valores únicos, pero las mejoras en la plataforma hacen que las variables de tráfico personalizadas sean innecesarias. Adobe recomienda utilizar variables de conversión personalizadas (evars) en la mayoría de los casos. See [Custom traffic variables](../components/c-variables/dimensionslist/reports-custom-traffic.md) in the Components user guide.
* **Informe de tendencias:** Formato de informe que generalmente muestra varios intervalos de fechas con una métrica. Este tipo de informe permite ver cómo funciona una métrica a través del tiempo. Consulte también Informe de clasificación.
* **Visitante único**: Representa la cantidad de individuos únicos que ingresaron al sitio. Un solo visitante único puede tener varias visitas. See [Unique visitor](../components/c-variables/c-metrics/metrics-unique-visitors.md) in the Components user guide.
* **Grupo de informes virtuales:** Contenedor virtual de datos que hace referencia a un grupo de informes normal y permite refinar los datos. Los datos no se envían a un grupo de informes virtuales; en su lugar, los datos se envían a un grupo de informes normal y un grupo de informes virtuales se desactiva de esos datos recopilados. See [Virtual report suites](../components/vrs/vrs-about.md) in the Components user guide.
* **Visita:** Representa la cantidad de sesiones únicas que se han producido en el sitio. See [Visits](../components/c-variables/c-metrics/metrics-visit.md) in the Components user guide.
* **Regla VISTA:** Lógica personalizada creada por Adobe en la solicitud de un cliente para copiar, analizar o filtrar datos en el lado del servidor. Las reglas VISTA suelen suponer costes adicionales. Consulte también Reglas de procesamiento.
* **Señalización web:** Consulte Solicitud de imagen.

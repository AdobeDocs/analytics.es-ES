---
description: Esta página de ayuda contiene casos de uso recomendados para cada herramienta de Adobe Analytics. Las herramientas deben considerarse en el orden en que aparecen en la lista. Si una herramienta específica no se adapta a sus necesidades, continúe con la siguiente herramienta.
title: ¿Qué herramienta de Adobe Analytics debo usar?
uuid: 1179e49d-3cfc-4abd-a8eb-35c5ae380c16
exl-id: d65575df-19c6-4129-89c8-d36de7bb6b2f
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '1158'
ht-degree: 98%

---

# ¿Qué herramienta de Adobe Analytics debo usar?

Esta página de ayuda contiene casos de uso recomendados para cada herramienta de Adobe Analytics. Las herramientas deben considerarse en el orden en que aparecen en la lista. Si una herramienta específica no se adapta a sus necesidades, continúe con la siguiente herramienta.

Para obtener más información sobre comparativas de producto de Adobe Analytics, diríjase [aquí](/help/admin/c-analytics-product-comparison/analytics-product-comparison.md).

## Interfaz de usuario de informes de Adobe Analytics {#user-interfaces}

**[Analysis Workspace](/help/analyze/analysis-workspace/home.md)** debe ser la interfaz de usuario de referencia para todas sus necesidades de informe y análisis. Adobe continúa invirtiendo en el lanzamiento de actualizaciones mensuales de este producto. Si hay una tarea que no puede realizar en Analysis Workspace, evalúe las otras interfaces que aparecen a continuación.**

**[Reports &amp; Analytics](/help/analyze/reports-analytics/overview/report-overview.md)** debe usarse:

* Por parte de los usuarios principiantes que necesitan acceso a los informes predefinidos que son más fáciles de explorar.
* Para acceder a datos en tiempo real en la IU.
* Para configurar eventos de Calendario.
* Para configurar Targets.
* Para ver informes de Bot.
* Para acceder a visualizaciones de vídeo únicas de Video Daypart y Viewer Drop-off.
* Para utilizar las Listas de publicación en informes programados.

El **[Data Workbench](https://experienceleague.adobe.com/docs/data-workbench/using/home.html)** debe usarse:

* Como la opción de herramienta de Analytics más flexible (para análisis en el nivel de visita y de visitante).
* Para crear un conjunto de datos de varios canales de interacciones en línea y sin conexión desde CRM hasta POS a web.
* Para generar atribuciones avanzadas (modelos algorítmicos y basados en reglas).
* Para generar modelos predictivos y estadísticos (puntuación de tendencia, agrupación en clústeres, correlaciones, etc.).
* Para análisis de latencia (tiempo antes/desde un evento).
* Para la identificación y exportación de segmentos completos mediante Adobe Experience Cloud.

## Importación de datos en Adobe Analytics {#import}

**[Las clasificaciones](/help/components/classifications/c-classifications.md)** deben usarse:

* Cuando hay metadatos que desea asociar a un valor recopilado (eVar, prop, canal de marketing).
* Opciones:

   * Generador de reglas: úselo cuando tenga valores de formato predecibles que se recopilen para una variable (por ejemplo, valores delimitados). Este enfoque le permite configurar reglas una vez y, en gran medida, no tendrá que volver a modificarlas.
   * Importación del explorador: Úsela cuando no tenga valores predecibles o cuando tenga una lista de valores limitada que requiera una actualización única. Para este enfoque es necesario supervisar de forma continuada las clasificaciones para identificar nuevos valores.

Las **[Fuentes de datos](/help/import/c-data-sources/datasrc-home.md)** deben usarse:

* Cuando hay datos sin conexión que desea escribir de forma permanente en Adobe Analytics.
* Opciones:

   * Resumen: cargas de datos sencillas, por día o de dimensiones limitadas.
   * ID de transacción: cargas de datos que conectan un extremo en línea a datos sin conexión y que asocian por completo los datos importados a una instantánea de visitante capturada en línea (por ejemplo, pedidos completados en línea y devueltos sin conexión).
   * Procesamiento completo: fuentes de datos con marca de tiempo, procesadas como si fueran visitas recopiladas por servidores de Adobe (es decir, los datos se insertan directamente en el recorrido del visitante).

Los **[Data Connectors](https://www.adobeexchange.com/experiencecloud.html)** deben usarse:

* Al interactuar con un proveedor ajeno que dispone de una conexión compatible con Adobe Analytics. Los Data Connectors suelen incorporar a Adobe Analytics datos en el nivel de resumen de manera permanente, automática y recurrente.

La **[API de inserción de datos](/help/import/c-data-insertion-api/c-data-insertion-api.md)** debe usarse:

* Cuando sea necesario cargar datos en Adobe Analytics y no sea posible utilizar Adobe AppMeasurement o el código del SDK móvil.

**[API de inserción de datos en lotes](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)**

* Tanto la API de inserción de datos como la API de inserción masiva de datos son métodos para enviar datos de colección del lado del servidor a Adobe Analytics. Las llamadas a la API de inserción de datos se realizan a razón de un evento a la vez. La API de inserción masiva de datos acepta archivos con formato CSV que contienen datos de evento, un evento por fila. Si está trabajando en una nueva implementación de la colección del lado del servidor, le recomendamos utilizar la API de inserción masiva de datos.

**[Los atributos del cliente](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html)** deben usarse:

* Si obtiene datos de clientes empresariales en una base de datos de administración de la relación con los clientes (CRM) y desea cargarlos en Experience Cloud.
* Si desea utilizar datos CRM para un análisis más profundo en Analytics, o como criterio de segmentación en Adobe Target.

**[Audience Analytics](/help/integrate/c-audience-analytics/mc-audiences-aam.md)** debe usarse:

* Si quiere incorporar datos de audiencia de Adobe Audience Manager (AAM), como información demográfica (p. ej., sexo o nivel de ingresos), información psicográfica (p. ej., intereses y aficiones), datos CRM o datos de impresión publicitaria a cualquier flujo de trabajo de Analytics.
* Si desea que los datos CRM cargados estén basados en el tiempo, ya que esta integración envía nueva información a Analytics visita tras visita.

## Exportación de datos desde Adobe Analytics {#export}

El **[Report Builder](/help/analyze/report-builder/home.md)** debe usarse:

* Si las opciones de diseño personalizadas del Workspace son limitadas (el Report Builder permite realizar cualquier personalización dentro de los límites de Excel).
* Para vincular de forma temporal entradas de usuario o fuentes de datos sin conexión (impresiones, costo) con los datos de Adobe. Una solución más permanente para vincular datos son las Fuentes de datos (consulte Importación de datos en Analytics).
* Para combinar datos de diferentes informes dimensionales (por ejemplo, un informe de impresiones de promociones unido a un informe de clic a conversión de promociones).
* Combinar datos de diferentes grupos de informes, ya sea sumándolos o mostrándolos en la misma tabla uno al lado del otro.
* Si desea usar la automatización mediante la programación (XLSX, XLSM, CSV, PDF, TXT, XML, MHT).

**[El Data Warehouse](/help/export/data-warehouse/data-warehouse.md)** debe usarse para:

* Para acceder a variables que no se muestran en la interfaz de usuario (como Dirección IP, Experience Cloud ID, ID de visitante de Analytics, URL de página).
* Para acceder a datos más granulares de los que están disponibles en la interfaz de usuario (vista de tabla no normalizada).
* Para descargar datos en un formato adecuado para una entrada de tabla dinámica.
* Si el cliente desea introducir datos de Adobe en una herramienta de visualización de datos de terceros (resumidos ligeramente y que no sean de nivel de visita).
* Para acceder a todos los elementos de dimensión únicos si aparece “Poco tráfico” en Adobe Analytics.

Se debe usar la **[Fuente de datos de Analytics:](/help/export/analytics-data-feed/c-df-contents/datafeeds-contents.md)**

* Para usar la fuente de datos más granular disponible (ID de visitante, visita).
* Si el cliente desea almacenar los datos de Adobe en una base de datos del lado del cliente, con el nivel más granular que podemos enviar.
* Si el cliente desea desarrollar una herramienta de inteligencia empresarial (BI) o especificar datos de Adobe de nivel de visita en una herramienta de terceros.

Las **[API de informes](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/reporting-guide.md)** deben usarse cuando el resto de las opciones de visualización no satisfagan sus necesidades. Estas son las tres opciones de la API:

* **Procesamiento total**: cuando desea usar datos con funciones avanzadas (como visitas, visitantes y segmentos). Son datos resumidos típicos de la interfaz de usuario de Analytics que están disponibles en ~30-90 minutos. Se puede usar mediante el Report Builder.
* **Tiempo real:** si desea ver unas pocas métricas y dimensiones con segundos de latencia. Son datos resumidos limitados y procesados parcialmente que están disponibles en ~30 segundos. Se incluyen algoritmos únicos de los más populares, ganadores y perdedores. Se puede usar mediante el Report Builder.
* **[!UICONTROL Emisión en directo]**: Si desea un flujo de datos de Analytics de nivel de visita procesados parcialmente pocos segundos después de su recopilación. Son datos procesados parcialmente que están disponibles en ~30 segundos. Solo está disponible para Analytics Premium. Necesita otra forma de visualizar los datos (normalmente, mediante una participación de los Servicios de ingeniería).

## Soluciones personalizadas {#custom-solutions}

Los Servicios de ingeniería deben usarse cuando:

* El resto de las herramientas de Adobe no se adaptan a sus necesidades.
* Desea obtener una experiencia personalizada.
* Desea una solución completamente automatizada.
* Desea alcanzar a un gran número de dispositivos.
* Tiene varias fuentes de datos.
* Tiene requisitos de ETL (extracción, transformación y carga) de datos complejos.
* Desea implementar una personalización de marca.
* Desea visualizar la [!UICONTROL emisión en directo de Analytics].

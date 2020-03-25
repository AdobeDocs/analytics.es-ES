---
description: Esta página de ayuda contiene casos de uso recomendados para cada herramienta de Adobe Analytics. Las herramientas deben considerarse en el orden en que aparecen en la lista. Si una determinada herramienta no satisface las necesidades, pase a la siguiente para su consideración.
title: ¿Qué herramienta de Adobe Analytics debo usar?
uuid: 1179e49d-3cfc-4abd-a8eb-35c5ae380c16
translation-type: tm+mt
source-git-commit: f7125e6845a653ca3d4dd3f1313d1b39f564459c

---


# ¿Qué herramienta de Adobe Analytics debo usar?

Esta página de ayuda contiene casos de uso recomendados para cada herramienta de Adobe Analytics. Las herramientas deben considerarse en el orden en que aparecen en la lista. Si una determinada herramienta no satisface las necesidades, pase a la siguiente para su consideración.

Para obtener más información sobre comparativas de producto de Adobe Analytics, diríjase [aquí](/help/admin/c-analytics-product-comparison/analytics-product-comparison.md).

## Interfaz de usuario de informes de Adobe Analytics {#section_8265460EBB47405AB19A3B2B0729C8A4}

**[Analysis Workspace](/help/analyze/analysis-workspace/analysis-workspace-features.md)**debe ser la interfaz de usuario de referencia para todas sus necesidades de informe y análisis. Adobe continúa invirtiendo en el lanzamiento de actualizaciones mensuales de este producto. Si hay una tarea que no puede realizar en Analysis Workspace, evalúe las otras interfaces que aparecen a continuación.**

**[Reports &amp; Analytics](/help/analyze/reports-analytics/overview/report-overview.md)**debe usarse:

* Por parte de los usuarios principiantes que necesitan acceso a los informes predefinidos que son más fáciles de explorar.
* Para comprender el alza y la confianza de la actividad de Destinatario (Analytics para Destinatario/A4T).
* Para acceder a los datos en tiempo real en la interfaz de usuario.
* Para configurar eventos de calendario.
* Para configurar Destinatarios.
* vista del sistema de informes de bots.
* Para acceder a visualizaciones de vídeo únicas del visor simultáneo, partición de días de vídeo y menú desplegable de visor.
* Para aprovechar las Listas de publicación en el sistema de informes programado.

La **[interfaz de usuario de Mobile Services](https://docs.adobe.com/content/help/en/mobile-services/using/home.html)**debe usarse:

* Si desea una vista siloed de datos de aplicaciones móviles.
* Para administrar la implementación del SDK de la aplicación móvil.
* Para configurar la publicidad móvil, como la mensajería en la aplicación, la mensajería push y el direccionamiento de ubicación.
* Si desea realizar visualizaciones más interactivas para los datos de la aplicación (destello solar).
* Para visualizar puntos de interés en un mapa.
* Para métricas de valor de duración.

Los **[Ad Hoc Analysis](/help/analyze/ad-hoc-analysis/adhoc-home.md)**deben usarse:

* Para exportar 50.000 filas de datos
* Si se desea organizar por tabuladores el trabajo del proyecto.
* Para utilizar el informe Análisis del sitio (informe de rutas 3D).

El **[Data Workbench](https://docs.adobe.com/content/help/en/data-workbench/using/home.html)**debe usarse:

* Como la opción de herramienta de Analytics más flexible (hasta la análisis de nivel de visita individual de nivel de visitante).
* Para crear un conjunto de datos de varios canales de interacciones en línea y sin conexión desde CRM hasta POS y Web.
* Para atribución avanzada (modelos algorítmicos y basados en reglas).
* Para modelos predictivos y estadísticos (puntuación de tendencia, agrupación en clúster, correlaciones, etc.).
* Para la análisis de latencia (tiempo antes/desde un evento).
* Para la identificación y exportación de segmentos complejos en Adobe Experience Cloud.

## Importación de datos en Adobe Analytics {#section_B42B998D6E3E4357B024AEFA4EC69A23}

**[Las clasificaciones](/help/components/c-classifications2/c-classifications.md)**deben usarse:

* Cuando hay metadatos que desea asociar a un valor recopilado (eVar, prop, canal de marketing)
* Opciones:

   * Generador de reglas: se utiliza cuando se recopilan valores con formato predecibles para una variable, por ejemplo, valores delimitados. Este enfoque le permite configurar reglas una vez y en gran medida &quot;configurarlas y olvidarlas&quot;.
   * Importación del explorador: Úsela cuando no tenga valores predecibles o cuando tenga una lista de valores limitada que requiera una actualización única. Para este enfoque es necesario supervisar de forma continuada las clasificaciones para identificar nuevos valores.

Las **[Fuentes de datos](/help/import/c-data-sources/datasrc-home.md)**deben usarse:

* Cuando hay datos sin conexión que desea escribir de forma permanente en Adobe Analytics
* Opciones:

   * Resumen: cargas de datos simples, por día o dimensiones limitadas
   * ID de transacción: cargas de datos que conectan un punto final en línea con datos sin conexión y asocian completamente los datos importados a una instantánea de visitante capturada en línea (por ejemplo, pedidos completados en línea y devueltos sin conexión)
   * Procesamiento completo: fuentes de datos con marca de hora, procesadas como si se tratara de una visita recopilada por los servidores de Adobe. Es decir, los datos se insertan directamente en el viaje de visitante.

Los **[Data Connectors](https://www.adobeexchange.com/experiencecloud.html)(anteriormente, Génesis)**deben usarse:

* Cuando interactúa con un proveedor de terceros que ha creado una conexión compatible con Adobe Analytics. Los Conectores de datos suelen incorporar datos de nivel de resumen a Adobe Analytics de forma permanente y automática, de forma periódica.

La **[API de inserción de datos](https://marketing.adobe.com/developer/documentation/data-insertion/c-data-insertion-api)**debe usarse:

* Cuando sea necesario cargar datos en Adobe Analytics y no sea posible utilizar Adobe AppMeasurement o el código del SDK móvil.

**[Los atributos del cliente](/help/components/c-variables/dimensionslist/reports-customer-attributes.md)**deben usarse:

* Si captura datos de clientes empresariales en una base de datos de administración de la relación con los clientes (CRM) y desea cargar los datos en Experience Cloud.
* Si desea utilizar datos CRM para una análisis más profunda en Analytics o como criterios de objetivo en Adobe Destinatario.

**[Audience Analytics](/help/integrate/c-audience-analytics/mc-audiences-aam.md)**debe usarse:

* Si desea incorporar datos de audiencia de Adobe Audiencia Manager (AAM), como información demográfica (por ejemplo, sexo o nivel de ingresos), información psicográfica (por ejemplo, intereses y aficiones), datos CRM o datos de impresiones de publicidad en cualquier flujo de trabajo de Analytics.
* Si desea que los datos de CRM cargados se basen en el tiempo, porque esta integración envía nueva información a las visitas de Analytics.

## Exportación de datos desde Adobe Analytics {#section_901C06ABF2014E92B2952906723DF235}

El **[Report Builder](/help/analyze/report-builder/home.md)**debe usarse:

* Si las opciones de diseño personalizadas del Workspace son limitadas (el Report Builder permite realizar cualquier personalización dentro de los límites de Excel).
* Para vincular de forma flexible las entradas de usuario o las fuentes de datos sin conexión (impresiones, costo) a los datos de Adobe. La solución más permanente para enlazar datos son las fuentes de datos (consulte Importación de datos a Analytics).
* Para combinar datos de diferentes informes dimensionales (por ejemplo: informe de impresiones de promoción junto con informe de conversión a clic de promoción).
* Para vistas entre grupos de informes.
* Si desea la automatización mediante programación (XLSX, XLSM, CSV, PDF, TXT, XML, MHT).

**[El Data Warehouse](/help/export/data-warehouse/data-warehouse.md)**debe usarse para:

* Para acceder a variables que no se muestran en la interfaz de usuario (como Dirección IP, Experience Cloud ID, ID de visitante de Analytics, URL de página).
* Para acceder a datos más granulares que la IU (vista de tabla desnormalizada)
* Para descargar datos en un formato adecuado para una entrada de tabla dinámica
* Si el cliente desea introducir datos de Adobe en una herramienta de visualización de datos de terceros (resumidos ligeramente y no en el nivel de visita individual)
* Para acceder a todos los valores de dimensión únicos si aparece “Poco tráfico” en Adobe Analytics.

Se debe usar la **[Fuente de datos de Analytics](/help/export/analytics-data-feed/c-df-contents/datafeeds-contents.md)**:

* Para utilizar la fuente de datos más granular que podemos proporcionar (ID de visitante, visita).
* Si el cliente desea que los datos de Adobe se almacenen en una base de datos del lado del cliente, en el nivel más granular que podemos enviar.
* Si el cliente desea desarrollar una herramienta de inteligencia empresarial (BI) o introducir datos de Adobe de nivel de visita en una herramienta de terceros.

Las **[API de informes](https://marketing.adobe.com/developer/get-started/introduction/c-introduction)**deben usarse cuando el resto de las opciones de visualización no satisfagan sus necesidades. Las 3 opciones de API incluyen:

* **Procesamiento** completo: cuando desee datos con muchas funciones (incluidas visitas, visitantes y segmentos). Se trata de datos resumidos típicos de la interfaz de usuario de Analytics, disponibles en ~30-90 minutos. Se puede utilizar a través del Creador de informes.
* **Tiempo** real: cuando desee vista de algunas métricas y dimensiones con segundos de latencia. Se trata de datos resumidos limitados, parcialmente procesados y disponibles en ~30 segundos. Incluye algoritmos únicos de los más populares, ganadores y perdedores. Se puede utilizar a través del Creador de informes.
* **[!UICONTROL Live Stream]**:: cuando desee un flujo de datos de Analytics de nivel de visita procesados parcialmente pocos segundos después de la recopilación. Se trata de datos parcialmente procesados, disponibles en ~30 segundos. Disponible solo para Analytics Premium. Requiere alguna forma de visualizar los datos, generalmente mediante una participación de los servicios de ingeniería.

## Soluciones personalizadas {#section_4A212F26A15947599DFB0399A0440CB6}

Los Servicios de ingeniería deben usarse cuando:

* El resto de las herramientas de Adobe no se adaptan a sus necesidades.
* Desea una experiencia personalizada.
* Desea una solución completamente automatizada.
* Desea llegar a muchos dispositivos.
* Tiene varias fuentes de datos.
* Tiene requisitos de ETL (Extract-Transform-Load) de datos complejos.
* Desea personalizar la marca.
* Desea visualizar [!UICONTROL Analytics Live Stream].

---
description: Esta página de ayuda contiene casos de uso recomendados para cada herramienta de Adobe Analytics. Las herramientas deben considerarse en el orden en que aparecen en la lista. Si una herramienta específica no se adapta a sus necesidades, continúe con la siguiente herramienta.
title: ¿Qué herramienta de Adobe Analytics debo usar?
feature: Analytics Basics
exl-id: d65575df-19c6-4129-89c8-d36de7bb6b2f
TQID: https://experienceleague.adobe.com/xk485fKU7Q2DeZIYaTtN-a4JKnyVamAygW03z7ffAOk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: a421fb65-2c82-457a-921c-28c46b697a39
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: c2ae876122715b4fa6367326dc23479dd9648021
workflow-type: tm+mt
source-wordcount: 1175
ht-degree: 98%

---

# ¿Qué herramienta de Adobe Analytics debo usar?

Esta página de ayuda contiene casos de uso recomendados para cada herramienta de Adobe Analytics. Las herramientas deben considerarse en el orden en que aparecen en la lista. Si una herramienta específica no se adapta a sus necesidades, continúe con la siguiente herramienta.

Para obtener más información sobre comparaciones de productos de Adobe Analytics, consulte [Comparación de productos de Analytics](/help/analyze/get-started/analytics-product-comparison.md).


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Comparación de herramientas](https://video.tv.adobe.com/v/27220?quality=12&learn=on){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]


## Interfaces de usuario de creación de informes de Adobe Analytics {#user-interfaces}

**[Analysis Workspace](/help/analyze/analysis-workspace/home.md)** debe ser la interfaz de usuario de referencia para todas sus necesidades de informe y análisis. Adobe continúa invirtiendo en el lanzamiento de actualizaciones mensuales de este producto. Si hay una tarea que no puede realizar en Analysis Workspace, evalúe las otras interfaces que aparecen a continuación.**

**[Paneles de Adobe Analytics](/help/analyze/mobile-app/home.md)** permite que los usuarios accedan mediante dispositivos móviles a informes de valoración intuitivos. Los informes de valoración son un conjunto de métricas clave y de otros componentes que se presentan en un diseño en mosaico. Los mosaicos se pueden pulsar para obtener desgloses e informes de tendencias más detallados. La aplicación móvil es compatible con los sistemas operativos iOS y Android.

**[Report Builder](/help/analyze/report-builder/rb-overview.md)** es un complemento para Microsoft Excel que se ejecuta en Mac, Windows y exploradores web. Le permite generar solicitudes personalizadas a partir de datos de Adobe Analytics, que se pueden insertar en sus hojas de cálculo de Excel. Las solicitudes pueden hacer referencia de forma dinámica a las celdas de las hojas de cálculo y es posible actualizar y personalizar el modo en el que Report Builder presenta los datos.

**[Report Builder heredado](/help/analyze/legacy-report-builder/home.md)** es un complemento para Microsoft Excel que se ejecuta solamente en Windows. Le permite generar solicitudes personalizadas a partir de datos de Adobe Analytics, que se pueden insertar en sus hojas de cálculo de Excel. Las solicitudes pueden hacer referencia de forma dinámica a las celdas de las hojas de cálculo y es posible actualizar y personalizar el modo en el que Report Builder presenta los datos.

**[Activity Map](/help/analyze/activity-map/overview.md)** es una funcionalidad de Adobe Analytics que proporciona una representación visual de la participación del usuario en páginas web y aplicaciones móviles. Permite a los especialistas en marketing y a los analistas realizar un seguimiento y analizar las interacciones del usuario, como los clics, los desplazamientos de ratón y el comportamiento de desplazamiento.

## Importación de datos en Adobe Analytics {#import}

**[Las clasificaciones](/help/components/classifications/classifications-overview.md)** deben usarse con lo siguiente:

* Cuando hay metadatos que desea asociar a un valor recopilado (eVar, prop, canal de marketing). Adobe recomienda utilizar [Conjuntos de clasificación](/help/components/classifications/sets/overview.md). La clasificación del generador de reglas y el importador de clasificaciones son métodos heredados para introducir los datos de clasificación en Adobe Analytics.

Las **[Fuentes de datos](/help/import/data-sources/overview.md)** deben usarse:

* Cuando hay datos sin conexión que desea escribir de forma permanente en Adobe Analytics.
* Opciones:
   * Resumen: cargas de datos sencillas, por día o de dimensiones limitadas.
   * ID de transacción: cargas de datos que conectan un extremo en línea a datos sin conexión y que asocian por completo los datos importados a una instantánea de visitante capturada en línea (por ejemplo, pedidos completados en línea y devueltos sin conexión).

**[Integraciones de Adobe Exchange](https://www.adobeexchange.com/experiencecloud.html)** debe usarse:

* Al interactuar con un proveedor ajeno que dispone de una conexión compatible con Adobe Analytics. Las aplicaciones de integración suelen incorporar en Adobe Analytics datos en el nivel de resumen de manera permanente, automática y recurrente.

**[API de inserción de datos en lotes](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)**

* La API de inserción de datos en lotes acepta archivos con formato CSV que contienen datos de evento, un evento por fila. Adobe recomienda utilizar la API de inserción de datos en lotes para cualquier implementación que requiera código del lado del servidor o que no pueda utilizar AppMeasurement o SDK web para la recopilación de datos.

La **[API de inserción de datos (heredada)](/help/import/c-data-insertion-api/c-data-insertion-api.md)** debe usarse:

* Cuando necesite introducir datos en Adobe Analytics y no pueda utilizar AppMeasurement, SDK web o la API de inserción de datos en lotes.

Deben usarse **[atributos del cliente](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html?lang=es)**:

* Si captura los datos del cliente empresarial en una base de datos de administración de la relación con los clientes (CRM) y desea cargar los datos en CX Enterprise.
* Si desea utilizar datos CRM para un análisis más profundo en Analytics, o como criterio de segmentación en Adobe Target.

**[Audience Analytics](/help/integrate/c-audience-analytics/mc-audiences-aam.md)** debe usarse:

* Si quiere incorporar datos de público de Adobe Audience Manager, como la información demográfica (p. ej., género o nivel de ingresos), la información psicográfica (p. ej., intereses y aficiones), los datos CRM o los datos de impresión publicitaria a cualquier flujo de trabajo de Analytics.
* Si desea que los datos CRM cargados estén basados en el tiempo, ya que esta integración envía nueva información a Analytics visita tras visita.

## Exportación de datos desde Adobe Analytics {#export}

El **[Report Builder](/help/analyze/report-builder/rb-overview.md)** debe usarse:

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

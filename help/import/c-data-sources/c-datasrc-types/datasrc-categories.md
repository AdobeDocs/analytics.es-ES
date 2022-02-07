---
description: Las categorías de fuentes de datos identifican diferentes tipos de fuentes datos que ofrecen una funcionalidad similar.
subtopic: Data sources
title: Resumen de los tipos de datos y las categorías
topic-fix: Developer and implementation
uuid: b5004cdc-b68a-4a82-a159-a7cd7b8bfe21
exl-id: d459fd06-a0fe-49e6-8624-b42f0c60ee6e
source-git-commit: 0b31585f5a928d68083764b80f3a08927b407387
workflow-type: ht
source-wordcount: '903'
ht-degree: 100%

---

# Resumen de los tipos de datos y las categorías

Las categorías de fuentes de datos identifican diferentes tipos de fuentes datos que ofrecen una funcionalidad similar.

Las categorías ofrecen un modo de agrupar las fuentes de datos según la perspectiva del usuario. Para crear una fuente de datos a través de la interfaz de usuario de [!DNL Data Sources] correspondiente, primero se selecciona una categoría de fuentes de datos y después un tipo específico de fuente de datos. Cada categoría contiene tipos de fuentes de datos que admiten tipos de datos similares. [!DNL Data Sources] proporciona las siguientes categorías de fuentes de datos:

## Uso del sitio web {#web-usage}

| Fuente de datos | Tipo de procesamiento | Descripción |
| --- | --- | --- |
| [!UICONTROL Archivos de registro del servidor web] | [Registro web](/help/import/c-data-sources/c-datasrc-types/datasrc-web-log.md) | La mayoría de los servidores web genera archivos de registro donde se asienta cada página que se solicita al servidor. El uso de esta fuente de datos permite procesar los archivos de registro de la mayoría de los servidores web y agregarlos a los informes. |
| [!UICONTROL Carga por lotes de Advertising Cloud] | [Conversión](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Ofrece cargas por lotes, tanto manuales como automatizadas con Excel.[!DNL Advertising Cloud] |
| [!UICONTROL Fuente de datos de tráfico de nivel de sitio] | [Tráfico](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md) | Importa datos de tráfico de todo el sitio web. Por ejemplo, [!UICONTROL vistas de páginas]. |
| [!UICONTROL Fuente de datos del tráfico desglosados] | [Tráfico](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md) | Importa datos del tráfico desglosados por otra variable del sitio web. Por ejemplo, [!UICONTROL Vistas de páginas] desglosadas por [!UICONTROL Producto]. |

## Campañas de publicidad {#ad-campaigns}

| Fuente de datos | Tipo de procesamiento | Descripción |
| --- | --- | --- |
| [!UICONTROL Servidor de publicidad genérico] | [Conversión](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Permite integrar desde el servidor de publicidad a informes de marketing métricas sobre impresiones y otras métricas de primera línea sobre las actividades de los servicios de publicidad. Es la fuente de datos genérica para servidores de publicidad; utilice esta fuente si no hay otra fuente compatible con el servidor de publicidad específico. |
| [!UICONTROL Servidor de campaña de correo electrónico genérico] | [Conversión](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Permite integrar en informes de marketing métricas provenientes del servidor de campañas de correo electrónico.  Algunas métricas que suelen incorporarse son las cantidades de mensajes enviados, recibidos y leídos. Es la fuente de datos genérica para servidores de campañas por correo electrónico; utilice esta fuente si no hay otra fuente compatible con el servidor de campañas por correo electrónico específico. |
| [!UICONTROL Servicio de pago por clic genérico] | [Conversión](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Permite importar datos sobre rendimiento de pago por clic, incluidos datos como impresiones, clics y costes.  Es la fuente de datos genérica para datos de pago por clic; utilice esta fuente si no hay otra fuente compatible con el servicio pago por clic específico. |

## Administración de la relación con los clientes (CRM) {#crm}

| Fuente de datos | Tipo de procesamiento | Descripción |
| --- | --- | --- |
| [!UICONTROL Centro de llamadas genérico] | [Conversión](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Permite integrar en informes de marketing información sobre centros de llamadas. Las métricas que se importan con más frecuencia incluyen la cantidad y duración de las llamadas, el agente y el total de ventas.  Es la fuente de datos genérica para centros de llamadas. Utilícela si no hay otra fuente compatible con el software específico del centro de llamadas. |
| [!UICONTROL Aplicación genérica del soporte técnico del cliente] | [Conversión](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Permite integrar en informes de marketing información proveniente del software de asistencia al cliente. Incluye métricas tales como la cantidad de incidentes nuevos, la cantidad de incidentes resueltos y el tiempo empleado para resolverlos.  Es la fuente de datos genérica para datos de aplicaciones de asistencia al cliente; utilice esta fuente si no hay otra fuente compatible con la aplicación específica. |

## Satisfacción del cliente {#csat}

| Fuente de datos | Tipo de procesamiento | Descripción |
| --- | --- | --- |
| [!UICONTROL Datos genéricos de encuesta] | [Conversión](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Permite integrar en informes de marketing resultados de encuestas creadas con herramientas de otras empresas, para mostrar la satisfacción general de los clientes con la interacción con el sitio.  Es la fuente de datos genérica para datos de encuestas; utilice esta fuente si no hay otra fuente compatible con el servicio de encuestas específico. |

## Rendimiento del sitio {#performance}

| Fuente de datos | Tipo de procesamiento | Descripción |
| --- | --- | --- |
| [!UICONTROL Velocidad de descarga del sitio genérico] | [Conversión](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Permite integrar sus datos con los datos de aplicaciones o servicios que hagan un seguimiento de la velocidad de las descargas. Es la fuente de datos genérica para datos de velocidad de descarga; utilice esta fuente si no hay otra fuente compatible con el software o servicio de datos de velocidad específico. |

## Genéricas {#generic}

| Fuente de datos | Tipo de procesamiento | Descripción |
| --- | --- | --- |
| [!UICONTROL Fuente de datos genérica (solo datos de resumen)] | [Conversión](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Utilice esta fuente de datos cuando no haya otra que coincida más con el tipo de datos que desea importar a informes y análisis de marketing. |
| [!UICONTROL Fuente de datos genérica (procesamiento completo)] | Procesamiento completo | Adobe dejó de utilizar las fuentes de datos de procesamiento completo el 31 de enero de 2022. [Más información](/help/import/c-data-sources/c-datasrc-types/datasrc-fullproc-eol.md). Adobe recomienda usar la [API de inserción de datos en lote (BDIA)](https://www.adobe.io/apis/experiencecloud/analytics/docs.html?lang=es) en su lugar. |
| [!UICONTROL Fuente de datos genérica (ID de transacción)] | <ul><li>ID de transacción</li><li>ID de visitante</li></ul> | Permite vincular cualquier evento que se produce sin conexión con otro que se produce con conexión. El [!UICONTROL ID de transacción] actúa como una clave que vincula los eventos sin conexión con los eventos en línea. |

## Compras en línea {#purchases}

| Fuente de datos | Tipo de procesamiento | Descripción |
| --- | --- | --- |
| [!UICONTROL Devoluciones de productos] | [Conversión](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Permite importar datos de devolución de productos para asociarlos con un ID de compra y de ese modo identificar los atributos (tales como motores de búsqueda, palabras clave, campañas, etc.) que se relacionan con una mayor probabilidad de que se produzcan devoluciones. |
| [!UICONTROL Coste de productos] | [Conversión](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Permite obtener el coste real de los productos comprados y enviados desde el sitio web, al asociar el coste o el beneficio con productos individuales, de modo que puede generar informes precisos sobre las campañas, palabras clave y promociones internas del sitio web que generan la mayor rentabilidad. |
| [!UICONTROL Estado de pedidos] | [Conversión](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Permite utilizar métricas para identificar el estado de cada pedido hecho, lo cual incluye pedidos cancelados, enviados, finalizados o considerados fraudulentos. La información de estado de los pedidos permite identificar los métodos de adquisición que generan la mayor cantidad de pedidos finalizados. |

## Posibles clientes y cotizaciones {#leads}

| Fuente de datos | Tipo de procesamiento | Descripción |
| --- | --- | --- |
| [!UICONTROL Generación de posibles clientes] | [Conversión](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Permite cargar información sobre los resultados de cada posible cliente logrado a través del sitio, incluido los ingresos reales generados.  Después de que el ingreso se atribuya con precisión a los ID de los posibles clientes, se podrán identificar las campañas y promociones más rentables. |
| [!UICONTROL Cotización en línea] | [Conversión](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Permite cargar información sobre los resultados de cada posible cliente logrado a través del sitio, incluido los ingresos reales generados.  Después de que el ingreso se atribuya con precisión a los ID de los posibles clientes, se podrán identificar las campañas y promociones más rentables. |
| [!UICONTROL Datos de centro de llamadas] | [Conversión](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Permite cargar transacciones del centro de llamadas para identificar las tácticas (campañas, promociones, etc.). que llevan a que los clientes atiendan el teléfono. |

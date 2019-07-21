---
description: Las categorías de fuentes de datos identifican diferentes tipos de fuentes datos que ofrecen una funcionalidad similar.
seo-description: Las categorías de fuentes de datos identifican diferentes tipos de fuentes datos que ofrecen una funcionalidad similar.
seo-title: Descripción general de los tipos de datos y las categorías
solution: Analytics
subtopic: Fuentes de datos
title: Descripción general de los tipos de datos y las categorías
topic: Desarrollador e implementación
uuid: b 5004 cdc-b 68 a -4 a 82-a 159-a 7 cd 7 b 8 bfe 21
translation-type: tm+mt
source-git-commit: e3b1ac3139f26ca3a97f3d2228276e690ec4cb79

---


# Descripción general de los tipos de datos y las categorías

Las categorías de fuentes de datos identifican diferentes tipos de fuentes datos que ofrecen una funcionalidad similar.

Las categorías ofrecen un modo de agrupar las fuentes de datos según la perspectiva del usuario. Para crear una fuente de datos a través de la interfaz de usuario correspondiente, primero se selecciona una categoría de fuentes de datos y después un tipo específico de fuente de datos. Cada categoría contiene tipos de fuentes de datos que admiten tipos de datos similares. Las fuentes de datos pueden agruparse en las siguientes categorías:

## Uso del sitio web {#section_4BA8D97B6BA848518F21760AE49F41D1}

<table id="table_2562E7A400214B8F9BB9177D210348F4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Fuente de datos </p> </th> 
   <th colname="col2" class="entry"> <p>Tipo de procesamiento </p> </th> 
   <th colname="col3" class="entry"> <p>Descripción </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Archivos de registro del servidor web </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-web-log.md#concept_E25D89C8B90A41FEB7DF4E936CACEE2B" type="concept" format="dita" scope="local"> Registro web </a> </p> </td> 
   <td colname="col3"> <p>La mayoría de los servidores web genera archivos de registro donde se asienta cada página que se solicita al servidor. El uso de esta fuente de datos permite procesar los archivos de registro de la mayoría de los servidores web y agregarlos a los informes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Carga masiva de Marketing Cloud </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0" type="concept" format="dita" scope="local"> Conversión </a> </p> </td> 
   <td colname="col3"> <p>Proporciona cargas masivas manuales y automatizadas de Excel en Advertising Cloud. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Fuente de datos de tráfico de nivel de sitio </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-traffic.md#concept_F50D3AC6A5544D06BB81EF1E279576BC" type="concept" format="dita" scope="local"> Tráfico </a> </p> </td> 
   <td colname="col3"> <p>Importa datos de tráfico de todo el sitio web. Por ejemplo, vistas de páginas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Fuente de datos de tráfico desglosados </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-traffic.md#concept_F50D3AC6A5544D06BB81EF1E279576BC" type="concept" format="dita" scope="local"> Tráfico </a> </p> </td> 
   <td colname="col3"> <p>Importa datos de tráfico desglosados por otra variable del sitio web. Por ejemplo, vistas de páginas por producto. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Campañas de publicidad {#section_9AE27E347CFC48F29E7C1134B6E928A6}

<table id="table_2A297A86CC3E4B1E8B72389AA148549A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Fuente de datos </p> </th> 
   <th colname="col2" class="entry"> <p>Tipo de procesamiento </p> </th> 
   <th colname="col3" class="entry"> <p>Descripción </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Servidor de publicidad genérico </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0" type="concept" format="dita" scope="local"> Conversión </a> </p> </td> 
   <td colname="col3"> <p>Permite integrar desde el servidor de publicidad a informes de marketing métricas sobre impresiones y otras métricas de primera línea sobre las actividades de los servicios de publicidad. Es la fuente de datos genérica para servidores de publicidad; utilice esta fuente si no hay otra fuente compatible con el servidor de publicidad específico. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Servidor de campaña de correo electrónico genérico </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0" type="concept" format="dita" scope="local"> Conversión </a> </p> </td> 
   <td colname="col3"> <p>Permite integrar en informes de marketing métricas provenientes del servidor de campañas de correo electrónico. </p> <p>Algunas métricas que suelen incorporarse son las cantidades de mensajes enviados, recibidos y leídos. Es la fuente de datos genérica para servidores de campañas por correo electrónico; utilice esta fuente si no hay otra fuente compatible con el servidor de campañas por correo electrónico específico. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Servicio de pago por clic genérico </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0" type="concept" format="dita" scope="local"> Conversión </a> </p> </td> 
   <td colname="col3"> <p> Permite importar datos sobre rendimiento de pago por clic, incluidos datos como impresiones, clics y costes.  </p> <p>Es la fuente de datos genérica para datos de pago por clic; utilice esta fuente si no hay otra fuente compatible con el servicio pago por clic específico. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Administración de la relación con los clientes (CRM) {#section_013A1C5D3CAD4CCEAD22C2FDD26715A0}

<table id="table_5895659CAB2C415AB2AA59A2E6C75AD1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Fuente de datos </p> </th> 
   <th colname="col2" class="entry"> <p>Tipo de procesamiento </p> </th> 
   <th colname="col3" class="entry"> <p>Descripción </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Centro de llamadas genérico </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0" type="concept" format="dita" scope="local"> Conversión </a> </p> </td> 
   <td colname="col3"> <p>Permite integrar en informes de marketing información sobre centros de llamadas. Las métricas que se importan con más frecuencia incluyen la cantidad y duración de las llamadas, el agente y el total de ventas. </p> <p>Es la fuente de datos genérica para centros de llamadas; utilice esta fuente si no hay otra fuente compatible con el software específico del centro de llamadas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> </p> <p>Aplicación genérica </p> <p>de asistencia al cliente </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0" type="concept" format="dita" scope="local"> Conversión </a> </p> </td> 
   <td colname="col3"> <p>Permite integrar en informes de marketing información proveniente del software de asistencia al cliente. Incluye métricas tales como la cantidad de incidentes nuevos, la cantidad de incidentes resueltos y el tiempo empleado para resolverlos. </p> <p>Es la fuente de datos genérica para datos de aplicaciones de asistencia al cliente; utilice esta fuente si no hay otra fuente compatible con la aplicación específica. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Satisfacción del cliente {#section_1058CA3860044630B0B06EEDA261DBA2}

<table id="table_3811CA1E2B7C45D7A0CBEC5CE44C11A8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Fuente de datos </p> </th> 
   <th colname="col2" class="entry"> <p>Tipo de procesamiento </p> </th> 
   <th colname="col3" class="entry"> <p>Descripción </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Datos genéricos de encuesta </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0" type="concept" format="dita" scope="local"> Conversión </a> </p> </td> 
   <td colname="col3"> <p>Permite integrar en informes de marketing resultados de encuestas creadas con herramientas de otras empresas, para mostrar la satisfacción general de los clientes con la interacción con el sitio. </p> <p>Es la fuente de datos genérica para datos de encuestas; utilice esta fuente si no hay otra fuente compatible con el servicio de encuestas específico. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Rendimiento del sitio {#section_3A7BECB0B4B247FB991DC59237ECFE1F}

<table id="table_7B623D08275E4FDEADDD85EA89A2B7C7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Fuente de datos </p> </th> 
   <th colname="col2" class="entry"> <p>Tipo de procesamiento </p> </th> 
   <th colname="col3" class="entry"> <p>Descripción </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Velocidad de descarga del sitio genérico </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0" type="concept" format="dita" scope="local"> Conversión </a> </p> </td> 
   <td colname="col3"> <p>Permite integrar sus datos con los datos de aplicaciones o servicios que hagan un seguimiento de la velocidad de las descargas. </p> <p>Es la fuente de datos genérica para datos de velocidad de descarga; utilice esta fuente si no hay otra fuente compatible con el software o servicio de datos de velocidad específico. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Genéricas {#section_9B9A2A9871894B6491032AE1E961629A}

<table id="table_D63A6A00C93A4CD48FEBE7BC24E5DA9F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Fuente de datos </p> </th> 
   <th colname="col2" class="entry"> <p>Tipo de procesamiento </p> </th> 
   <th colname="col3" class="entry"> <p>Descripción </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> </p> <p>Fuente de datos genérica (solo datos de resumen) </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0" type="concept" format="dita" scope="local"> Conversión </a> </p> </td> 
   <td colname="col3"> <p>Utilice esta fuente de datos cuando no haya otra que coincida más con el tipo de datos que desea importar a informes y análisis de marketing. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Fuente de datos genérica (procesamiento completo) </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-full-processing.md#concept_975B1BB9981D49139B4EE09C78CDE6ED" type="concept" format="dita" scope="local"> Procesamiento completo </a> </p> </td> 
   <td colname="col3"> <p>Permite importar datos del archivo de registro. Los datos se procesarán como si fueran recibidos por los servidores de recopilación de datos en el momento especificado (cada visita recibe una fecha y hora de registro). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> </p> <p>Fuente de datos genérica (ID de transacción) </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-transactionid.md#concept_A97302E9EC45468A8F30285FACE8C776" type="concept" format="dita" scope="local"> ID de transacción </a> </p> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-visitorid.md#concept_1CFAA61D57A84B22A41F7A8E0DFCAAB5" type="concept" format="dita" scope="local"> Visitor ID </a> </p> </td> 
   <td colname="col3"> <p>Permite vincular cualquier evento que se produce sin conexión con otro que se produce con conexión. La ID de transacción actúa como una clave que vincula los eventos sin conexión con los eventos en línea. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Compras en línea {#section_2B2D4DBB045548C3A5DC7DEF81BA56D1}

<table id="table_EE450D955D4C4264A40142AF6D74F1AA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Fuente de datos </p> </th> 
   <th colname="col2" class="entry"> <p>Tipo de procesamiento </p> </th> 
   <th colname="col3" class="entry"> <p>Descripción </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Devoluciones de productos </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0" type="concept" format="dita" scope="local"> Conversión </a> </p> </td> 
   <td colname="col3"> <p>Permite importar datos de devolución de productos para asociarlos con una ID de compra y de ese modo identificar los atributos (tales como motores de búsqueda, palabras clave, campañas, etc.) que se relacionan con una mayor probabilidad de que se produzcan devoluciones. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Coste de productos </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0" type="concept" format="dita" scope="local"> Conversión </a> </p> </td> 
   <td colname="col3"> <p>Permite obtener el coste real de los productos comprados y enviados desde el sitio web, al asociar el coste o el beneficio con productos individuales, de modo que puede generar informes precisos sobre las campañas, palabras clave y promociones internas del sitio web que generan la mayor rentabilidad. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Estado de pedidos </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0" type="concept" format="dita" scope="local"> Conversión </a> </p> </td> 
   <td colname="col3"> <p>Permite utilizar métricas para identificar el estado de cada pedido hecho, lo cual incluye pedidos cancelados, enviados, finalizados o considerados fraudulentos. </p> <p>La información de estado de los pedidos permite identificar los métodos de adquisición que generan la mayor cantidad de pedidos finalizados. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Posibles clientes y cotizaciones {#section_0B3EAA59BEC94244BE3EB3825D719DF6}

<table id="table_85B095414F6C4644A191A94AC0CAD13D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Fuente de datos </p> </th> 
   <th colname="col2" class="entry"> <p>Tipo de procesamiento </p> </th> 
   <th colname="col3" class="entry"> <p>Descripción </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Generación de posibles clientes </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0" type="concept" format="dita" scope="local"> Conversión </a> </p> </td> 
   <td colname="col3"> <p>Permite cargar información sobre los resultados de cada posible cliente logrado a través del sitio, incluido los ingresos reales generados. </p> <p>Después de que el ingreso se atribuya con precisión a los ID de los posibles clientes, se podrán identificar las campañas y promociones más rentables. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cotización en línea </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0" type="concept" format="dita" scope="local"> Conversión </a> </p> </td> 
   <td colname="col3"> <p>Permite cargar información sobre los resultados de cada posible cliente logrado a través del sitio, incluido los ingresos reales generados. </p> <p>Después de que el ingreso se atribuya con precisión a los ID de los posibles clientes, se podrán identificar las campañas y promociones más rentables. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Datos de centro de llamadas </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0" type="concept" format="dita" scope="local"> Conversión </a> </p> </td> 
   <td colname="col3"> <p>Permite cargar transacciones del centro de llamadas para identificar las tácticas (campañas, promociones, etc.). que llevan a que los clientes atiendan el teléfono. </p> </td> 
  </tr> 
 </tbody> 
</table>


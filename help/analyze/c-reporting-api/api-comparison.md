---
description: Tabla de comparación para las API de sistema de informes de Analytics. Se proporcionan vínculos a la documentación de apoyo.
title: Comparación de las API de informes de Analytics
uuid: fa533a8e-33c0-42f4-a294-cabee0258c8f
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Comparación de las API de informes de Analytics

Tabla de comparación para las API de sistema de informes de Analytics. Se proporcionan vínculos a la documentación de apoyo.

>[!NOTE] En cuanto a latencia, Analytics para Target (A4T) combina datos de Analytics y Target en la misma visita para generar así informes integrados. Dado que las llamadas de Analytics y Destinatario se producen en momentos diferentes, las visitas se almacenan antes de que se realice ningún procesamiento para recopilar datos de ambas soluciones. Este proceso agrega **una latencia adicional de 7 a 10 minutos** a todos los puntos de comprobación.

<table id="table_7AF4FD678D494063ADF459B3CBC3EF3F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de API </th> 
   <th colname="col2" class="entry"> Procesamiento completo </th> 
   <th colname="col3" class="entry"> Tiempo real </th> 
   <th colname="col4" class="entry"> Livestream </th> 
   <th colname="col5" class="entry"> Data Warehouse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Descripción</b> </td> 
   <td colname="col2"> Datos finalizados y completamente procesados disponibles en todas las interfaces de Analytics. </td> 
   <td colname="col3"> Métricas parcialmente procesadas y limitadas disponibles pocos segundos después de la recopilación. </td> 
   <td colname="col4"> Datos de visitas parcialmente procesados disponibles en segundos después de la recopilación. </td> 
   <td colname="col5"> Datos finalizados y completamente procesados que se utilizan para extraer grandes exportaciones de datos. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://marketing.adobe.com/resources/help/en_US/analytics/whitepapers/analytics-data-availability.pdf"  > Latencia</a> </p> </td> 
   <td colname="col2"> 30-90 Minutos </td> 
   <td colname="col3"> * Segundos -10 minutos </td> 
   <td colname="col4"> Segundos -10 minutos </td> 
   <td colname="col5"> 90 minutos + </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Finalización del procesamiento</b> </td> 
   <td colname="col2"> Completa </td> 
   <td colname="col3"> Parcial </td> 
   <td colname="col4"> Parcial </td> 
   <td colname="col5"> Completa </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <a href="https://marketing.adobe.com/resources/help/es_ES/reference/"  > Interfaces de generación de informes</a> </td> 
   <td colname="col2"> Informes y análisis, Creador de informes, API </td> 
   <td colname="col3"> Informe en tiempo real en Informes y análisis, Creador de informes, API </td> 
   <td colname="col4"> Solo API </td> 
   <td colname="col5"> Almacén de datos y API </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Granularidad de datos</b> </td> 
   <td colname="col2"> Resumido </td> 
   <td colname="col3"> Resumido </td> 
   <td colname="col4"> Nivel de visita </td> 
   <td colname="col5"> Resumido </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Procesamiento de Perfil de Visitante</b> </td> 
   <td colname="col2"> Sí </td> 
   <td colname="col3"> No </td> 
   <td colname="col4"> No </td> 
   <td colname="col5"> Sí  </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Admite segmentos</b> </td> 
   <td colname="col2"> Sí </td> 
   <td colname="col3"> No </td> 
   <td colname="col4"> No </td> 
   <td colname="col5"> Sí (pero solo segmentos compatibles con el almacén de datos) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>SKU de Analytics</b> </td> 
   <td colname="col2"> Estándar+ </td> 
   <td colname="col3"> Estándar+ </td> 
   <td colname="col4"> Inteligencia Premium completa o predictiva </td> 
   <td colname="col5"> Estándar+ </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Documentación</b> </td> 
   <td colname="col2"> <p> <a href="https://marketing.adobe.com/developer/documentation/analytics-reporting-1-4/get-started%E2%80%8B"  > Servicios Web</a> </p> </td> 
   <td colname="col3"> <p> <a href="https://marketing.adobe.com/developer/documentation/analytics-reporting-1-4/real-time"  > Informes en tiempo real</a> </p> </td> 
   <td colname="col4"> <p> <a href="https://marketing.adobe.com/developer/documentation/analytics-live-stream/overview-1%E2%80%8B"  > Información general de emisión en directo</a> </p> </td> 
   <td colname="col5"> <p><a href="https://marketing.adobe.com/resources/help/es_ES/reference/data_warehouse.html"  > Data Warehouse</a> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Ayuda relacionada**

* [Adobe/IO](https://www.adobe.io/) : una fuente completa para la documentación técnica y las herramientas necesarias para integrar las tecnologías de Adobe en sus aplicaciones.
* [API de Consulta de Área de trabajo de datos](https://marketing.adobe.com/developer/documentation/data-workbench-query-api/c-ins-qry-api)


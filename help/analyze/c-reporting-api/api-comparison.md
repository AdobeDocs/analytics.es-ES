---
description: Una tabla comparativa de las API de informes de Analytics. Se incluyen vínculos a documentación de apoyo.
title: Comparación de las API de informes de Analytics
uuid: fa533a8e-33c0-42f4-a294-cabee0258c8f
feature: API
role: Developer
translation-type: tm+mt
source-git-commit: 4359f451692b86087efe27d4b3ec49ca85b7addc
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 100%

---


# Comparación de las API de informes de Analytics

Una tabla comparativa de las API de informes de Analytics. Se incluyen vínculos a documentación de apoyo.

>[!NOTE]
>
>En cuanto a latencia, Analytics para Target (A4T) combina datos de Analytics y Target en la misma visita para generar así informes integrados. Dado que las llamadas de Analytics y Target se producen en momentos diferentes, las visitas se almacenan antes de procesarse para poder recopilar datos de las dos soluciones. Este proceso añade **de 7 a 10 minutos más** de latencia a todos los puntos de comprobación.

<table id="table_7AF4FD678D494063ADF459B3CBC3EF3F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de API </th> 
   <th colname="col2" class="entry"> Procesamiento total </th> 
   <th colname="col3" class="entry"> Tiempo real </th> 
   <th colname="col4" class="entry"> Livestream </th> 
   <th colname="col5" class="entry"> Data Warehouse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Descripción</b> </td> 
   <td colname="col2"> Datos totalmente procesados y finalizados disponibles en todas las interfaces de Analytics. </td> 
   <td colname="col3"> Métricas parcialmente procesadas y limitadas disponibles unos segundos después de recopilarse. </td> 
   <td colname="col4"> Datos de visitas parcialmente procesados disponibles unos segundos después de recopilarse. </td> 
   <td colname="col5"> Datos totalmente procesados y finalizados que se utilizan para extraer exportaciones de datos de gran volumen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://docs.adobe.com/content/help/es-ES/analytics/technotes/latency.html"  > Latencia</a> </p> </td> 
   <td colname="col2"> De 30 a 90 minutos </td> 
   <td colname="col3"> * De segundos a 10 minutos </td> 
   <td colname="col4"> De segundos a 10 minutos </td> 
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
   <td colname="col1"> <a href="https://docs.adobe.com/content/help/es-ES/analytics/landing/home.html"  > Interfaces de generación de informes</a> </td> 
   <td colname="col2"> Analysis Workspace, Reports &amp; Analytics, Report Builder, API </td> 
   <td colname="col3"> Real-time report in Reports &amp; Analytics, Report Builder, 1.4 API </td> 
   <td colname="col4"> Solo API </td> 
   <td colname="col5"> Data Warehouse y API </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Granularidad de los datos</b> </td> 
   <td colname="col2"> Resumida </td> 
   <td colname="col3"> Resumida </td> 
   <td colname="col4"> Nivel de visita </td> 
   <td colname="col5"> Resumida </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Procesamiento de perfiles del visitante</b> </td> 
   <td colname="col2"> Sí </td> 
   <td colname="col3"> No </td> 
   <td colname="col4"> No </td> 
   <td colname="col5"> Sí </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Admite segmentos</b> </td> 
   <td colname="col2"> Sí </td> 
   <td colname="col3"> No </td> 
   <td colname="col4"> No </td> 
   <td colname="col5"> Sí (pero solo segmentos compatibles con el Data Warehouse) </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <b>Documentación</b> </td> 
   <td colname="col2"> <p> <a href="https://www.adobe.io/apis/experiencecloud/analytics/docs.html"  > API de Analytics</a> </p> </td> 
   <td colname="col3"> <p> <a href="https://github.com/AdobeDocs/analytics-1.4-apis"  > Informes en tiempo real</a> </p> </td> 
   <td colname="col4"> <p> <a href="https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md"  > Información general de emisión en directo</a> </p> </td> 
   <td colname="col5"> <p><a href="https://docs.adobe.com/content/help/es-ES/analytics/export/data-warehouse/data-warehouse.html"  > Data Warehouse</a> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Ayuda relacionada**

* [Adobe/IO](https://www.adobe.io/): una fuente exhaustiva de documentación técnica y herramientas necesarias para integrar las tecnologías de Adobe en sus aplicaciones.
* [API de consulta del Data Workbench](https://marketing.adobe.com/developer/documentation/data-workbench-query-api/c-ins-qry-api)


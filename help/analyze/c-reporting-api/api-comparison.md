---
description: Una tabla comparativa de las API de informes de Analytics. Se incluyen vínculos a documentación de apoyo.
seo-description: Una tabla comparativa de las API de informes de Analytics. Se incluyen vínculos a documentación de apoyo.
seo-title: Comparación de las API de informes de Analytics
solution: Analytics
title: Comparación de las API de informes de Analytics
uuid: fa 533 a 8 e -33 c 0-42 f 4-a 294-cabee 0258 c 8 f
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Comparación de las API de informes de Analytics

Una tabla comparativa de las API de informes de Analytics. Se incluyen vínculos a documentación de apoyo.

>[!NOTE]
>
>Con respecto a la latencia, Analytics para Target (A 4 T) combina datos de Analytics y Target en la misma visita para crear informes integrados. Dado que las llamadas de Analytics y Target se producen en momentos diferentes, las visitas se almacenan antes de procesarse para poder recopilar datos de las dos soluciones. Este proceso añade **de 7 a 10 minutos más** de latencia a todos los puntos de comprobación.

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
   <td colname="col1"> <p><a href="https://marketing.adobe.com/resources/help/en_US/analytics/whitepapers/analytics-data-availability.pdf" format="https" scope="external"> Latencia</a> </p> </td> 
   <td colname="col2"> De 30 a 90 minutos </td> 
   <td colname="col3"> * De segundos a 10 minutos </td> 
   <td colname="col4"> De segundos a 10 minutos </td> 
   <td colname="col5"> + de 90 minutos </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Finalización del procesamiento</b> </td> 
   <td colname="col2"> Completa </td> 
   <td colname="col3"> Parcial </td> 
   <td colname="col4"> Parcial </td> 
   <td colname="col5"> Completa </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <a href="https://marketing.adobe.com/resources/help/en_US/reference/" format="https" scope="external"> Interfaces de generación de informes</a> </td> 
   <td colname="col2"> Reports &amp; Analytics, Report Builder, API </td> 
   <td colname="col3"> Informe en tiempo real en Reports &amp; Analytics, Report Builder, API </td> 
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
   <td colname="col1"> <b>Identificadores SKU de análisis</b> </td> 
   <td colname="col2"> Standard+ </td> 
   <td colname="col3"> Standard+ </td> 
   <td colname="col4"> Premium Complete o Predictive Intelligence </td> 
   <td colname="col5"> Standard+ </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Documentación</b> </td> 
   <td colname="col2"> <p> <a href="https://marketing.adobe.com/developer/documentation/analytics-reporting-1-4/get-started%E2%80%8B" format="https" scope="external"> Servicios Web</a> </p> </td> 
   <td colname="col3"> <p> <a href="https://marketing.adobe.com/developer/documentation/analytics-reporting-1-4/real-time" format="https" scope="external"> Informes en tiempo real</a> </p> </td> 
   <td colname="col4"> <p> <a href="https://marketing.adobe.com/developer/documentation/analytics-live-stream/overview-1%E2%80%8B" format="https" scope="external"> Información general de emisión en directo</a> </p> </td> 
   <td colname="col5"> <p><a href="https://marketing.adobe.com/resources/help/en_US/reference/data_warehouse.html" format="https" scope="external"> Data Warehouse</a> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Ayuda relacionada**

* [Adobe/IO](https://www.adobe.io/): una fuente exhaustiva de documentación técnica y herramientas necesarias para integrar las tecnologías de Adobe en sus aplicaciones.
* [API de consulta del Data Workbench.](https://marketing.adobe.com/developer/documentation/data-workbench-query-api/c-ins-qry-api)


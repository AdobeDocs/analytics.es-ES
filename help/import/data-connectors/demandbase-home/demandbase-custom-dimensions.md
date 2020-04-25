---
description: Enumera los identificadores de dimensión opcionales que se pueden proporcionar en el paso 4 del asistente de integración de Adobe.
title: Dimensiones personalizadas de Demandbase
uuid: d1621046-3aa2-46b9-a536-4a8fb792b69f
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Dimensiones personalizadas de Demandbase {#demandbase-custom-dimensions}

Enumera los identificadores de dimensión opcionales que se pueden proporcionar en el paso 4 del asistente de integración de Adobe.

Si no está seguro del ID de API exacto para entrar en el asistente, consúltelo con su representante de Demandbase.

>[!IMPORTANT]
>
>Se recomienda NO incluir la dirección IP como dimensión personalizada. El número extremadamente alto de valores únicos puede causar problemas de rendimiento con los informes. Además, la dirección IP ya se ofrece como una opción de informes a través de la creación de informes de Adobe Data Warehouse.

<table id="table_3B44A18BE5FE45BC83389F89B48D9B97"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dimensión </th> 
   <th colname="col2" class="entry"> ID de API </th> 
   <th colname="col3" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ISP </td> 
   <td colname="col2"> ISP </td> 
   <td colname="col3"> Indica si la organización identificada está clasificada como ISP. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Alias de marketing </td> 
   <td colname="col2"> marketing_alias </td> 
   <td colname="col3"> Nombre de organización identificativo o abreviado (32 caracteres o menos) para su uso en anuncios, mensajes o copias de marketing. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Etiquetas de observación de cuenta </td> 
   <td colname="col2"> watch_list (personalizada) </td> 
   <td colname="col3">Conjunto ilimitado de etiquetas definidas por el cliente que pueden añadirse a sus datos de respuesta de API, por organización. <p><b>Ejemplo</b>: si tiene una etiqueta de observación llamada Target en el cuarto trimestre, el campo API sería </p> <code> watch_list_q4_target</code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fortune 1000 </td> 
   <td colname="col2"> queue_1000 </td> 
   <td colname="col3"> Indica si la organización está en la lista Fortune 1000. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Forbes 2000 </td> 
   <td colname="col2"> forbes_2000 </td> 
   <td colname="col3"> Indica si la organización está en la lista Forbes 2000. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Recuento de empleados </td> 
   <td colname="col2"> employee_count </td> 
   <td colname="col3"> Número de personas empleadas en la organización. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ventas anuales </td> 
   <td colname="col2"> anual_sales </td> 
   <td colname="col3"> En el caso de las entidades públicas, los ingresos anuales se basan en los registros públicos informados por la empresa para la sede global en todas las ubicaciones. Para las organizaciones privadas, se basa en una estimación consensuada del número anual de ingresos por ventas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Número de teléfono </td> 
   <td colname="col2"> phone </td> 
   <td colname="col3"> Número de teléfono de la organización identificada. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dirección </td> 
   <td colname="col2"> street_address </td> 
   <td colname="col3"> Dirección de la organización identificada. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ciudad </td> 
   <td colname="col2"> city </td> 
   <td colname="col3"> La ciudad de la organización identificada. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Estado </td> 
   <td colname="col2"> state </td> 
   <td colname="col3"> Estado de la organización identificada. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Código del país </td> 
   <td colname="col2"> country_code </td> 
   <td colname="col3"> Código de país ISO de dos caracteres de la organización identificada. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nombre del país </td> 
   <td colname="col2"> country_name </td> 
   <td colname="col3"> El nombre de país del valor de cadena del país para la organización identificada. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Zip </td> 
   <td colname="col2"> zip </td> 
   <td colname="col3"> Código postal del país o estado de la organización identificada. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sitio web </td> 
   <td colname="col2"> web_site </td> 
   <td colname="col3"> Dirección URL utilizada por la organización identificada. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ticker bursátil </td> 
   <td colname="col2"> stock_ticker </td> 
   <td colname="col3"> El ticker bursátil si la organización está integrada en bolsa. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Código SIC primario </td> 
   <td colname="col2"> primary_sic </td> 
   <td colname="col3"> Código SIC de consenso asignado a la organización identificada. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Latitud </td> 
   <td colname="col2"> latitude </td> 
   <td colname="col3"> Latitud para la ubicación de la organización identificada. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Longitud </td> 
   <td colname="col2"> longitude </td> 
   <td colname="col3"> Longitud de la ubicación de la organización identificada. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tráfico </td> 
   <td colname="col2"> traffic </td> 
   <td colname="col3"> Cantidad de tráfico del sitio web, estimada en baja, media o alta o muy alta. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> B2B </td> 
   <td colname="col2"> b2b </td> 
   <td colname="col3"> Indica que la empresa identificada vende principalmente a otras empresas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> B2C </td> 
   <td colname="col2"> b2c </td> 
   <td colname="col3"> Indica que la empresa identificada vende principalmente a consumidores o personas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Perspectiva de la tecnología </td> 
   <td colname="col2"> ??? </td> 
   <td colname="col3"> Hasta 75 categorías de tecnología definidas por los clientes a través de categoría, proveedor y productos para el uso de anuncios, mensajes o copias de marketing con objetivos o personalización. </td> 
  </tr> 
 </tbody> 
</table>


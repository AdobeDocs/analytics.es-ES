---
description: Enumera los identificadores de dimensión opcionales que se pueden proporcionar en el paso 4 del Asistente de integración de Adobe.
seo-description: Enumera los identificadores de dimensión opcionales que se pueden proporcionar en el paso 4 del Asistente de integración de Adobe.
seo-title: Dimensiones personalizadas Demandbase
title: Dimensiones personalizadas Demandbase
uuid: d 1621046-3 aa 2-46 b 9-a 536-4 a 8 fb 792 b 69 f
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Demandbase Custom Dimensions{#demandbase-custom-dimensions}

Enumera los identificadores de dimensión opcionales que se pueden proporcionar en el paso 4 del Asistente de integración de Adobe.

Si no está seguro del ID de API exacto para ingresar al asistente, consulte con el representante de Demandbase.

>[!IMPORTANT]
>
>Se recomienda NO incluir la dirección IP como dimensión personalizada. La cantidad extremadamente alta de valores únicos puede provocar problemas de rendimiento con los informes. Además, la dirección IP ya se ofrece como opción de informes a través de los informes del almacén de datos de Adobe.

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
   <td colname="col2"> isp </td> 
   <td colname="col3"> Indica si la organización identificada se clasifica como ISP. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Alias de mercadotecnia </td> 
   <td colname="col2"> marketing_ alias </td> 
   <td colname="col3"> Nombre de organización limpio o abreviado (32 caracteres o menos) para su uso en anuncios, mensajes o copia de marketing. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Etiquetas Watch Watch </td> 
   <td colname="col2"> watch_ list (personalizado) </td> 
   <td colname="col3">Conjunto ilimitado de etiquetas definidas por cliente que pueden agregarse a sus datos de respuesta API por organización. <p><b>Ejemplo</b>: si tiene una etiqueta de inspección llamada T 4 Target, el campo API sería </p> <code> watch_ list_ q 4_ target</code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fortune 1000 </td> 
   <td colname="col2"> fortune_ 1000 </td> 
   <td colname="col3"> Indica si la organización está en la lista Fortune 1000. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Forbes 2000 </td> 
   <td colname="col2"> forbes_ 2000 </td> 
   <td colname="col3"> Indica si la organización está en la lista Forbes 2000. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Recuento de empleados </td> 
   <td colname="col2"> employee_ count </td> 
   <td colname="col3"> Número de personas empleadas en la organización. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ventas anuales </td> 
   <td colname="col2"> anual_ sales </td> 
   <td colname="col3"> Para entidades públicas, los ingresos anuales se basan en registros públicos informados por la empresa para el HQ global en todas las ubicaciones. Para las organizaciones privadas, se basa en la estimación de consenso del número de ingresos anual de ventas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Número de teléfono </td> 
   <td colname="col2"> teléfono </td> 
   <td colname="col3"> Número de teléfono de la organización identificada. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dirección Street </td> 
   <td colname="col2"> street_ address </td> 
   <td colname="col3"> Se identificó la dirección street de la organización. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ciudad </td> 
   <td colname="col2"> ciudad </td> 
   <td colname="col3"> Ciudad de la organización identificada. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Estado </td> 
   <td colname="col2"> state </td> 
   <td colname="col3"> El estado de la organización identificada. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Código del país </td> 
   <td colname="col2"> country_ code </td> 
   <td colname="col3"> El código de país de dos caracteres ISO de la organización identificada. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nombre del país </td> 
   <td colname="col2"> country_ name </td> 
   <td colname="col3"> El valor de cadena del país del país de la organización identificada. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Código postal </td> 
   <td colname="col2"> zip </td> 
   <td colname="col3"> Código postal del país o estado de la organización identificada. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sitio Web </td> 
   <td colname="col2"> web_ site </td> 
   <td colname="col3"> La dirección URL utilizada por la organización identificada. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Stock Ticker </td> 
   <td colname="col2"> stock_ ticker </td> 
   <td colname="col3"> El ticker de bolsa si la organización identificada se ha comercializado públicamente. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Código SIC principal </td> 
   <td colname="col2"> primary_ sic </td> 
   <td colname="col3"> Código SIC de consenso asignado para la organización identificada. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Latitud </td> 
   <td colname="col2"> latitud </td> 
   <td colname="col3"> Latitud para la ubicación de la organización identificada. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Longitud </td> 
   <td colname="col2"> longitud </td> 
   <td colname="col3"> Longitud de la ubicación de la organización identificada. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tráfico </td> 
   <td colname="col2"> tráfico </td> 
   <td colname="col3"> Cantidad de tráfico del sitio Web, estimada en baja, media o alta o muy alta. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> B2B </td> 
   <td colname="col2"> b2b </td> 
   <td colname="col3"> Indica que la empresa identificada principalmente vende a otras empresas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> B2C </td> 
   <td colname="col2"> b2c </td> 
   <td colname="col3"> Indica que la empresa identificada principalmente vende a consumidores o personas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Insight Insight </td> 
   <td colname="col2"> ??? </td> 
   <td colname="col3"> Hasta 75 categorías de tecnología definidas por clientes por categoría, vendedor y producto para el uso de objetivos y/o personalización de publicidades, mensajes o copia de mercadotecnia. </td> 
  </tr> 
 </tbody> 
</table>


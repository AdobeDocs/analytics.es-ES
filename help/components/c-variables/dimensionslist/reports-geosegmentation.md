---
description: Muestra datos sobre la ubicación del visitante. Los informes de segmentación geográfica incluyen Países, Regiones, Ciudades, Estados de EE.UU. y DMA de EE.UU. (área de mercadotecnia digital). Los informes de segmentación geográfica están habilitados para todos los clientes.
title: Segmentación geográfica
topic: Reports
uuid: 66aa22c4-dcbc-491a-b23c-0c3d87444d23
translation-type: tm+mt
source-git-commit: 5e47974fcf95625def21a9011ad981197ae39c99

---


# Segmentación geográfica

Muestra datos sobre la ubicación del visitante. Los informes de segmentación geográfica incluyen Países, Regiones, Ciudades, Estados de EE.UU. y DMA de EE.UU. (área de mercadotecnia digital). Los informes de segmentación geográfica están habilitados para todos los clientes.

Todas las métricas que están disponibles en otras partes de Informes y análisis se incluyen automáticamente en los informes Países, Regiones, Ciudades, Estados de EE.UU. y DMA: métricas de conversión y basadas en visitas, así como métricas calculadas. For more information, see this Adobe [blog](https://blogs.adobe.com/digitalmarketing/analytics/introducing-new-metrics-in-geosegmentation-and-more/) post.

<table id="table_566CFFC82E1149D8BAFE6641627FCF1F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Información general de la tienda de aplicaciones </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Países </td> 
   <td colname="col2"> <p> La mayor división geográfica. Además de las vistas Tendencias y Clasificación estándar que están disponibles en la mayoría de los informes, existe también una vista Mapa que representa los países con colores, de acuerdo con la contribución relativa de cada uno al tráfico total. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Regiones </td> 
   <td colname="col2"> <p> Área geográfica más pequeña que un país pero más grande que una ciudad. En algunos países, una región es un estado, una provincia o una prefectura. En otras áreas, es un país constitutivo, departamento o región metropolitana. A la derecha de cada región mostrada, el país de la región también se muestra entre paréntesis. </p> <p>En el detalle de la tabla, haga clic en Ejecutar un informe de ciudades para esta región (la lupa) para ejecutar un informe que muestre el rendimiento de las ciudades de una región seleccionada en comparación con otras ciudades de la región. </p> <p>See <a href="/help/components/c-variables/dimensionslist/reports-geosegmentation-reference.md"  > GeoSegmentation Regions and Postal Code usage by Country</a> to see which countries use regions. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ciudades </td> 
   <td colname="col2"> <p> La división geográfica más pequeña. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Estados de EE. UU. </td> 
   <td colname="col2"> <p> Mapa de calor que muestra visitantes a cada estado de los Estados Unidos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> DMA de EE. UU. </td> 
   <td colname="col2"> <p> (Área de marketing digital) Divisiones de mercado de medios para radio y televisión en todo Estados Unidos. Puede filtrar el informe para que muestre solamente las áreas de mercadotecnia dentro de un estado en particular. Estos datos se proporcionan mediante una asociación entre Adobe y Nielsen Media Research, Inc. </p> <p>Nota: La entrada No especificada en el informe DMA de EE. UU. indica los visitantes que no pudieron asociarse con un DMA específico. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Precisión del informe </td> 
   <td colname="col2"> <p>Adobe se ha asociado con Digital Envoy, un proveedor líder de soluciones de autenticación e inteligencia IP, para la segmentación geográfica de oferta, una función de medición geográfica basada en las direcciones IP de los usuarios finales. Si bien la precisión basada en conjuntos de datos individuales puede variar, por lo general Digital Envoy oferta más del 99% de la precisión a nivel de país, más del 97% a nivel de región y más del 90% de la precisión a nivel de ciudad. </p> <p>Note: These numbers assume that <a href="/help/admin/admin/general-acct-settings-admin.md">the setting</a> to remove the last octet of the IP address is NOT enabled. </p> <p>Las direcciones IP se asignan a códigos postales; cada ciudad queda definida por los códigos postales que define la “autoridad local” como parte de esa ciudad. Por ejemplo, la periferia de Berlín no se incluye en la definición de la ciudad, sino que cada localidad/ciudad se indica por separado, asumiendo que las direcciones IP se puedan asignar con precisión a un código postal en una de esas localidades. </p> <p>Algunos factores que pueden influir en los datos de segmentación geográfica son: </p> 
    <ul id="ul_1B05024AD5174232A8DB8145753FB09B"> 
     <li id="li_C3A21E7C1186490EB9A236634DB45E7F">Direcciones IP que representan proxies corporativos. Pueden aparecer como tráfico procedente de la red corporativa del usuario, que en realidad puede ser una ubicación diferente si el usuario trabaja de forma remota. </li> 
     <li id="li_56FC36B3598C420F9246D4E8772822A7">Direcciones IP móviles. La segmentación por IP móvil funciona en distintos niveles según la ubicación y la red. Varios portadores reparan el tráfico de IP a través de POP centralizados o regionales. </li> 
     <li id="li_C1EED854AE584489BCBC2A7AA20B8EF1">Direcciones IP pertenecientes a usuarios de ISP satelitales. Identificar la ubicación específica de estos usuarios es difícil, ya que normalmente parecen proceder de la ubicación del vínculo superior. </li> 
     <li id="li_A735756F39554DF19E05D251CA614F02">IP militares y gubernamentales. Esto suele representar al personal que viaja por todo el mundo y entra por su lugar de origen, en lugar de la base o oficina donde se encuentra actualmente. </li> 
     <li id="li_ACFF1B8094684173B8325A44304CA32B">Nuestros datos de segmentación geográfica/IP son proporcionados por un proveedor de terceros y se actualizan regularmente según la información proporcionada por los ISP y otras fuentes de red. Las búsquedas de IP son intrínsecamente volátiles, porque se compran y venden frecuentemente en todo el mundo. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>


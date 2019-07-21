---
description: Muestra información sobre la ubicación del visitante. Los informes de segmentación geográfica incluyen Países, Regiones, Ciudades, Estados de EE. UU. y la DMA de EE. UU. (área de marketing digital). Los informes de segmentación geográfica están habilitados para todos los clientes.
seo-description: Muestra información sobre la ubicación del visitante. Los informes de segmentación geográfica incluyen Países, Regiones, Ciudades, Estados de EE. UU. y la DMA de EE. UU. (área de marketing digital). Los informes de segmentación geográfica están habilitados para todos los clientes.
seo-title: Segmentación geográfica
solution: Analytics
title: Segmentación geográfica
topic: 'Informes '
uuid: 66 aa 22 c 4-dcbc -491 a-b 23 c -0 c 3 d 87444 d 23
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Segmentación geográfica

Muestra información sobre la ubicación del visitante. Los informes de segmentación geográfica incluyen Países, Regiones, Ciudades, Estados de EE. UU. y la DMA de EE. UU. (área de marketing digital). Los informes de segmentación geográfica están habilitados para todos los clientes.

Todas las métricas disponibles en otros lugares distintos a Reports &amp; Analytics se incluyen automáticamente en los informes Países, Regiones, Ciudades, Estados de EE. UU. y DMA: métricas de conversión y las basadas en visitas, así como las métricas calculadas. Para obtener más información, consulte esta publicación de [blog](https://blogs.adobe.com/digitalmarketing/analytics/introducing-new-metrics-in-geosegmentation-and-more/) de Adobe.

<table id="table_566CFFC82E1149D8BAFE6641627FCF1F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Informe </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Países </td> 
   <td colname="col2"> <p> La división geográfica más extensa. Además de las vistas Tendencias y Clasificación estándar que están disponibles en la mayoría de los informes, existe también una vista Mapa que representa los países con colores, de acuerdo con la contribución relativa de cada uno al tráfico total. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Regiones </td> 
   <td colname="col2"> <p> Una zona geográfica más pequeña que un país, pero más grande que ciudad. En algunos países, una región es un estado, una provincia o una prefectura. En otras zonas, se trata de un país constituyente, departamento o región metropolitana. A la derecha de cada región que aparece, se muestra entre paréntesis el país al que pertenece. </p> <p>En el detalle de la tabla, haga clic en Ejecutar un informe de ciudades para esta región (la lupa) para ejecutar un informe que muestre el rendimiento de las ciudades de una región determinada comparado con el de otras ciudades de esa misma región. </p> <p>Consulte <a href="../../../components/c-variables/dimensionslist/reports-geosegmentation-reference.md#concept_F7D998B418544B39ACD8838B48B732F1" format="dita" scope="local"> Uso de regiones de segmentación geográfica y código postal por país</a> para ver qué países utilizan regiones. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ciudades </td> 
   <td colname="col2"> <p> La división geográfica más pequeña. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Estados de EE. UU. </td> 
   <td colname="col2"> <p> Mapa de calor de los visitantes de cada estado de Estados Unidos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> DMA de EE. UU. </td> 
   <td colname="col2"> <p> (Área de marketing digital) Divisiones del mercado de los medios de comunicación para radio y televisión de Estados Unidos. Es posible filtrar el informe para mostrar únicamente áreas de marketing dentro de un estado en particular. Estos datos se ofrecen gracias a la asociación establecida entre Adobe y Nielsen Media Research, Inc. </p> <p>Nota: La entrada No especificada en el informe DMA de EE. UU. indica los visitantes que no pudieron asociarse con un DMA específico. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Precisión de los informes </td> 
   <td colname="col2"> <p>Adobe se ha asociado con Digital Envoy, un proveedor líder de soluciones de autenticación e inteligencia IP, con el objetivo de ofrecer segmentación geográfica, que es una funcionalidad de medición geográfica basada en las direcciones IP de los usuarios finales. A pesar de que la precisión basada en conjuntos de datos individuales puede variar, la exactitud ofrecida por Digital Envoy supera generalmente el 99 % a nivel de país, el 97 % a nivel de región y el 90 % a nivel de ciudad. </p> <p>Nota: Estos números suponen que [la configuración] (/help/admin/admin/general-acct-settings-admin. md) para eliminar el último octeto de la dirección IP NO está habilitado. </p> <p>Las direcciones IP se asignan a códigos postales; cada ciudad queda definida por los códigos postales que define la autoridad local como parte de esa ciudad. Por ejemplo, la periferia de Berlín no se incluye en la definición de la ciudad, sino que cada localidad/ciudad se indica por separado, asumiendo que las direcciones IP se puedan asignar con precisión a un código postal en una de esas localidades. </p> <p>Entre los factores que pueden influir en los datos de segmentación geográfica están: </p> 
    <ul id="ul_1B05024AD5174232A8DB8145753FB09B"> 
     <li id="li_C3A21E7C1186490EB9A236634DB45E7F">Direcciones IP que representan proxies corporativos. Puede parecer que es tráfico procedente de la red corporativa del usuario, que en realidad puede estar en una ubicación diferente si el usuario trabaja remotamente. </li> 
     <li id="li_56FC36B3598C420F9246D4E8772822A7">Direcciones IP de dispositivos móviles. La identificación de IP móviles objetivo funciona a varios niveles en función de la ubicación y la red. Hay una serie de operadores que conectan el tráfico de IP a través de POP centralizados o regionales. </li> 
     <li id="li_C1EED854AE584489BCBC2A7AA20B8EF1">Direcciones IP que pertenecen a usuarios de ISP satélites. No es fácil identificar la ubicación específica de estos usuarios, ya que normalmente parecen proceder de la ubicación del uplink. </li> 
     <li id="li_A735756F39554DF19E05D251CA614F02">Direcciones IP de ejércitos o gobiernos. A menudo se trata de personal que viaja por el mundo y entra en la red a través de su ubicación local, en vez de hacerlo desde la base o la oficina en la que está destinado. </li> 
     <li id="li_ACFF1B8094684173B8325A44304CA32B">Nuestros datos de geosegmentación o IP los facilita un proveedor tercero y se actualizan periódicamente basándose en la información que proporcionan los ISP y otras fuentes de red. Los búsquedas de IP son volátiles de forma inherente porque se compran y venden frecuentemente en todo el mundo. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>


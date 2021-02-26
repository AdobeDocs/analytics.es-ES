---
description: Opciones de calendario aparte del modelo gregoriano. Las opciones incluyen los modelos de calendario 4-4-5, 4-5-4 y 5-4-4, todos ellos utilizados como estándar en el sector minorista. Además, los informes ofrecen la opción de usar un calendario totalmente personalizable que puede configurar usted mismo.
title: Personalizar calendario
topic: Herramientas de administración
uuid: 4e5e538b-54c9-4c2f-8b6c-9f91b6c7bcc7
translation-type: tm+mt
source-git-commit: d0fe97b9368cbc4c9e79f9e56adf9786b58dce1a
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 92%

---


# Personalizar calendario

Opciones de calendario aparte del modelo gregoriano. Las opciones incluyen los modelos de calendario 4-4-5, 4-5-4 y 5-4-4, todos ellos utilizados como estándar en el sector minorista. Además, los informes ofrecen la opción de usar un calendario totalmente personalizable que puede configurar usted mismo.

**[!UICONTROL Administración]** > **[!UICONTROL Grupo de informes]** > Seleccionar grupo de informes > **[!UICONTROL Editar configuración]** > **[!UICONTROL General]** > **[!UICONTROL Personalizar calendario]**

>[!CAUTION]
>
>Al modificar el calendario se cambia la forma en que se procesan los datos (es decir, la definición de los visitantes únicos por semana y por mes). Al cambiar la definición de semanas y meses de un calendario no se modifican los datos históricos. Esta configuración también afecta a los segmentos en función de intervalos de fechas.

El calendario se puede usar para definir el primer día de la semana y del año, y permite elegir un estilo de calendario comercial distinto. Los formatos de calendario se utilizan por distintos motivos, entre los que se incluyen la comparación de ventas y estandarización de la previsión, el análisis del costo en plantilla o la regulación del recuento de inventario físico. Por ejemplo, el sector minorista utiliza el calendario contable 4-5-4 para las temporadas de venta específicas de dicho sector. A continuación se describe cada formato de calendario.

## Descripción de las opciones de personalización de calendario {#section_B0D224DACB914A378902A4E0E1234889}

<table id="table_E609632569EB499184E56618C2CEF742"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Calendario </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Calendario gregoriano </p> </td> 
   <td colname="col2"> <p> Utiliza el formato de calendario tradicional (de enero a diciembre con 30 o 31 días y un número variable de semanas en cada mes). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Calendario gregoriano modificado </p> </td> 
   <td colname="col2"> <p> Utiliza el calendario gregoriano tradicional, pero permite seleccionar el primer mes del año y el primer día de la semana. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Calendario comercial 4-5-4 </p> </td> 
   <td colname="col2"> <p> Divide cada mes según el número de semanas del mes. Es decir, enero tiene cuatro semanas y así sucesivamente. La National Retail Federation (Federación Nacional Minorista de EE. UU.) utiliza el formato de calendario 4-5-4. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Calendario personalizado </p> </td> 
   <td colname="col2"> <p> Ofrece tres formatos, según el número de semanas de cada mes. El número de semanas de cada mes depende del primer día del año seleccionado. </p> <p>Un año tiene 52 semanas. Se divide esa cantidad entre 4 trimestres y se obtienen 13 semanas por trimestre. Pero un trimestre tiene 3 meses. Como 13 no es divisible entre 3, se acaba asignando la semana extra a uno de los meses para que el resultado siempre sea coherente. 5-4-4 significa que el primer mes del trimestre tiene la semana extra. 4-5-4 significa que el segundo mes del trimestre tiene la semana extra, etc. En el calendario 4-4-5, la semana 53.ª se añade al último trimestre del año. </p> 
    <ul id="ul_1579FD106A47419486B03E248A5E6ED5"> 
     <li id="li_E9B9E8F03E324DBDA9139C2D0D599092"><b>4-5-4</b>: enero tiene 4 semanas, febrero tiene 5, marzo tiene 4, y así sucesivamente. </li> 
     <li id="li_D0675DBDEC4641D2A8645B5CDFC565AB"><b>4-4-5</b>: enero tiene 4 semanas, febrero tiene otras 4, marzo tiene 5, y así sucesivamente. </li> 
     <li id="li_6743BBB9AC9A4CFEAA0CBCE51052BC29"><b>5-4-4</b>: enero tiene 5 semanas, febrero tiene 4, marzo tiene otras 4, y así sucesivamente. </li> 
    </ul> <p>Nota:  Esta opción de calendario se admite en todas las herramientas de Adobe Analytics (Analysis Workspace, Informes y análisis, Report Builder y Activity Map) excepto en la Data Warehouse, que no admite calendarios personalizados. </p> </td> 
  </tr> 
 </tbody> 
</table>


---
description: Report Builder utiliza el calendario personalizado de Analytics. El calendario se puede usar para definir el primer día de la semana y del año, y permite elegir un estilo de calendario comercial distinto. Los formatos de calendario se utilizan por distintos motivos, entre los que se incluyen la comparación de ventas y estandarización del pronóstico, el análisis del coste en plantilla o la regulación del recuento de inventario físico.
title: Calendario personalizado
feature: Report Builder
role: User, Admin
exl-id: e65cb6c8-8bb0-4dcd-a3a3-d22adcd024fa
TQID: https://experienceleague.adobe.com/At3YiOPV0jx5WXwe-VvA05n3yIEmiAJIRzoOoeISeA4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 409
ht-degree: 83%

---

# Calendario personalizado

{{legacy-arb}}

Report Builder utiliza el calendario personalizado de Analytics. El calendario se puede usar para definir el primer día de la semana y del año, y permite elegir un estilo de calendario comercial distinto. Los formatos de calendario se utilizan por distintos motivos, entre los que se incluyen la comparación de ventas y estandarización del pronóstico, el análisis del coste en plantilla o la regulación del recuento de inventario físico.

A continuación, se describe cada formato de calendario.

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
   <td colname="col2"> <p> Ofrece tres formatos, según el número de semanas de cada mes. El número de semanas de cada mes depende del primer día del año seleccionado. </p> <p>Un año tiene 52 semanas. Se divide esa cantidad entre 4 trimestres y se obtienen 13 semanas por trimestre. Pero un trimestre tiene 3 meses. Como 13 no es divisible entre 3, se acaba asignando la semana extra a uno de los meses para que el resultado siempre sea coherente. 5-4-4 significa que el primer mes del trimestre tiene la semana extra. 4-5-4 significa que el segundo mes tiene la semana extra, etc. En el calendario 4-4-5, la semana 53.ª se añade al último trimestre del año. </p> 
    <ul id="ul_1579FD106A47419486B03E248A5E6ED5"> 
     <li id="li_E9B9E8F03E324DBDA9139C2D0D599092"><b>4-5-4</b>: enero tiene 4 semanas, febrero tiene 5, marzo tiene 4, y así sucesivamente. </li> 
     <li id="li_D0675DBDEC4641D2A8645B5CDFC565AB"><b>4-4-5</b>: enero tiene 4 semanas, febrero tiene otras 4, marzo tiene 5, y así sucesivamente. </li> 
     <li id="li_6743BBB9AC9A4CFEAA0CBCE51052BC29"><b>5-5-4</b>: enero tiene 5 semanas, febrero tiene 5, marzo tiene 4, y así sucesivamente. </li> 
    </ul> <p>Nota: Esta opción de calendario es compatible con todas las herramientas de Adobe Analytics: Analysis Workspace, Report Builder y Activity Map. La excepción es Data Warehouse, que no admite calendarios personalizados. </p> </td> 
  </tr> 
 </tbody> 
</table>

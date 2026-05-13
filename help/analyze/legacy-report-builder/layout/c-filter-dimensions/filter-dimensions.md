---
description: Puede filtrar las dimensiones que agregue a la cuadrícula Rótulos de fila. Los filtros limitan los datos devueltos por las solicitudes y se pueden aplicar desde la tabla dinámica o los diseños personalizados. Al configurar el filtrado de dimensiones desde el Diseño de tabla dinámica, también se puede especificar el número de entradas de la celda.
title: Resumen del filtrado de dimensiones
uuid: c54d5add-f278-476d-8f14-73f1c2e37671
feature: Report Builder
role: User, Admin
exl-id: eded07d5-3c06-419b-92fd-1a48856ac293
TQID: https://experienceleague.adobe.com/yY1Sl6vEWRb-62SzM5e5qxt5lZPHeg-LU5ZiUNb5z8Q
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 451
ht-degree: 17%

---

# Resumen del filtrado de dimensiones

{{legacy-arb}}

Puede filtrar las dimensiones que agregue a la cuadrícula Rótulos de fila. Los filtros limitan los datos devueltos por las solicitudes y se pueden aplicar desde la tabla dinámica o los diseños personalizados. Al configurar el filtrado de dimensiones desde el Diseño de tabla dinámica, también se puede especificar el número de entradas de la celda.

El formulario de filtro seleccionado se rellena en función del elemento y la métrica que estén seleccionados en la solicitud de Report Builder.

## Definir filtro: valores y caracteres especiales {#section_15840216A4044C40974945FAA435AD93}

Información sobre los filtros del panel **[!UICONTROL Filtro más popular]** > **[!UICONTROL Definir filtro]**.

![Captura de pantalla que muestra el cuadro de diálogo Definir filtro con opciones para filtrar por aplicación, usuario y proyecto.](/help/admin/tools/assets/filter.png)

En las tablas siguientes se proporcionan ejemplos e información sobre los filtros:

<table id="table_8AC3A26FF02143DBA949B30F2A46CF11"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Filtro </th> 
   <th colname="col02" class="entry"> Descripción </th> 
   <th colname="col2" class="entry"> Filtro de ejemplo </th> 
   <th colname="col3" class="entry"> Resultados de coincidencias </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Contiene todos los términos </p> </td> 
   <td colname="col02"> <p>Contiene todos los valores delimitados por espacios en cualquier orden. </p> </td> 
   <td colname="col2"> <p>a b c </p> </td> 
   <td colname="col3"> <p>Coincide con <span class="term"> a b c</span> y <span class="term"> b a c</span>, etc. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Contiene cualquier término </p> </td> 
   <td colname="col02"> <p>Contiene al menos uno de los filtros (delimitados por espacios). </p> </td> 
   <td colname="col2"> <p>A B C </p> </td> 
   <td colname="col3"> <p>Coincide con <span class="term"> A1</span>, <span class="term"> B2</span>, <span class="term"> C3</span>, pero no con <span class="term"> D4</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Contiene la frase </p> </td> 
   <td colname="col02"> <p>Contiene el filtro de búsqueda y posiblemente otros términos. </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p>Coincide con <span class="term"> abc</span> y <span class="term"> abc def</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>No contiene ningún término </p> </td> 
   <td colname="col02"> <p>Devuelve todo, a menos que contenga un valor que usted haya especificado. </p> </td> 
   <td colname="col2"> <p>a b c </p> </td> 
   <td colname="col3"> <p>Coincide <span class="term"> d e f</span> pero no <span class="term"> c d e f</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>No contiene la frase </p> </td> 
   <td colname="col02"> <p>Devuelve todo lo que no contiene su frase. </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p>Excluye <span class="term"> abc</span>, <span class="term"> abc def</span> y coincide con <span class="term"> def</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Es igual a </p> </td> 
   <td colname="col02"> <p>Devuelve una coincidencia exacta. </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p> <span class="term"> abc</span> es el único resultado devuelto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>No es igual que </p> </td> 
   <td colname="col02"> <p>Devuelve todo lo que no coincida exactamente con su entrada. </p> </td> 
   <td colname="col2"> <p>a </p> </td> 
   <td colname="col3"> <p>No coincide con <span class="term"> a</span>. </p> <p>Coincide con <span class="term"> a b c</span>. </p> <p>Coincide con <span class="term"> abc</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Comienza con </p> </td> 
   <td colname="col02"> <p>Devuelve resultados que comienzan con un valor específico. </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p>Coincide con <span class="term"> abcd</span> pero no con <span class="term"> 1abc</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Finaliza con </p> </td> 
   <td colname="col02"> <p>Devuelve resultados que terminan con el valor específico. </p> </td> 
   <td colname="col2"> <p>xyz </p> </td> 
   <td colname="col3"> <p>Coincide con <span class="term"> wxyz</span>, pero no con <span class="term"> wxyz0</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Avanzado (caracteres especiales) </p> </td> 
   <td colname="col02"> <p>Permite usar caracteres regex: </p> <p> <code> "", ^, -, *, $, | </code> </p> </td> 
   <td colname="col2"> <p>"^Página*principal$" | deportes </p> </td> 
   <td colname="col3"> <p> Define un filtro que comienza con <span class="term"> Página principal</span>, luego busca cero o más caracteres y luego termina con <span class="term"> Página</span>. </p> <p>Además, cualquier página con <span class="term"> deportes</span>. </p> <p>Algunos ejemplos de coincidencias: </p> 
    <ul id="ul_72D76C5AFEAF405E8A0E4E3C604D10AE"> 
     <li id="li_4D490059B667450DA8A0103167C7B391">HomePage </li> 
     <li id="li_1351619156274092AEB2771D882AD357">Página principal y (otros caracteres) </li> 
     <li id="li_940EAA99A8CF49308E8471065EB317B1">Deportes en casa </li> 
     <li id="li_50A895F14A454BE9BF06EE0F07F99B3B">página de deportes </li> 
     <li id="li_F3CE0D07941D4C2485D2DE0B73E00677">deportes </li> 
     <li id="li_E84C15C061824A5D922D9900392F2996">deportes xyz abc </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_8BBB06C8860745DEA41B39673699DC0F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Caracteres especiales </th> 
   <th colname="col2" class="entry"> Finalidad </th> 
   <th colname="col3" class="entry"> Notas </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> " " </td> 
   <td colname="col2"> Es igual a </td> 
   <td colname="col3"> <p>No se escapa a menos que no esté emparejado con otra cita. Por ejemplo, <span class="term"> 17" Display</span> no es una frase. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> * </td> 
   <td colname="col2"> Comodín </td> 
   <td colname="col3"> <p>Igual que el asterisco utilizado en una expresión regular. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ^ </td> 
   <td colname="col2"> Comienza con </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> $ </td> 
   <td colname="col2"> Finaliza con </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> - </td> 
   <td colname="col2"> No </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> | </td> 
   <td colname="col2"> O bien </td> 
   <td colname="col3"> <p>Compatible solo con el filtro avanzado <span class="term"> (caracteres especiales)</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

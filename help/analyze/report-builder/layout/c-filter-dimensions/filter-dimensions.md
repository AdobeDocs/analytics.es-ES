---
description: Es posible filtrar las dimensiones que se añadan a la cuadrícula Rótulos de fila. Los filtros limitan los datos devueltos por las solicitudes y se pueden aplicar desde los diseños personalizados y de tabla dinámica. Cuando se configura el filtro de dimensiones desde el diseño de tabla dinámica, se puede especificar además el número de entradas de la celda.
title: Resumen del filtrado de dimensiones
uuid: c54d5add-f278-476d-8f14-73f1c2e37671
feature: Report Builder
role: Profesional empresarial, administrador
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 98%

---


# Resumen del filtrado de dimensiones

Es posible filtrar las dimensiones que se añadan a la cuadrícula Rótulos de fila. Los filtros limitan los datos devueltos por las solicitudes y se pueden aplicar desde los diseños personalizados y de tabla dinámica. Cuando se configura el filtro de dimensiones desde el diseño de tabla dinámica, se puede especificar además el número de entradas de la celda.

El formulario del filtro seleccionado se completa según el elemento y la métrica que estén seleccionados en la solicitud de Report Builder.

## Definir filtro: valores y caracteres especiales {#section_15840216A4044C40974945FAA435AD93}

Información sobre filtros en el panel **[!UICONTROL Filtros más populares]** > **[!UICONTROL Definir filtro]**.

![](assets/define_filter.png)

Las tablas que aparecen a continuación contienen ejemplos e información sobre filtros:

<table id="table_8AC3A26FF02143DBA949B30F2A46CF11"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Filtro </th> 
   <th colname="col02" class="entry"> Descripción </th> 
   <th colname="col2" class="entry"> Ejemplo de filtro </th> 
   <th colname="col3" class="entry"> Resultados de coincidencias </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Contiene todos los términos </p> </td> 
   <td colname="col02"> <p>Contiene todos los valores delimitados por espacios, en cualquier orden. </p> </td> 
   <td colname="col2"> <p>a b c </p> </td> 
   <td colname="col3"> <p>Devuelve como resultado <span class="term"> a b c</span> y <span class="term"> b a c</span>, etc. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Contiene cualquier término </p> </td> 
   <td colname="col02"> <p>Contiene al menos uno de los filtros (delimitados por espacios). </p> </td> 
   <td colname="col2"> <p>A B C </p> </td> 
   <td colname="col3"> <p>Devuelve como resultado <span class="term"> A1</span>, <span class="term"> B2</span>, <span class="term"> C3</span>, pero no <span class="term"> D4</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Contiene la frase </p> </td> 
   <td colname="col02"> <p>Contiene el filtro de búsqueda y, posiblemente, otros términos. </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p>Devuelve como resultado <span class="term"> abc</span> y <span class="term"> abc def</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>No contiene ningún término </p> </td> 
   <td colname="col02"> <p>Devuelve todos los resultados excepto los que contienen alguno de los valores introducidos. </p> </td> 
   <td colname="col2"> <p>a b c </p> </td> 
   <td colname="col3"> <p>Devuelve como resultado <span class="term"> d e f</span> pero no <span class="term"> c d e f</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>No contiene la frase </p> </td> 
   <td colname="col02"> <p>Devuelve todos los resultados excepto los que contienen la frase especificada. </p> </td> 
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
   <td colname="col1"> <p>No es igual a </p> </td> 
   <td colname="col02"> <p>Devuelve todos los resultados excepto los que coinciden exactamente con lo que ha escrito. </p> </td> 
   <td colname="col2"> <p>a </p> </td> 
   <td colname="col3"> <p>No devuelve como resultado <span class="term"> a</span>. </p> <p>Coincide con <span class="term"> a b c</span>. </p> <p>Coincide con <span class="term"> abc</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Comienza con </p> </td> 
   <td colname="col02"> <p>Devuelve los resultados que comienzan con un valor específico. </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p>Devuelve como resultado <span class="term"> abcd</span> pero no <span class="term"> 1abc</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Finaliza con </p> </td> 
   <td colname="col02"> <p>Devuelve los resultados que finalizan con el valor especificado. </p> </td> 
   <td colname="col2"> <p>xyz </p> </td> 
   <td colname="col3"> <p>Coincide con <span class="term"> wxyz</span> pero no con <span class="term"> wxyz0</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Avanzado (caracteres especiales) </p> </td> 
   <td colname="col02"> <p>Permite usar caracteres de expresiones regulares: </p> <p> <code> "", ^, -, *, $, | </code> </p> </td> 
   <td colname="col2"> <p>"^Página*principal$" | deportes </p> </td> 
   <td colname="col3"> <p> Define un filtro que empieza por <span class="term"> Inicio</span> y, a continuación, busca cero o más caracteres y termina con <span class="term">Página</span>. </p> <p>Además, cualquier página con <span class="term"> deportes</span>. </p> <p>Varios ejemplos de coincidencias: </p> 
    <ul id="ul_72D76C5AFEAF405E8A0E4E3C604D10AE"> 
     <li id="li_4D490059B667450DA8A0103167C7B391">Página principal </li> 
     <li id="li_1351619156274092AEB2771D882AD357">Página y (otros caracteres) principal </li> 
     <li id="li_940EAA99A8CF49308E8471065EB317B1">Página de deportes </li> 
     <li id="li_50A895F14A454BE9BF06EE0F07F99B3B">Deportes principal </li> 
     <li id="li_F3CE0D07941D4C2485D2DE0B73E00677">deportes </li> 
     <li id="li_E84C15C061824A5D922D9900392F2996">xyz deportes abc </li> 
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
   <td colname="col1"> " </td> 
   <td colname="col2"> Es igual a </td> 
   <td colname="col3"> <p>No es necesario anteponer un carácter de escape si no se combina con otras comillas. Por ejemplo, <span class="term">Pantalla de 17"</span> no es una frase. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> * </td> 
   <td colname="col2"> Comodín </td> 
   <td colname="col3"> <p>Igual que el asterisco de una expresión regular. </p> </td> 
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
   <td colname="col2"> O </td> 
   <td colname="col3"> <p>Solo se puede usar en el filtro <span class="term"> Filtro avanzado (caracteres especiales)</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

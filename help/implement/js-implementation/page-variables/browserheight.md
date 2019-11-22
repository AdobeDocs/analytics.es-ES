---
description: Las variables de página rellenan directamente un informe, como pageName, Props de lista, Variables de lista, etc.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Variables de página
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 47291fb3d55ab3eb5ef181770bf2078c7ea55bc4

---


# browserHeight

La variable muestra la altura de la ventana del explorador.


<!-- 
browserheight.xml
-->

Esta variable se rellena después del código de página y antes de que se ejecute *`doPlugins`*.

> [!NOTE] Esta variable solo debe leerse, nunca configurarse.

Puede leer estos valores y copiarlos en props/eVars, pero no debe modificarlos nunca. Esta variable se incorporó por primera vez con la versión H.11 del archivo JavaScript.

**Parámetros**

<table id="table_94598A2204CF42FF9DD14D353D5C0468"> 
 <thead> 
  <tr> 
   <th class="entry"> Parámetro de consulta </th> 
   <th class="entry"> Valor </th> 
   <th class="entry"> Ejemplo </th> 
   <th class="entry"> Informes afectados </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>bh </p> </td> 
   <td> <p>Número entero positivo </p> </td> 
   <td> <p>865 </p> </td> 
   <td> <p>Tráfico &gt; Tecnología &gt; Altura del explorador </p> </td> 
  </tr> 
 </tbody> 
</table>


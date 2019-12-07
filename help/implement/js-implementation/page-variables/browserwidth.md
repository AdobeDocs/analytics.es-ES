---
description: Las variables de página rellenan directamente un informe, como pageName, Props de lista, Variables de lista, etc.
keywords: Analytics Implementation
subtopic: Variables
title: Variables de página
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---



# browserWidth

La variable muestra la anchura de la ventana del explorador.


<!-- 

browserwidth.xml

 -->

Esta variable se rellena después del código de página y antes de que se ejecute *`doPlugins`*.

> [!NOTE] Esta variable solo debe leerse, nunca configurarse.

Puede leer estos valores y copiarlos en props/eVars, pero no debe modificarlos nunca. Esta variable se incorporó por primera vez con la versión H.11 del archivo JavaScript.

**Parámetros**

<table id="table_B70F279A8CD240328520E5BD889806BD"> 
 <tbody> 
  <tr> 
   <td> <p> <b>Parámetro de consulta</b> </p> </td> 
   <td> <p> <b>Valor</b> </p> </td> 
   <td> <p> <b>Ejemplo</b> </p> </td> 
   <td> <p> <b>Informes afectados</b> </p> </td> 
  </tr> 
  <tr> 
   <td> <p>bw </p> </td> 
   <td> <p>Número entero positivo </p> </td> 
   <td> <p>1179 </p> </td> 
   <td> <p>Tráfico &gt; Tecnología &gt; Ancho del explorador </p> </td> 
  </tr> 
 </tbody> 
</table>

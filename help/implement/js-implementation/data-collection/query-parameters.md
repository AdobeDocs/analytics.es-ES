---
description: En las tablas siguientes se describe el parámetro de consulta que contiene el valor de las distintas variables de Analytics que se envían a la recopilación de datos.
keywords: Analytics Implementation
title: Parámetros de consulta de recopilación de datos
topic: Developer and implementation
uuid: 4d5af486-df27-42fe-bb9c-28938dddf2b2
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Parámetros de consulta de recopilación de datos

En las tablas siguientes se describe el parámetro de consulta que contiene el valor de las distintas variables de Analytics que se envían a la recopilación de datos.

Esta información puede usarse para depurar con [Analizadores de paquetes](/help/implement/impl-testing/packet-monitor.md), construir manualmente solicitudes de imagen o usar [Variables dinámicas](/help/implement/js-implementation/c-variables/dynvars-overview.md).

<table id="table_5442E15BF0AE4BDA92DDADD1C08F7C13"> 
 <thead> 
  <tr> 
   <th class="entry"> Parámetro </th> 
   <th class="entry"> Variable de Analytics </th> 
   <th class="entry"> Información introducida en el informe </th> 
   <th class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> aamlh </td> 
   <td colname="col2"> Ninguna </td> 
   <td colname="col3"> Ninguna </td> 
   <td colname="col4"> Indicación de ubicación de Audience Manager (usado en la integración de Experience Cloud Shared Profile) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> aamb </td> 
   <td colname="col2"> Ninguna </td> 
   <td colname="col3"> Ninguna </td> 
   <td colname="col4"> Blob de Audience Manager (usado en la integración de Experience Cloud Shared Profile) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> aid </td> 
   <td colname="col2"> Ninguna </td> 
   <td colname="col3"> Ninguna </td> 
   <td colname="col4"> ID de visitante de Analytics </td> 
  </tr> 
  <tr> 
   <td> AQB </td> 
   <td> Ninguna </td> 
   <td> Ninguna </td> 
   <td> Indica el comienzo de una solicitud de imagen. </td> 
  </tr> 
  <tr> 
   <td> AQE </td> 
   <td> Ninguna </td> 
   <td> Ninguna </td> 
   <td> Indica el final de una solicitud de imagen, indicando que no se truncó la solicitud. </td> 
  </tr> 
  <tr> 
   <td> bh </td> 
   <td> Ninguna </td> 
   <td> Perfil del visitante | Tecnología | Altura del explorador </td> 
   <td> Altura de la ventana del explorador (en píxeles). </td> 
  </tr> 
  <tr> 
   <td> bw </td> 
   <td> Ninguna </td> 
   <td> Perfil del visitante | Tecnología | Ancho del explorador </td> 
   <td> Ancho de la ventana del explorador (en píxeles). </td> 
  </tr> 
  <tr> 
   <td> c </td> 
   <td> Ninguna </td> 
   <td> Perfil del visitante | Tecnología | Profundidad de color del monitor </td> 
   <td> Calidad de color (en bits). </td> 
  </tr> 
  <tr> 
   <td> </td><td><p></p></td><td><p></p></td><td><p></p><p><code> &lt;my.a&gt;red&lt;/my.a&gt; </code></p><p></p><p><code> &lt;my&gt;&lt;a&gt;red&lt;/a&gt;&lt;/my&gt; </code></p><p><code> my.a = red </code></p><p><code> c.&my.a=red </code></p></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td><code> D </code></td><td></td><td></td><td><p></p></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td><p><code> t </code></p><code>
      dd/mm/yyyy&amp;nbsp;hh:mm:ss&amp;nbsp;D&amp;nbsp;OFFSET 
    </code><p><code> 0-6 </code><code> OFFSET </code></p><code>
      offset&amp;nbsp;from&amp;nbsp;GMT&amp;nbsp;in&amp;nbsp;hours&amp;nbsp;*&amp;nbsp;60&amp;nbsp;*&amp;nbsp;-&amp;nbsp;1 
    </code><p></p><code>
      23/09/2016&amp;nbsp;14:00:00&amp;nbsp;1&amp;nbsp;420 
    </code></td></tr><tr><td><code> ts </code></td><td><p></p></td><td></td><td><p></p></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td><p></p></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td><p></p></td></tr></tbody></table>


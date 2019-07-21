---
description: Descripciones de los campos de la configuración general del administrador dinámico de etiquetas para la implementación de Adobe Analytics.
keywords: Implementación de Analytics; método de implementación; administración dinámica de etiquetas; dtm; configuración general; conformidad con EU; conjunto de caracteres; código de moneda; servidor de seguimiento; servidor de seguimiento ssl
seo-description: Descripciones de los campos de la configuración general del administrador dinámico de etiquetas para la implementación de Adobe Analytics.
seo-title: General
solution: Analytics
title: General
topic: Desarrollador e implementación
uuid: 93008719-6 fb 6-4 e 39-9 a 75-c 937 fe 3247 b 9
translation-type: tm+mt
source-git-commit: 49c81e50ff10060ef7a3debe82132d1099e25118

---


# General

Descripciones de los campos de la configuración General en DTM para implementar Adobe Analytics.

**[!UICONTROL &lt; Propiedad &gt;]** &gt; ![](assets/settings_gear.png)**[!UICONTROL Herramienta de edición]** &gt; **[!UICONTROL General]**

<table id="table_DD8DA303698041D296DD5DB080AF7971"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Permitir conformidad con la UE de <span class="keyword">Adobe Analytics </span> </p> </td> 
   <td colname="col2"> <p> Habilita o deshabilita el rastreo en base a las cookies de privacidad de la UE. </p> <p>Cuando se carga una página, el sistema comprueba si hay una cookie denominada <span class="filepath">sat_track</span> configurada (o el nombre de cookie personalizado especificado en la página <span class="wintitle">Editar propiedad</span>). Consideremos la información siguiente: </p> 
    <ul id="ul_42A6D728F0BC4FBABB0069EFB66DCB01"> 
     <li id="li_227CB14326344AA3980F20C7EACF2AD2"> <p> Si la cookie no existe, o si existe pero está establecida en cualquier valor excepto <span class="term"> true </span>, la carga de la herramienta se omite cuando esta opción está habilitada. Lo que significa que cualquier parte de una regla que utilice la herramienta no se aplicará. </p> <p>Si una regla cuenta con análisis conformes con la UE y código de terceros, y la cookie se configura como <span class="term"> false </span>, el código de terceros sigue ejecutándose. Sin embargo, las variables de análisis no se configurarán. </p> </li> 
     <li id="li_1E74E02D7E4646ACA86D862A1D3C6679"> Si la cookie existe y está establecida en <span class="term"> true </span>, la herramienta se carga normalmente. </li> 
    </ul> <p>You are responsible for setting the <span class="filepath"> sat_track </span> (or custom named) cookie to <span class="term"> false </span> if a visitor opts out. Puede realizar esto mediante el uso de un código personalizado: </p> <p> 
     <code>_ satellite. setcookie («sat_ track», &amp; amp; nbsp; «false»); </code>
  </p> <p> You must also have a mechanism to set that cookie to <span class="term"> true </span> if you want a visitor to be able to opt in later: </p> <p> 
     <code>_ satellite. setcookie («sat_ track», &amp; amp; nbsp; «true»); </code>
  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Conjunto de caracteres </p> </td> 
   <td colname="col2"> <p>Muestra los conjuntos de codificación de caracteres disponibles. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Código de divisa </p> </td> 
   <td colname="col2"> <p>Muestra los códigos de divisa admitidos para la selección. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Servidor de seguimiento </p> </td> 
   <td colname="col2"> <p>Dominio en el cual se escriben la solicitud de imagen y la cookie. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Servidor de seguimiento de SSL </p> </td> 
   <td colname="col2"> <p>Dominio en el cual se escriben la solicitud de imagen y la cookie. Se utiliza para páginas seguras. Si no está definido, los datos SSL se dirigen a <span class="term"> trackingServer </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Centro de datos </p> </td> 
   <td colname="col2"> <p>Centro de datos de Adobe que se utiliza para recopilar datos. </p> </td> 
  </tr> 
 </tbody> 
</table>


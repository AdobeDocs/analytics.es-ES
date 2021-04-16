---
description: Descripciones de los campos de la configuración general del administrador dinámico de etiquetas para la implementación de Adobe Analytics.
keywords: Implementación de Analytics, método de implementación, Dynamic Tag Management, dtm, configuración general, conformidad con la ue, conjunto de caracteres, código de divisa, servidor de seguimiento, servidor de seguimiento de ssl
title: General
topic-fix: Developer and implementation
uuid: 93008719-6fb6-4e39-9a75-c937fe3247b9
exl-id: f63e83bf-be87-4ea2-ba04-5c152e5d16d3
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 100%

---

# General

Descripciones de los campos de la configuración general de DTM para la implementación de Adobe Analytics.

**[!UICONTROL *`Property`*]** > ![](assets/settings_gear.png) **[!UICONTROL Editar herramienta]** > **[!UICONTROL General]**

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
     <li id="li_227CB14326344AA3980F20C7EACF2AD2"> <p> Si la cookie no existe, o si existe pero está establecida en cualquier valor excepto como <span class="term"> True </span>, la carga de la herramienta se omite al activar esta configuración. Lo que significa que cualquier parte de una regla que utilice la herramienta no se aplicará. </p> <p>Si una regla cuenta con análisis conformes con la UE y código de terceros, y la cookie se configura como <span class="term"> false </span>, el código de terceros seguirá ejecutándose. Sin embargo, las variables de análisis no se configurarán. </p> </li> 
     <li id="li_1E74E02D7E4646ACA86D862A1D3C6679"> Si la cookie existe y está establecida en <span class="term"> True </span>, la herramienta se cargará de forma normal. </li> 
    </ul> <p>Usted es el responsable de configurar la cookie <span class="filepath">sat_track</span> (o personalizada) en <span class="term">False</span> si un visitante decide excluirse. Puede realizar esto mediante el uso de un código personalizado: </p> <p> 
     <code>
       _satellite.setCookie("sat_track",&amp;nbsp;"false"); 
     </code> </p> <p> También debe tener un mecanismo para configurar esa cookie como <span class="term"> true </span> si desea que un visitante pueda aceptar su inclusión más tarde: </p> <p> 
     <code>
       _satellite.setCookie("sat_track",&amp;nbsp;"true"); 
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Conjunto de caracteres </p> </td> 
   <td colname="col2"> <p>Muestra los conjuntos de codificación de caracteres disponibles. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Código de moneda </p> </td> 
   <td colname="col2"> <p>Muestra los códigos de divisa admitidos para la selección. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Servidor de seguimiento </p> </td> 
   <td colname="col2"> <p>Dominio en el cual se escriben la solicitud de imagen y la cookie. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Servidor de seguimiento de SSL </p> </td> 
   <td colname="col2"> <p>Dominio en el cual se escriben la solicitud de imagen y la cookie. Se utiliza para páginas seguras. Si no se define, los datos SSL se dirigen a <span class="term">trackingServer</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Centro de datos </p> </td> 
   <td colname="col2"> <p>Centro de datos de Adobe que se utiliza para recopilar datos. </p> </td> 
  </tr> 
 </tbody> 
</table>

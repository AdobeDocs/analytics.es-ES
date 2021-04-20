---
description: Pasos para detener el seguimiento de los vínculos en Activity Map o en ClickMap preexistente.
title: Detener el seguimiento de vínculos
uuid: e17fb7bd-d6ed-45c3-a006-9150d5718cff
feature: Activity Map
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 96%

---


# Detener el seguimiento de vínculos

Pasos para detener el seguimiento de los vínculos en Activity Map o en ClickMap preexistente.

<table id="table_1745199B3105467CBA26F50B3B1CCE99"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Detención del seguimiento de vínculos </th> 
   <th colname="col2" class="entry"> Instrucciones </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Activity Map </td> 
   <td colname="col2"> Elimine el siguiente contenido del archivo Appmeasurement.js: 
    <code>
     /*
     &nbsp;START&nbsp;Activity&nbsp;Map&nbsp;MODULE&nbsp;The&nbsp;following&nbsp;module&nbsp;enables&nbsp;Activity&nbsp;Map&nbsp;tracking&nbsp;in&nbsp;Adobe&nbsp;Analytics.&nbsp;Activity&nbsp;Map
     &nbsp;allows&nbsp;you&nbsp;to&nbsp;view&nbsp;data&nbsp;overlays&nbsp;on&nbsp;your&nbsp;links&nbsp;and&nbsp;content&nbsp;to&nbsp;understand&nbsp;how
     &nbsp;users&nbsp;engage&nbsp;with&nbsp;your&nbsp;web&nbsp;site.&nbsp;If&nbsp;you&nbsp;do&nbsp;not&nbsp;intend&nbsp;to&nbsp;use&nbsp;Activity&nbsp;Map,&nbsp;you
     &nbsp;can&nbsp;remove&nbsp;the&nbsp;following&nbsp;block&nbsp;of&nbsp;code&nbsp;from&nbsp;your&nbsp;AppMeasurement.js&nbsp;file.
     &nbsp;Additional&nbsp;documentation&nbsp;on&nbsp;how&nbsp;to&nbsp;configure&nbsp;Activity&nbsp;Map&nbsp;is&nbsp;available&nbsp;at:
     &nbsp;https://docs.adobe.com/content/help/en/analytics/analyze/activity-map/getting-started/get-started-admins/activitymap-enable.html
     */
     function&nbsp;AppMeasurement_Module_Activity&nbsp;Map(g){func
     ...
     /*&nbsp;END&nbsp;Activity&nbsp;Map&nbsp;MODULE&nbsp;*/
    </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ClickMap (anteriormente ClickMap de visitantes) </td> 
   <td colname="col2"> <p>Defina la variable <a href="https://docs.adobe.com/content/help/es-ES/analytics/implementation/vars/config-vars/configuration-variables.html"  >trackInlineStats</a> en false (este es el valor predeterminado). La sintaxis es la siguiente: 
     <code>
       s.trackInlineStats=false
     </code> </p> </td> 
  </tr> 
 </tbody> 
</table>


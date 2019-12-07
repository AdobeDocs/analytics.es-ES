---
description: Pasos para empezar a realizar un seguimiento de los vínculos en Activity Map o en ClickMap preexistente.
title: Iniciar el seguimiento de vínculos
topic: Activity map
uuid: 425cb287-f76e-4430-802f-288499711ba9
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Iniciar el seguimiento de vínculos

Pasos para empezar a realizar un seguimiento de los vínculos en Activity Map o en ClickMap preexistente.

<table id="table_1745199B3105467CBA26F50B3B1CCE99"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Comienzo del seguimiento de vínculos </th> 
   <th colname="col2" class="entry"> Instrucciones </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Activity Map </td> 
   <td colname="col2"> Añada el siguiente contenido del archivo Appmeasurement.js:  
    <code>
     /*
     &nbsp;START&nbsp;Activity&nbsp;Map&nbsp;MODULE&nbsp;The&nbsp;following&nbsp;module&nbsp;enables&nbsp;Activity&nbsp;Map&nbsp;tracking&nbsp;in&nbsp;Adobe&nbsp;Analytics.&nbsp;Activity&nbsp;Map
     &nbsp;allows&nbsp;you&nbsp;to&nbsp;view&nbsp;data&nbsp;overlays&nbsp;on&nbsp;your&nbsp;links&nbsp;and&nbsp;content&nbsp;to&nbsp;understand&nbsp;how
     &nbsp;users&nbsp;engage&nbsp;with&nbsp;your&nbsp;web&nbsp;site.&nbsp;If&nbsp;you&nbsp;do&nbsp;not&nbsp;intend&nbsp;to&nbsp;use&nbsp;Activity&nbsp;Map,&nbsp;you
     &nbsp;can&nbsp;remove&nbsp;the&nbsp;following&nbsp;block&nbsp;of&nbsp;code&nbsp;from&nbsp;your&nbsp;AppMeasurement.js&nbsp;file.
     &nbsp;Additional&nbsp;documentation&nbsp;on&nbsp;how&nbsp;to&nbsp;configure&nbsp;Activity&nbsp;Map&nbsp;is&nbsp;available&nbsp;at:
     &nbsp;https://marketing.adobe.com/resources/help/en_US/analytics/activitymap/getting-started-admins.html
     */
     function&nbsp;AppMeasurement_Module_Activity&nbsp;Map(g){func
     ...
     /*&nbsp;END&nbsp;Activity&nbsp;Map&nbsp;MODULE&nbsp;*/
    </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ClickMap (anteriormente ClickMap de visitantes) </td> 
   <td colname="col2"> <p>Defina la variable <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/trackInlineStats.html"  >trackInlineStats</a> en true. La sintaxis es la siguiente: 
     <code>
       s.trackInlineStats=true
     </code> </p> </td> 
  </tr> 
 </tbody> 
</table>


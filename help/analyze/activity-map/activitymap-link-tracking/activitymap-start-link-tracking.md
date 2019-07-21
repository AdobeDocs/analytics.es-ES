---
description: Pasos para empezar a realizar un seguimiento de los vínculos en Activity Map o en ClickMap preexistente.
seo-description: Pasos para empezar a realizar un seguimiento de los vínculos en Activity Map o en ClickMap preexistente.
seo-title: Iniciar el seguimiento de vínculos
solution: Analytics
title: Iniciar el seguimiento de vínculos
topic: Activity Map
uuid: 425 cb 287-f 76 e -4430-802 f -288499711 ba 9
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

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
    <code>/* Iniciar Activity Map MODULE El siguiente módulo habilita el seguimiento de Mapa de actividades en Adobe Analytics.Mapa de actividades permite ver superposiciones de datos en los vínculos y el contenido para comprender cómo los usuarios interactúan con el sitio Web.Si no pretende utilizar Activity Map, puede eliminar el siguiente bloque de código del archivo appmeasurement. js.
  Additional documentation on how to configure Activity Map is available at:
      https://marketing.adobe.com/resources/help/en_US/analytics/activitymap/getting-started-admins.html
     */
     function AppMeasurement_Module_Activity Map(g){func
     ...
     /* END Activity Map MODULE */
    </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ClickMap (anteriormente ClickMap de visitantes) </td> 
   <td colname="col2"> <p>Defina la variable <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/trackInlineStats.html" format="https" scope="external">trackInlineStats</a> en true. The syntax reads as follows: 
     <code>
       s.trackInlineStats=true
     </code> </p> </td> 
  </tr> 
 </tbody> 
</table>


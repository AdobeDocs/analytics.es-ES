---
description: Muestra el dominio o la dirección URL desde donde los visitantes llegaron al sitio, cómo encontraron el sitio web y la cantidad de visitas al sitio provenientes de esas ubicaciones referentes.
seo-description: Muestra el dominio o la dirección URL desde donde los visitantes llegaron al sitio, cómo encontraron el sitio web y la cantidad de visitas al sitio provenientes de esas ubicaciones referentes.
seo-title: Referentes
solution: Analytics
title: Referentes
topic: 'Informes '
uuid: e 63 b 47 b 4-49 f 3-43 af -8409-3272 bec 0484 e
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Referentes

Muestra el dominio o la dirección URL desde donde los visitantes llegaron al sitio, cómo encontraron el sitio web y la cantidad de visitas al sitio provenientes de esas ubicaciones referentes.

Por ejemplo, si un visitante llega al sitio haciendo clic en un vínculo desde el sitio A, y el sitio A no está definido como parte del dominio, entonces el sitio A es el sitio referente. Durante la implementación, un asesor de implementación puede ayudar a definir los dominios y las direcciones URL que forman parte del sitio web. (Este cambio se puede hacer después de la implementación).

Todo dominio o dirección URL que no forme parte de esos dominios y direcciones URL definidos se consideran referentes. Por ejemplo, supongamos que la página web A y la página web B se agregan al filtro de URL interno, pero la página web C no. En este caso, la página web C se considera referente.

## Asignación, caducidad y valores especiales {#section_4D8CE5E111DD48FBBDCF9B5A1F16E92E}

<table id="table_EC7423532C7E44DE97B7FC0321585A2B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> Reports &amp; Analytics de marketing (SiteCatalyst) </th> 
   <th colname="col3" class="entry"> Análisis específico </th> 
   <th colname="col4" class="entry"> Almacén de datos </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Asignación de métricas </td> 
   <td colname="col2"> Más reciente </td> 
   <td colname="col3"> Más reciente </td> 
   <td colname="col4"> Más reciente </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Los valores caducan después de </td> 
   <td colname="col2"> Visita </td> 
   <td colname="col3"> Visita </td> 
   <td colname="col4"> Visita </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Límites de valores </td> 
   <td colname="col2"> Sin límites (puede cambiar en próximas versiones) </td> 
   <td colname="col3"> Sin límites (puede cambiar en próximas versiones) </td> 
   <td colname="col4"> ninguno </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Valores especiales </td> 
   <td colname="col2"> <p>"Ninguno": totales de todo el sitio que no tienen un referente durante la visita. </p> </td> 
   <td colname="col3"> <p>"Ninguno": totales de todo el sitio que no tienen un referente durante la visita. </p> </td> 
   <td colname="col4"> <p> Vacío (equivale a "Ninguno"): totales de todo el sitio que no tienen un referente durante la visita. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Notas {#section_B83A3571D64E4E7792712FAF740D7955}

* El referente, tipo de referente y dominio de referencia se establecen en la primera vista de la visita, o durante una visita cuando el referente es externo (por ejemplo, si un visitante sale del sitio, usa un motor de búsqueda y vuelve al sitio antes de que caduque la primera visita). Estos valores se establecen de forma simultánea y persisten durante toda la visita.
* Se filtran las direcciones URL internas. En el informe solo se muestran los referentes que no coinciden con los filtros de URL internas.
* La métrica correspondiente se llama Instancia de referente en los Ad Hoc Analysis.
* Los valores escritos o marcadores no se incluyen en los informes de referentes. Esto quiere decir que las visitas de todo el sitio no coincidirán con las visitas en este informe.

## Historial de informes {#section_6C0FCEA9DAF04D97BA056E153B7E4628}

<table id="table_9DFA79EC6A5A48648F2FB5418E1752DB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fecha </th> 
   <th colname="col2" class="entry"> Cambiar </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 16/1/2014 </td> 
   <td colname="col2"> El almacén de datos se ha actualizado para que coincida con la lógica usada por los Reports &amp; Analytics de marketing. Antes de esta fecha, las palabras clave de búsqueda no persistían durante la visita. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 19/6/2012 </td> 
   <td colname="col2"> <p> Antes de julio de 2012, "Ninguno" incluía todo el tráfico de móviles, escritos o marcadores, y las visitas sin JavaScript. Después de julio de 2012, "Ninguno" solo incluye visitas sin JavaScript en la primera página de la visita. </p> </td> 
  </tr> 
 </tbody> 
</table>


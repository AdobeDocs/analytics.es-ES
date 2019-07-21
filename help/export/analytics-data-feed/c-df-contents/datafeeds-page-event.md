---
description: La tabla de búsqueda para determinar el tipo de visita basándose en el valor de page_event.
keywords: Fuente de datos; page; event; page_ event; post_ page_ event
seo-description: La tabla de búsqueda para determinar el tipo de visita basándose en el valor de page_event.
seo-title: Búsqueda de eventos de página
solution: Analytics
title: Búsqueda de eventos de página
topic: Reports and Analytics
uuid: 73 af 597 c -5560-466 e -94 b 2-ddd 1 d 64797 c 8
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# Búsqueda de eventos de página

La tabla de búsqueda para determinar el tipo de visita basándose en el valor de page_event.

<table id="table_33AF375E0B41474696D7A4A92C652A5F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de visita </th> 
   <th colname="col02" class="entry"> valor de page_event </th> 
   <th colname="col2" class="entry"> valor de post_page_event </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Vistas de páginas </td> 
   <td colname="col02"> el mismo que el posterior </td> 
   <td colname="col2"> <p>0 para todas las vistas de página (llamadas <code>s.t()</code>) </p> <p>0 para las llamadas <code>trackState</code> desde los SDK para móviles. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Seguimiento de vínculos </td> 
   <td colname="col02"> <p>10 para "otro vínculo" </p> <p>10 para llamadas <code>trackAction</code> y del ciclo vital desde los SDK para móviles. </p> <p>11 para "vínculo de descarga" </p> <p>12 para "vínculo externo o de salida" </p> </td> 
   <td colname="col2"> <p>100 para "otro vínculo" </p> <p>100 para llamadas <code>trackAction</code> y del ciclo vital desde los SDK para móviles. </p> <p>101 para "vínculo de descarga" </p> <p>102 para "vínculo externo o de salida" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Vídeo de hitos </td> 
   <td colname="col02"> 
    <!--<p>30 - Legacy full media tracking event at the end of the video playback (no longer supported)</p>--> <p>31: evento de inicio de recursos multimedia </p> <p>32: solo el evento de actualización de medios (no realiza ninguna evar ni el procesamiento de otra variable) </p> <p>33: evento de actualización de recursos multimedia + de otra variable (incluye eVar y el procesamiento de otra variable) </p> </td> 
   <td colname="col2"> 
    <!--<p> 75 - Legacy full media tracking event at theend of the video playback (no longer supported)</p>--> <p> 76: evento de inicio de recursos multimedia </p> <p>77: único evento de actualización de recursos multimedia (no realiza ninguna eVar ni el procesamiento de otra variable) </p> <p>78: evento de actualización de recursos multimedia + de otra variable (incluye eVar y el procesamiento de otra variable) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vídeo de monitoreo del funcionamiento </p> </td> 
   <td colname="col02"> el mismo que el posterior </td> 
   <td colname="col2"> <p> 50 = inicio del flujo de recursos multimedia (que no sea Primetime) </p> <p> 51 = cierre del flujo de recursos multimedia (que no sea Primetime), completo o finalizado </p> <p> 52 = limpieza del flujo de recursos multimedia (que no sea Primetime) </p> <p> 53 = mantener vivo el flujo de recursos multimedia (que no sea Primetime) </p> <p> 54 = inicio publicitario del flujo de recursos multimedia (que no sean Primetime) </p> <p> 55 = cierre publicitario del flujo de recursos multimedia (que no sea Primetime), completo o finalizado </p> <p> 56 = limpieza publicitaria del flujo de recursos multimedia (que no sean Primetime) </p> <p> 60 = inicio del flujo de recursos multimedia Primetime </p> <p> 61 = cierre del flujo de recursos multimedia Primetime (completo o finalizado) </p> <p> 62 = limpieza del flujo de recursos multimedia Primetime </p> <p> 63 = mantener vivo el flujo de recursos multimedia Primetime </p> <p> 64 = inicio publicitario del flujo de recursos multimedia Primetime </p> <p> 65 = cierre publicitario del flujo de recursos multimedia Primetime (completo o finalizado) </p> <p> 66 = limpieza publicitaria del flujo de recursos multimedia Primetime </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Survey </td> 
   <td colname="col02"> 40 </td> 
   <td colname="col2"> 80 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Analytics para Target </td> 
   <td colname="col02"> 70: indica una visita que incluye datos de actividad de Target. Se aplica a visitas asociadas o no asociadas a una llamada de Analytics. </td> 
   <td colname="col2"> </td> 
  </tr> 
 </tbody> 
</table>


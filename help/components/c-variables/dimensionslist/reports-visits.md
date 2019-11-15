---
description: Muestra la cantidad de visitas realizadas al sitio web durante un período determinado.
solution: Analytics
title: Visitas
topic: Reports
uuid: ff65bddf-fb65-4cf0-8aae-4ab59c2bb0a7
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Visitas

Muestra la cantidad de visitas realizadas al sitio web durante un período determinado.

**Propiedades de los informes**

* Una visita se define como la secuencia consecutiva de vistas de la página sin una interrupción de 30 minutos, o 12 horas de actividad continua.
* Cuando caduca una visita, se inicia una nueva en cualquier solicitud de imagen posterior.
* Normalmente, un visitante contiene al menos una visita (aunque probablemente más de una).
* El inicio de una visita se produce en la primera solicitud de imagen procedente de un visitante nuevo, o después de que la visita del usuario existente haya caducado. Es lo que se identifica como página de entrada.
* El final de una visita es la última solicitud de imagen antes de que la visita caduque. Es lo que se identifica como página de salida.

   Consulte [Informes de entradas y salidas](/help/components/c-variables/dimensionslist/reports-entries-exits.md).
* Los desgloses por hora se basan en el huso horario del grupo de informes.
* Este informe no contiene elementos de línea. Solo se puede ver en formato de tendencias.
* Se puede aplicar una granularidad de hora, día, semana, mes, trimestre y año. Estas configuraciones de granularidad están disponibles en función del intervalo de fechas de los informes.

Consulte [Métrica de visitas](/help/components/c-variables/c-metrics/metrics-visit.md) para obtener más información sobre el modo en el que Experience Cloud procesa esta métrica.

**Información del informe específica de productos**

<table id="table_3138CA443CAC4F55838216E8B8786EE2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Producto </th> 
   <th colname="col2" class="entry"> Navegación </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Reports &amp; Analytics </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> Métricas del sitio</span> &gt; <span class="uicontrol">Visitas</span> </p> <p>Puede ejecutar un <span class="wintitle">informe de visitas</span> sobre una página seleccionada. Las visitas que se extienden más allá de la media noche se contabilizan tanto en el día en que se inició la visita como en el día en que finalizó. No obstante, en el total del intervalo de fechas dado se anula la duplicación. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Ad Hoc Analysis  </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> Informes</span> &gt; <span class="uicontrol">Métricas del sitio</span> &gt; <span class="uicontrol">Visitas</span> </p> 
    <ul id="ul_73FEE02C129041D6A63F2DB07676960F"> 
     <li id="li_CC3BB22DE97941EB8032BE4421FFC173"> Puede desglosar cada elemento de este informe según casi todos los demás informes y variables, lo que permite ver los desgloses con cualquier granularidad. </li> 
     <li id="li_D53D480D73264D47945C9E1202B7BD4F">Las visitas que se extienden más allá de la media noche se contabilizan tanto en el día en que se inició la visita como en el día en que finalizó. No obstante, en el total del intervalo de fechas dado se anula la duplicación. </li> 
     <li id="li_B8BCC584F95B407DB87F5EA57CC88F62">Se pueden usar todas las métricas de conversión y tráfico de este informe, así como distintas asignaciones para todas las métricas de conversión. </li> 
     <li id="li_0F342D3DCFF44ABAB79BD0F9E7F43E1E">Este informe puede utilizar varios segmentos muy avanzados. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>


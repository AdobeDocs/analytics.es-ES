---
description: Adobe Analytics y Adobe Audience Manager cuentan con métricas de visitantes con definiciones similares, pero que no están perfectamente alineadas por distintos motivos.
title: Diferencias en la contabilización de visitantes
uuid: c3bbb887-bd02-4c1c-9a2b-64811c0ef56a
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Diferencias en la contabilización de visitantes

Adobe Analytics y Adobe Audience Manager cuentan con métricas de visitantes con definiciones similares, pero que no están perfectamente alineadas por distintos motivos.

Las métricas de visitante son:

<table id="table_F9FE107A89934C3B854C55D7D76AC6E8"> 
 <thead> 
  <tr> 
   <th colname="col2" class="entry"> Métrica </th> 
   <th colname="col3" class="entry"> Definición </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col2"> <p><a href="https://docs.adobe.com/content/help/es-ES/audience-manager/user-guide/features/segments/segment-builder-data.html"  > AAM: Propagación total de segmentos</a> </p> </td> 
   <td colname="col3"> <p>Se trata del número de dispositivos (Experience Cloud ID) que formaban parte de su segmento durante el período retroactivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><a href="https://docs.adobe.com/content/help/es-ES/audience-manager/user-guide/features/segments/segment-builder-data.html"  > AAM: Propagación de segmentos en tiempo real</a> </p> </td> 
   <td colname="col3"> <p>Se trata del número de dispositivos (Experience Cloud ID) que formaban parte de su segmento y han alcanzado sus propiedades durante el período retroactivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Analytics: Visitantes exclusivos </p> </td> 
   <td colname="col3"> <p>Muestra el número de visitantes exclusivos que alcanzaron sus propiedades durante el tiempo de realización del informe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Analytics: Visitantes con Experience Cloud ID </p> </td> 
   <td colname="col3"> <p>Muestra el número de visitantes exclusivos con un Experience Cloud ID que han alcanzado sus propiedades durante el período retroactivo. </p> </td> 
  </tr> 
 </tbody> 
</table>

Las métricas AAM: Propagación de segmentos en tiempo real y Analytics: Visitantes con Experience Cloud ID usadas dentro de los informes de Audience Analytics serán las más parecidas. No obstante, y debido a diversos factores, habrá pequeñas discrepancias entre ellos. Entre estos factores se cuentan los siguientes:

<table id="table_A391B37CC077456F8BB83BAA3C640EF6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Factor </th> 
   <th colname="col2" class="entry"> AAM: Propagación de segmentos en tiempo real </th> 
   <th colname="col3" class="entry"> Analytics: Visitantes con Experience Cloud ID </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Zona horaria </p> </td> 
   <td colname="col2"> <p>UTC (tiempo universal coordinado) </p> </td> 
   <td colname="col3"> <p>Se especifica por grupo de informes </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Filtros personalizados </p> </td> 
   <td colname="col2"> <p>No </p> </td> 
   <td colname="col3"> <p>Sí, p. ej., filtros, filtros bot </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Límite de 150 segmentos </p> </td> 
   <td colname="col2"> <p>No </p> </td> 
   <td colname="col3"> <p>Sí  - Los recuentos de Analytics pueden variar hasta un 5% debido al límite de integración de 150 segmentos. El mensaje “Alcanzado límite de audiencias” aparecerá en la dimensión Nombre de audiencia si se ha truncado. </p> </td> 
  </tr> 
 </tbody> 
</table>

Consulte [Explicación de los segmentos en Analytics y Audience Manager](/help/integrate/c-audience-analytics/aam-analytics-segments.md) para comprender mejor las pequeñas diferencias entre Analytics y Audience Manager en cuanto a datos y segmentación.

---
description: Adobe Analytics y Adobe Audience Manager cuentan con métricas de visitantes con definiciones similares, pero que no están perfectamente alineadas por distintos motivos.
title: Diferencias en la contabilización de visitantes
feature: Audience Analytics
exl-id: be5a935a-c3a2-4ab4-8cd7-ed54a37932c8
TQID: https://experienceleague.adobe.com/ksfYYDZ6G9vH7WEZVh-JsN93Rl-jsZTe9-CQADSwnfI
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 312
ht-degree: 46%

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
   <td colname="col2"> <p><a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/segments/segment-builder-data.html?lang=es"  > Adobe Audience Manager: Propagación total de segmentos</a> </p> </td> 
   <td colname="col3"> <p>Se trata del número de dispositivos (Experience Cloud ID) que formaban parte de su segmento durante el período retroactivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/segments/segment-builder-data.html?lang=es"  > Adobe Audience Manager: Propagación de segmentos en tiempo real</a> </p> </td> 
   <td colname="col3"> <p>Recuento de dispositivos (Experience Cloud ID) que eran miembros de su segmento y llegaron a sus propiedades durante el período retroactivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Analytics: Visitantes únicos </p> </td> 
   <td colname="col3"> <p>Muestra el número de visitantes únicos que llegaron a sus propiedades durante la ventana de creación de informes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Analytics: Visitantes con Experience Cloud ID </p> </td> 
   <td colname="col3"> <p>Muestra el número de visitantes únicos con un Experience Cloud ID que llegaron a sus propiedades durante la ventana de creación de informes. </p> </td> 
  </tr> 
 </tbody> 
</table>

Los visitantes de Adobe Audience Manager Real-time Segment Population y Analytics con Experience Cloud ID utilizados en los informes de Audience Analytics serán los más similares. Sin embargo, a corto plazo, debido a varios factores, habrá pequeñas discrepancias entre ellos. Los factores que contribuyen son:

<table id="table_A391B37CC077456F8BB83BAA3C640EF6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Factor </th> 
   <th colname="col2" class="entry"> Adobe Audience Manager: Propagación de segmentos en tiempo real </th> 
   <th colname="col3" class="entry"> Analytics: Visitantes con Experience Cloud ID </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Zona horaria </p> </td> 
   <td colname="col2"> <p>UTC (hora universal coordinada) </p> </td> 
   <td colname="col3"> <p>Especificado por grupo de informes </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Filtros personalizados </p> </td> 
   <td colname="col2"> <p>No </p> </td> 
   <td colname="col3"> <p>Sí, por ejemplo, filtros de direcciones IP, filtros bot </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Límite de 150 segmentos </p> </td> 
   <td colname="col2"> <p>No </p> </td> 
   <td colname="col3"> <p>Sí: los recuentos de Analytics pueden verse afectados hasta un 5 % por el límite de integración de 150 segmentos. El mensaje “Alcanzado límite de públicos” aparecerá en la dimensión Nombre de público si se ha truncado. </p> </td> 
  </tr> 
 </tbody> 
</table>

Consulte [Explicación de los segmentos en Analytics y Audience Manager](/help/integrate/c-audience-analytics/aam-analytics-segments.md) para comprender mejor las pequeñas diferencias entre Analytics y Audience Manager en cuanto a datos y segmentación.

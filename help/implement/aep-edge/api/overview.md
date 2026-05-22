---
title: Implementar Adobe Analytics mediante la API de Edge Network de Adobe Experience Platform
description: Utilice la API de Edge Network de Adobe Experience Platform para enviar datos a Adobe Analytics.
exl-id: 1ede95b7-4f17-4d69-aba6-62b253b6693a
feature: Implementation Basics
role: Admin, Developer, Leader
TQID: 'https://experienceleague.adobe.com/lvnplKx6dPwmmbZWgSShGvZXD2TtUoigi-HNiKutZSg'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
subfeature_v2:
  - id: b3e5f43e-2e2f-43c0-810a-044a5f91e31a
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 332
ht-degree: 42%

---

# Implementar Adobe Analytics mediante la API de Edge Network de Adobe Experience Platform

Normalmente, se utiliza la API de Edge Network de Experience Platform para recopilar datos del lado del servidor en lugar de del lado del cliente, y también para recopilar datos de dispositivos como dispositivos de IoT, descodificadores y aplicaciones de escritorio. A continuación, envía esos datos a la red de Edge y a servicios como Adobe Analytics.

Tenga en cuenta también la API de Edge Network cuando necesite que los datos confidenciales se recopilen de forma segura y se autentiquen en la red. Consulte [Autenticación](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/authentication.html) para obtener más información.

Una información general de alto nivel de las tareas de implementación:

![Adobe Analytics mediante el flujo de trabajo de extensión de Analytics](../../assets/edge-network-server-api-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>Tarea</b></th><th style="width:35%"><b>Más información</b></th>
</tr>

<tr>
<td>1</td>
<td>Asegúrese de haber <b>definido un grupo de informes</b>.</td>
<td><a href="../../../admin/tools/manage-rs/report-suites-admin.md">Administrador del grupo de informes</a></td>
</tr>

<tr>
<td>2</td>
<td><b>Configurar esquemas</b>. Para estandarizar la recopilación de datos para su uso en todas las aplicaciones que aprovechan Adobe Experience Platform, Adobe ha creado el estándar abierto y documentado públicamente, Modelo de datos de experiencia (XDM).</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=es">Resumen de IU de esquemas</a></td>
</tr>

<tr>
<td>3</td>
<td><b>Configurar una secuencia de datos</b>. Un conjunto de datos representa la configuración del lado del servidor al utilizar la API de la API de Adobe Experience Platform Edge Network.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=es">Configurar una secuencia de datos<a></td> 
</tr>

<tr>
<td>4</td>
<td><b>Implemente y pruebe la recopilación de datos</b> mediante las API de recopilación de datos de evento único y de evento por lotes.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/interactive-data-collection.html?lang=es">Recopilación de datos de un solo evento</a><br/><a href="https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/non-interactive-data-collection.html">Recopilación de datos de eventos por lotes</a>
</tr>

<td>5</td>
<td><b>Agregar un servicio de Adobe Analytics</b> a su secuencia de datos. Ese servicio controla si los datos se envían a Adobe Analytics y cómo se hacen.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/interacting-other-adobe-solutions/interacting-adobe-analytics.html?lang=es">Interactuar con Adobe Analytics</a></td>
</tr>


</table>

Consulte [Documentación de la API de Edge Network](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/overview.html?lang=es) para obtener más información.


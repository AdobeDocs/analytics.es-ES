---
title: Implementar Adobe Analytics mediante la API del servidor de red perimetral de Adobe Experience Platform
description: Utilice la API del servidor de red perimetral de Adobe Experience Platform para enviar datos a Adobe Analytics.
exl-id: 1ede95b7-4f17-4d69-aba6-62b253b6693a
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 33%

---

# Implementar Adobe Analytics mediante la API del servidor de red perimetral de Adobe Experience Platform

Normalmente, se utiliza la API del servidor de red perimetral de Experience Platform para recopilar datos de dispositivos como dispositivos de IoT, descodificadores y aplicaciones de escritorio. A continuación, envíe esos datos a la red de Edge y, luego, a servicios como Adobe Analytics.

Tenga en cuenta también la API del servidor de red perimetral cuando necesite que los datos confidenciales se recopilen de forma segura y se autentiquen en la red. Consulte [Autenticación](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/authentication.html?lang=en) para obtener más información.

Una información general de alto nivel de las tareas de implementación:

![Adobe Analytics mediante el flujo de trabajo de extensión de Analytics](../../assets/edge-network-server-api.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>Tarea</b></th><th style="width:35%"><b>Más información</b></th>
</tr>

<tr>
<td>1</td>
<td>Asegúrese de haber <b>definido un grupo de informes</b>.</td>
<td><a href="../../../admin/admin/c-manage-report-suites/report-suites-admin.md">Administrador del grupo de informes</a></td>
</tr>

<tr>
<td>2</td>
<td><b>Configuración de esquemas</b>. Para estandarizar la recopilación de datos para su uso en todas las aplicaciones que aprovechan Adobe Experience Platform, Adobe ha creado el estándar abierto y documentado públicamente, Experience Data Model (XDM).</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=es">Resumen de IU de esquemas</a></td>
</tr>

<tr>
<td>3</td>
<td><b>Configurar una secuencia de datos</b>. Un conjunto de datos representa la configuración del lado del servidor al utilizar la API de la API de Adobe Experience Platform Edge Network.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=es">Configurar una secuencia de datos<a></td> 
</tr>

<tr>
<td>4</td>
<td><b>Implementación y prueba de la recopilación de datos</b> mediante las API de recopilación de datos de evento único y de evento por lotes.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/interactive-data-collection.html?lang=en">Recopilación de datos de un solo evento</a><br/><a href="https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/non-interactive-data-collection.html?lang=en">Recopilación de datos de eventos por lotes</a>
</tr>

<td>5</td>
<td><b>Agregar un servicio de Adobe Analytics</b> a su secuencia de datos. Ese servicio controla si los datos se envían a Adobe Analytics y cómo se hacen.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/interacting-other-adobe-solutions/interacting-adobe-analytics.html?lang=ens">Interactuar con Adobe Analytics</a></td>
</tr>


</table>

Consulte [Documentación de API del servidor de red perimetral](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/overview.html?lang=es)y un ejemplo [integración con Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/interacting-other-adobe-solutions/interacting-adobe-analytics.html?lang=es) para obtener más información.


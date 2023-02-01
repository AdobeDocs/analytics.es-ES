---
title: Implementar Adobe Analytics mediante el SDK móvil de Adobe Experience Platform
description: Utilice la extensión del SDK móvil en la recopilación de datos de Adobe Experience Platform para enviar datos a Adobe Analytics.
source-git-commit: 97bff355a5d9bb737d510221b63ba1321aaf5812
workflow-type: tm+mt
source-wordcount: '632'
ht-degree: 28%

---

# Implementar Adobe Analytics mediante el SDK móvil de Adobe Experience Platform

El SDK móvil de Adobe Experience Platform ayuda a impulsar las soluciones y los servicios Experience Cloud de los Adobes en sus aplicaciones móviles. Está disponible para Android™, iOS y varios marcos de desarrollo entre plataformas. La configuración se administra mediante la recopilación de datos de Adobe Experience Platform.
>[!IMPORTANT]
>
>También hay una extensión de Adobe Analytics disponible en la recopilación de datos de Adobe Experience Platform. Si instala esta extensión, no aprovecha XDM ni la red perimetral.

## SDK de Adobe Experience Platform

Una visión general de alto nivel de las tareas de implementación:

![Adobe Analytics mediante el flujo de trabajo de extensión de Analytics](../../assets/mobilesdk-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>Tarea</b></th><th style="width:35%"><b>Más información</b></th>
</tr>

<tr>
<td>1</td>
<td>Asegúrese de que <b>definición de un grupo de informes</b>.</td>
<td><a href="../../../admin/admin/c-manage-report-suites/report-suites-admin.md">Administrador del grupo de informes</a></td>
</tr>

<tr>
<td>2</td>
<td><b>Configuración de esquemas y conjuntos de datos</b>. Para estandarizar la recopilación de datos para su uso en todas las aplicaciones que aprovechan Adobe Experience Platform, Adobe ha creado el estándar abierto y documentado públicamente, Experience Data Model (XDM).</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=es">Información general sobre la interfaz de usuario de Esquemas</a> y <a href="https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=es">Información general sobre la interfaz de usuario de conjuntos de datos</a></td>
</tr>

<tr>
<td>3</td>
<td><b>Configurar un conjunto de datos</b>. Un conjunto de datos representa la configuración del lado del servidor al implementar el SDK web de Adobe Experience Platform.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en">Configurar un conjunto de datos<a></td> 
</tr>

<td>4</td>
<td><b>Añadir un servicio de Adobe Analytics</b> al conjunto de datos. Ese servicio controla si los datos se envían a Adobe Analytics y cómo se hacen.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en#analytics">Añadir el servicio Adobe Analytics a un conjunto de datos</a></td>
</tr>

<tr>
<td>5</td>
<td><b>Crear una propiedad móvil</b>. Una propiedad es un contenedor que se rellena con extensiones, reglas, elementos de datos y bibliotecas.</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/">Configuración de una propiedad móvil</a></tr>

<tr>
<td>6</td>
<td><b>Instalación de la extensión Adobe Experience Platform Edge Network</b> en la propiedad mobile tag y configure el conjunto de datos en la extensión .</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/edge-network/">Adobe Experience Platform Edge Network</a>
</tr>

<tr>
<td>7</td>
<td><b>Uso del código en la aplicación</b> para registrar las extensiones necesarias y cargar la configuración de la etiqueta.</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#set-up-the-configuration">Configuración</a></td>
</tr>

<tr>
<td>8</td>
<td><b>Implementación y funcionalidad de prueba</b> mediante la combinación de elementos de datos de la etiqueta, reglas, extensiones adicionales y llamadas de API de SDK en la aplicación. Inspect, valide y depure la recopilación de datos y experiencias para su aplicación móvil.</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#use-the-sample-application">Uso de la aplicación de ejemplo</a>
</tr>

<tr>
<td>9</td>
<td><b>Ampliar y validar la implementación de la aplicación móvil</b> antes de llevarlo a producción.</td>
<td></td> 
</tr>

</table>


## Extensión de Adobe Analytics.

Una visión general de alto nivel de las tareas de implementación:

![Adobe Analytics mediante el flujo de trabajo de extensión de Analytics](../../assets/mobilesdk-analytics-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>Tarea</b></th><th style="width:35%"><b>Más información</b></th>
</tr>

<tr>
<td>1</td>
<td>Asegúrese de que <b>definición de un grupo de informes</b>.</td>
<td><a href="../../../admin/admin/c-manage-report-suites/report-suites-admin.md">Administrador del grupo de informes</a></td>
</tr>

<tr>
<td>2</td>
<td><b>Configuración de esquemas y conjuntos de datos</b>. Para estandarizar la recopilación de datos para su uso en todas las aplicaciones que aprovechan Adobe Experience Platform, Adobe ha creado el estándar abierto y documentado públicamente, Experience Data Model (XDM).</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=es">Información general sobre la interfaz de usuario de Esquemas</a> y <a href="https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=es">Información general sobre la interfaz de usuario de conjuntos de datos</a></td>
</tr>

<tr>
<td>3</td>
<td><b>Instalación de la extensión de Adobe Analytics</b> en la propiedad mobile tag y configure la extensión para que apunte al grupo de informes.</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/adobe-analytics/">Extensión de Adobe Analytics para la propiedad móvil</a>
</tr>

<tr>
<td>4</td>
<td><b>Uso del código en la aplicación</b> para registrar las extensiones necesarias y cargar la configuración de la etiqueta.</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#set-up-the-configuration">Configuración</a></td>
</tr>

<tr>
<td>5</td>
<td><b>Implementación y funcionalidad de prueba</b> mediante la combinación de elementos de datos de la etiqueta, reglas, extensiones adicionales y llamadas de API de SDK en la aplicación. Inspect, valide y depure la recopilación de datos y experiencias para su aplicación móvil.</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#use-the-sample-application">Uso de la aplicación de ejemplo</a>
</tr>

<tr>
<td>6</td>
<td><b>Ampliar y validar la implementación de la aplicación móvil</b> antes de llevarlo a producción.</td>
<td></td> 
</tr>

</table>

## Recursos adicionales

- [Documentación de etiquetas](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=es#)

- [Documentación de Mobile SDK](https://developer.adobe.com/client-sdks/documentation/)




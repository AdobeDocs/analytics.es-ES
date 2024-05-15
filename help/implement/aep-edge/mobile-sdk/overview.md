---
title: Implementar Adobe Analytics mediante el SDK móvil de Adobe Experience Platform
description: Utilice la extensión del SDK móvil en la recopilación de datos de Adobe Experience Platform para enviar datos a Adobe Analytics.
exl-id: 516e9a1e-caa7-4f8a-ab8c-6404e9242ccb
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 8b585a1a05b5fcabd343da52a4b6f05fea8fd86f
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 99%

---

# Implementar Adobe Analytics mediante el SDK móvil de Adobe Experience Platform

El SDK móvil de Adobe Experience Platform ayuda a impulsar las soluciones y los servicios Experience Cloud de los Adobes en sus aplicaciones móviles. Está disponible para Android™, iOS y varios marcos de desarrollo en plataformas múltiples. La configuración se administra mediante la recopilación de datos de Adobe Experience Platform.

>[!IMPORTANT]
>
>También hay una extensión de Adobe Analytics disponible en la recopilación de datos de Adobe Experience Platform. Si instala esta extensión, no aprovecha XDM ni la red perimetral.

## SDK de Adobe Experience Platform

Una información general de alto nivel de las tareas de implementación:

![Adobe Analytics mediante el flujo de trabajo de extensión de Analytics](../../assets/mobilesdk-annotated.png)

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
<td><b>Configurar una secuencia de datos</b>. Una secuencia de datos representa la configuración del lado del servidor al implementar los SDK web de Adobe Experience Platform.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=es">Configurar una secuencia de datos<a></td> 
</tr>

<td>3</td>
<td><b>Agregar un servicio de Adobe Analytics</b> a su secuencia de datos. Ese servicio controla si los datos se envían a Adobe Analytics y cómo se hacen.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html#analytics">Agregar el servicio Adobe Analytics a una secuencia de datos</a></td>
</tr>

<tr>
<td>4</td>
<td><b>Cree una propiedad móvil</b>. Una propiedad es un contenedor que se rellena con extensiones, reglas, elementos de datos y bibliotecas.</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/">Configuración de una propiedad móvil</a></tr>

<tr>
<td>5</td>
<td><b>Instale la extensión Adobe Experience Platform Edge Network</b> en la propiedad de etiqueta móvil y configure la secuencia de datos en la extensión.</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/edge-network/">Adobe Experience Platform Edge Network</a>
</tr>

<tr>
<td>6</td>
<td><b>Use el código en la aplicación</b> para registrar las extensiones necesarias y cargar la configuración de la etiqueta.</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#set-up-the-configuration">Establecimiento de la configuración</a></td>
</tr>

<tr>
<td>7</td>
<td><b>Implemente y pruebe la funcionalidad</b> mediante la combinación de elementos de datos de etiquetas, reglas, extensiones adicionales y llamadas a la API del SDK en su aplicación. Inspeccione, valide y depure la recopilación de datos y experiencias para su aplicación móvil.</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#use-the-sample-application">Uso de la aplicación de muestra</a>
</tr>

<tr>
<td>8</td>
<td><b>Amplíe y valide la implementación de su aplicación móvil</b> antes de pasarla a la producción.</td>
<td></td> 
</tr>

</table>


## Extensión de Adobe Analytics.

Una información general de alto nivel de las tareas de implementación:

![Adobe Analytics mediante el flujo de trabajo de extensión de Analytics](../../assets/mobilesdk-analytics-annotated.png)

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
<td><b>Instale la extensión de Adobe Analytics</b> en la propiedad de etiqueta móvil y configúrela para que apunte al grupo de informes.</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/adobe-analytics/">Extensión de Adobe Analytics para la propiedad móvil</a>
</tr>

<tr>
<td>3</td>
<td><b>Use el código en la aplicación</b> para registrar las extensiones necesarias y cargar la configuración de la etiqueta.</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#set-up-the-configuration">Establecimiento de la configuración</a></td>
</tr>

<tr>
<td>4</td>
<td><b>Implemente y pruebe la funcionalidad</b> mediante la combinación de elementos de datos de etiquetas, reglas, extensiones adicionales y llamadas a la API del SDK en su aplicación. Inspeccione, valide y depure la recopilación de datos y experiencias para su aplicación móvil.</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#use-the-sample-application">Uso de la aplicación de muestra</a>
</tr>

<tr>
<td>5</td>
<td><b>Amplíe y valide la implementación de su aplicación móvil</b> antes de pasarla a producción.</td>
<td></td> 
</tr>

</table>

## Recursos adicionales

- [Documentación sobre etiquetas](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=es#)

- [Documentación de Mobile SDK](https://developer.adobe.com/client-sdks/documentation/)

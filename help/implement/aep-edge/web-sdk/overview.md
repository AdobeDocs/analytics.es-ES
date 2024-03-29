---
title: Implementar Adobe Analytics mediante el SDK web de Adobe Experience Platform
description: Utilice la extensión del SDK web en la recopilación de datos de Adobe Experience Platform para enviar datos a Adobe Analytics.
exl-id: 97f8d650-247f-4386-b4d2-699f3dab0467
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 10ecae46424758fc5b19b58b733b49bb23cda222
workflow-type: tm+mt
source-wordcount: '670'
ht-degree: 72%

---

# Implementar Adobe Analytics mediante el SDK web de Adobe Experience Platform

Puede utilizar el [SDK web de Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/web-sdk/home.html) para enviar datos a Adobe Analytics. Este método de implementación funciona traduciendo el [Modelo de datos de experiencia (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=es) en un formato utilizado por Analytics. Puede enviar datos a Adobe Experience Platform Edge Network mediante la biblioteca JavaScript del SDK web o la extensión de etiqueta del SDK web.

## SDK web

Una información general de alto nivel de las tareas de implementación:

![Implementar Adobe Analytics mediante el flujo de trabajo del SDK web como se describe en esta sección.](../../assets/websdk-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>Tarea</b></th><th style="width:35%"><b>Más información</b></th>
</tr>

<tr>
<td>1</td>
<td>Asegúrese de haber <b>definido un grupo de informes</b>.</td>
<td><a href="/help/admin/admin/c-manage-report-suites/report-suites-admin.md">Administrador del grupo de informes</a></td>
</tr>

<tr>
<td>2</td>
<td><b>Configuración de esquemas</b>. Para estandarizar la recopilación de datos para su uso en todas las aplicaciones que aprovechan Adobe Experience Platform, Adobe ha creado el estándar abierto y documentado públicamente, Experience Data Model (XDM).</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=es">Resumen de IU de esquemas</a></td>
</tr>

<tr>
<td>3</td>
<td><b>Creación de una capa de datos</b> para administrar el seguimiento de los datos del sitio web.</td>
<td><a href="../../prepare/data-layer.md">Creación de una capa de datos</a></td>
</tr>

<tr>
<td> 4</td>
<td><b>Instale la versión independiente precompilada</b>. Puede hacer referencia a la biblioteca (<code>alloy.js</code>) en la red de distribución de contenido (CDN) directamente en su página, o bien, descargue y aloje en su propia infraestructura. Alternativamente, puede utilizar el paquete NPM.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/web-sdk/install/library.html">Instalación de la versión independiente precompilada</a> y <a href="https://experienceleague.adobe.com/docs/experience-platform/web-sdk/install/npm.html">Uso del paquete NPM</a></td>
</tr>

<tr>
<td>5</td>
<td><b>Configurar una secuencia de datos</b>. Una secuencia de datos representa la configuración del lado del servidor al implementar los SDK web de Adobe Experience Platform.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=es">Configurar una secuencia de datos<a></td> 
</tr>

<td>6</td>
<td><b>Agregar un servicio de Adobe Analytics</b> a su secuencia de datos. Este servicio controla si los datos se envían a Adobe Analytics y cómo, y a qué grupo o grupos de informes se envían específicamente.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html#analytics">Agregar el servicio Adobe Analytics a una secuencia de datos</a></td>
</tr>

<tr>
<td>7</td>
<td><b>Configurar el SDK web</b>. Asegúrese de que la biblioteca que instaló en el paso 4 esté configurada correctamente con el ID de secuencia de datos (anteriormente conocido como ID de configuración de Edge ( ).<code>edgeConfigId</code>)), id de organización (<code>orgId</code>) y otras opciones disponibles. Asegúrese de que la asignación de variables sea correcta. </td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/web-sdk/commands/configure/overview.html">Configuración del SDK web</a><br/><a href="../xdm-var-mapping.md">Asignación de variables de objeto XDM</a></td>
</tr>

<tr>
<td>8</td>
<td><b>Ejecutar comandos</b> o <b>seguimiento de eventos</b>. Una vez implementado el código base en la página web, puede empezar a ejecutar comandos y rastrear eventos con el SDK.
</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/web-sdk/commands/sendevent/overview.html">Envío de eventos</a></td>
</tr>

<tr>
<td>9</td><td><b>Ampliación y validación de la implementación</b> antes de llevarlo a producción.</td><td></td> 
</tr>
</table>


## Extensión del SDK web

Una información general de alto nivel de las tareas de implementación:

![Implementar Adobe Analytics mediante el flujo de trabajo de extensión del SDK web como se describe en esta sección.](../../assets/websdk-extension-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>Tarea</b></th><th style="width:35%"><b>Más información</b></th>
</tr>

<tr>
<td>1</td>
<td>Asegúrese de haber <b>definido un grupo de informes</b>.</td>
<td><a href="/help/admin/admin/c-manage-report-suites/report-suites-admin.md">Administrador del grupo de informes</a></td>
</tr>

<tr>
<td>2</td>
<td><b>Configuración de esquemas</b>. Para estandarizar la recopilación de datos para su uso en todas las aplicaciones que aprovechan Adobe Experience Platform, Adobe ha creado el estándar abierto y documentado públicamente, Experience Data Model (XDM).</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=es">Resumen de IU de esquemas</a></td>
</tr>

<tr>
<td>3</td>
<td><b>Creación de una capa de datos</b> para administrar el seguimiento de los datos del sitio web.</td>
<td><a href="../../prepare/data-layer.md">Creación de una capa de datos</a></td>
</tr>

<tr>
<td>4</td>
<td><b>Configurar una secuencia de datos</b>. Una secuencia de datos representa la configuración del lado del servidor al implementar los SDK web de Adobe Experience Platform.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=es">Configurar una secuencia de datos<a></td> 
</tr>

<tr>
<td>5</td> 
<td><b>Agregar un servicio de Adobe Analytics</b> a su secuencia de datos. Este servicio controla si los datos se envían a Adobe Analytics y cómo, y a qué grupo o grupos de informes se envían específicamente.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html#analytics">Agregar el servicio Adobe Analytics a una secuencia de datos</a></td>
</tr>

<tr>
<td>6</td>
<td><b>Crear una propiedad de etiquetas</b>: las propiedades son contenedores generales que se utilizan para hacer referencia a los datos de administración de etiquetas.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/admin/companies-and-properties.html#for-web">Creación o configuración de una propiedad de etiqueta para la web</a></td>
</tr>

<tr>
<td>7</td> 
<td><b>Instalación y configuración de la extensión del SDK web</b> en la propiedad de etiqueta. Configure la extensión del SDK web para enviar datos a la secuencia de datos configurada en el paso 4.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/sdk/overview.html?lang=es">Información general sobre la extensión de SDK web de Adobe Experience Platform</a></td>
</tr>

<tr>
<td>8</td>
<td><b>Repetición, validación y publicación</b> para producción. Incruste el código para incluir la propiedad de etiquetas en las páginas del sitio web. A continuación, utilice elementos de datos, reglas, etc. para personalizar la implementación.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html#embed-code">Código incrustado</a><br/><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=es">Resumen de publicación</a></td>
</tr>

</table>


## Recursos adicionales

Las etiquetas se pueden personalizar en gran medida. Obtenga más información sobre cómo aprovechar al máximo Adobe Analytics mediante la inclusión de los datos adecuados en la implementación.

- [Documentación de etiquetas](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=es#): descubra cómo funciona la interfaz y qué extensiones están disponibles.

- [Documentación del SDK web de Adobe Experience Platform](https://experienceleague.adobe.com/docs/web-sdk.html?lang=es)

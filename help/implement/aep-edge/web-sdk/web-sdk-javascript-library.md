---
title: Enviar datos a Adobe Analytics mediante la biblioteca JavaScript del SDK web
description: Comience con una implementación limpia del SDK web para enviar datos a Adobe Analytics mediante la biblioteca JavaScript.
exl-id: 593b63ac-e411-4f88-af7e-78f026269ec0
source-git-commit: bfafc1f8eddf82b34fb45e3d6197213f0cee0d97
workflow-type: tm+mt
source-wordcount: '1070'
ht-degree: 18%

---

# Enviar datos a Adobe Analytics mediante la biblioteca JavaScript del SDK web

Esta ruta de implementación implica una nueva instalación del SDK web mediante la biblioteca JavaScript del SDK web. Otras rutas de implementación se tratan en páginas independientes:

* [Extensión de etiqueta del SDK web](web-sdk-tag-extension.md): Una instalación nueva del SDK web que usa la extensión de etiqueta del SDK web. Es similar al método de biblioteca JavaScript del SDK web (esta página), excepto que la implementación se administra mediante etiquetas en la recopilación de datos de Adobe Experience Platform. Requiere el grupo de campos Adobe Analytics ExperienceEvent, que incluye variables típicas de Analytics que se deben incluir en el esquema XDM.
* [Extensión de Analytics a la extensión de SDK web](analytics-extension-to-web-sdk.md): adopte un enfoque suave y metódico para pasar de la extensión de etiquetas de Adobe Analytics a la extensión de etiquetas de SDK web. Este método suprime la necesidad de utilizar XDM hasta que su organización esté lista para utilizar los servicios de Adobe Experience Platform, como Customer Journey Analytics. Utilice el objeto `data` en lugar del objeto `xdm` para enviar datos al Adobe.
* [AppMeasurement a la biblioteca JavaScript del SDK web](appmeasurement-to-web-sdk.md): Un enfoque sencillo y metódico para migrar al SDK web, excepto que no utiliza etiquetas. En su lugar, puede quitar manualmente la biblioteca de recopilación de datos de Adobe Analytics (`AppMeasurement.js`) y reemplazarla por la biblioteca de JavaScript del SDK web (`alloy.js`).

## Ventajas y desventajas de esta ruta de implementación

El uso de la biblioteca JavaScript del SDK web para enviar datos a Adobe Analytics tiene ventajas y desventajas. Valore cuidadosamente cada opción para decidir qué enfoque es el mejor para su organización.

| Ventajas | Desventajas |
| --- | --- |
| <ul><li>**Enfoque directo**: Esta ruta de implementación es más sencilla que los enfoques que mueven las implementaciones de Adobe Analytics existentes. Si no tiene una implementación de Adobe Analytics actual de la que preocuparse, rellene los campos XDM aplicables del SDK web.</li><li>**Esquema predefinido**: Si su organización no necesita su propio esquema, puede usar simplemente el esquema orientado a Adobe Analytics. Este concepto se aplica incluso cuando se mueve hacia Customer Journey Analytics; el concepto de props y eVars no se aplica a Customer Journey Analytics, pero puede seguir utilizando props y eVars como dimensiones personalizadas simples.</li></ul> | <ul><li>**Los cambios de implementación requieren la intervención del desarrollador**: Si desea realizar cambios en la implementación del SDK web, debe trabajar con el equipo de desarrollo para editar el código del sitio. El método que usa la [extensión de etiqueta del SDK web](web-sdk-tag-extension.md) evita esta desventaja.</li><li>**Bloqueado en mediante un esquema específico**: cuando su organización se traslade a Customer Journey Analytics, debe elegir continuar usando el esquema de Adobe Analytics o migrar al esquema de su propia organización (que sería un conjunto de datos independiente). Si su organización desea evitar el esquema de Adobe Analytics y la migración a un conjunto de datos independiente al pasar a Customer Journey Analytics, Adobe recomienda uno de los dos métodos siguientes:</li><ul><li>Utilice el objeto `data`: El objeto `data` le permite enviar datos a Adobe Analytics sin ajustarse a un esquema XDM. Una vez creado el esquema de su organización, puede utilizar la asignación de secuencia de datos para asignar `data` campos de objeto a XDM. Tanto la extensión [Analytics a la extensión del SDK web](analytics-extension-to-web-sdk.md) como el [AppMeasurement a la biblioteca JavaScript del SDK web](appmeasurement-to-web-sdk.md) utilizan este objeto `data`.</li><li>Omitir Adobe Analytics por completo: si va a implementar el SDK web, puede enviar esos datos a un conjunto de datos en Adobe Experience Platform para su uso en Customer Journey Analytics. Puede utilizar cualquier esquema que desee; Adobe Analytics no participa en absoluto en este flujo de trabajo y, por lo tanto, no requiere el grupo de campos Adobe Analytics ExperienceEvent. Este método incurre en la menor cantidad de deuda técnica, pero también deja a Adobe Analytics fuera del panorama por completo.</li></ul></ul> |

>[!IMPORTANT]
>
>Este método de implementación requiere que utilice un esquema configurado para Adobe Analytics. Si su organización planea utilizar su propio esquema con Customer Journey Analytics en el futuro, el uso del esquema de Adobe Analytics puede crear confusión para los administradores de datos o los arquitectos. Existen varias opciones para mitigar este obstáculo:
>
>* Puede utilizar el esquema de Adobe Analytics en CJA. Tenga en cuenta que CJA no tiene un concepto de props o eVars; se tratan como cualquier otro campo de esquema. Tenga en cuenta también que el uso del esquema de Adobe Analytics en CJA puede dificultar el uso de otros servicios de plataforma, como Adobe Journey Optimizer o Real-time Customer Data Platform.
>* Puede utilizar el objeto de datos, de forma similar a un flujo de trabajo de migración. Tenga en cuenta que el uso del objeto de datos requiere que asigne cada campo de objeto de datos a un campo de esquema XDM.
>* Puede omitir la implementación de Adobe Analytics por completo y enviar datos a Adobe Experience Platform con su propio esquema. Este enfoque es ideal a largo plazo y permite a su organización empezar a utilizar Customer Journey Analytics.

## Pasos necesarios para implementar la biblioteca JavaScript del SDK web

Una información general de alto nivel de las tareas de implementación:

![Cómo implementar Adobe Analytics mediante el flujo de trabajo del SDK web, tal como se describe en esta sección.](../../assets/websdk-annotated.png)

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
<td><b>Configurar esquemas</b>. Para estandarizar la recopilación de datos para su uso en todas las aplicaciones que aprovechan Adobe Experience Platform, Adobe ha creado el estándar abierto y documentado públicamente, Experience Data Model (XDM).</td>
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
<td><b>Configurar el SDK web</b>. Asegúrese de que la biblioteca que instaló en el paso 4 esté configurada correctamente con el ID de secuencia de datos (anteriormente conocido como id. de configuración de Edge (<code>datastreamId</code>)), id. de organización (<code>orgId</code>) y otras opciones disponibles. Asegúrese de que la asignación de variables sea correcta. </td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/web-sdk/commands/configure/overview.html">Configurar el SDK web</a><br/><a href="../xdm-var-mapping.md">Asignación de variables de objetos XDM</a></td>
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

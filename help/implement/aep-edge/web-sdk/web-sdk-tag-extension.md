---
title: Envío de datos a Adobe Analytics mediante la extensión de etiqueta del SDK web
description: Comience con una implementación limpia de la recopilación de datos de Adobe Experience Platform para enviar datos a Adobe Analytics mediante XDM y el grupo de campos Adobe Analytics ExperienceEvent.
hide: true
hidefromtoc: true
source-git-commit: d6c16d8841110e3382248f4c9ce3c2f2e32fe454
workflow-type: tm+mt
source-wordcount: '1040'
ht-degree: 17%

---

# Envío de datos a Adobe Analytics mediante la extensión de etiqueta del SDK web

Esta ruta de implementación implica una nueva instalación del SDK web mediante etiquetas en la recopilación de datos de Adobe Experience Platform. Otras rutas de implementación se tratan en páginas independientes:

* [Biblioteca JavaScript del SDK web](web-sdk-javascript-library.md): una instalación nueva del SDK web mediante la biblioteca JavaScript del SDK web (`alloy.js`). Es similar al método de extensión de etiquetas SDK web (esta página), excepto que la implementación la administra usted mismo en lugar de utilizar la interfaz de usuario de etiquetas. Requiere el grupo de campos Adobe Analytics ExperienceEvent, que incluye variables típicas de Analytics que se deben incluir en el esquema XDM.
* [Extensión de Analytics a SDK web](analytics-extension-to-web-sdk.md): Adopte un enfoque suave y metódico para pasar de la extensión de etiquetas de Adobe Analytics a la extensión de etiquetas del SDK web. Este método suprime la necesidad de utilizar XDM hasta que su organización esté lista para utilizar los servicios de Adobe Experience Platform, como Customer Journey Analytics. Utilice el `data` en lugar del objeto `xdm` objeto para enviar datos al Adobe.
* [AppMeasurement a la biblioteca JavaScript del SDK web](appmeasurement-to-web-sdk.md): un enfoque suave y metódico para migrar al SDK web, excepto que no utiliza etiquetas. En su lugar, elimine manualmente la biblioteca de recopilación de datos de Adobe Analytics (`AppMeasurement.js`) y reemplácelo por la biblioteca JavaScript del SDK web (`alloy.js`).

## Ventajas y desventajas de esta ruta de implementación

El uso de la extensión del SDK web para enviar datos a Adobe Analytics tiene ventajas y desventajas. Valore cuidadosamente cada opción para decidir qué enfoque es el mejor para su organización.

| Ventajas | Desventajas |
| --- | --- |
| <ul><li>**El enfoque más directo**: Esta ruta de implementación es la más sencilla y, por lo general, la recomendada para las nuevas implementaciones de SDK web. Si no tiene una implementación de Adobe Analytics actual de la que preocuparse, rellene los campos XDM aplicables del SDK web.</li><li>**Esquema predefinido**: Si su organización no necesita su propio esquema, simplemente puede utilizar el esquema orientado a Adobe Analytics. Este concepto se aplica incluso cuando se mueve hacia Customer Journey Analytics; el concepto de props y eVars no se aplica a Customer Journey Analytics, pero puede seguir utilizando props y eVars como dimensiones personalizadas simples.</li><li>**Administración de etiquetas sin intervención del desarrollador**: Las etiquetas permiten administrar la implementación sin solicitar a los desarrolladores que realicen cambios en el código de la implementación. Los desarrolladores instalan el script del cargador de etiquetas y usted tiene control total sobre cómo se recopilan los datos.</li></ul> | <ul><li>**Bloqueado en mediante un esquema específico**: Cuando su organización se traslada a Customer Journey Analytics, debe elegir continuar utilizando el esquema de Adobe Analytics o migrar al esquema de su propia organización (que sería un conjunto de datos independiente). Si su organización desea evitar el esquema de Adobe Analytics y la migración a un conjunto de datos independiente al pasar a Customer Journey Analytics, Adobe recomienda uno de los dos métodos siguientes:<ul><li>Utilice el `data` objeto: El `data` permite enviar datos a Adobe Analytics sin ajustarse a un esquema XDM. Una vez creado el esquema de su organización, puede utilizar la asignación de flujos de datos para asignar `data` campos de objeto a XDM. Tanto la [Extensión de Analytics a SDK web](analytics-extension-to-web-sdk.md) y [AppMeasurement a la biblioteca JavaScript del SDK web](appmeasurement-to-web-sdk.md) use esto `data` objeto.</li><li>Omitir Adobe Analytics por completo: si va a implementar el SDK web, puede enviar esos datos a un conjunto de datos en Adobe Experience Platform para su uso en Customer Journey Analytics. Puede utilizar cualquier esquema que desee; Adobe Analytics no participa en absoluto en este flujo de trabajo y, por lo tanto, no requiere el grupo de campos Adobe Analytics ExperienceEvent. Este método incurre en la menor cantidad de deuda técnica, pero también deja a Adobe Analytics fuera del panorama por completo.</li></ul></ul> |

>[!CAUTION]
>
>Este método de implementación requiere que utilice un esquema configurado para Adobe Analytics. Si su organización planea utilizar su propio esquema con Customer Journey Analytics en el futuro, el uso del esquema de Adobe Analytics puede crear confusión para los administradores de datos o los arquitectos. Existen varias opciones para mitigar este obstáculo:
>
>* Puede utilizar el esquema de Adobe Analytics en CJA. Tenga en cuenta que CJA no tiene un concepto de props o eVars; se tratan como cualquier otro campo de esquema. Tenga en cuenta también que el uso del esquema de Adobe Analytics en CJA puede dificultar el uso de otros servicios de plataforma, como Adobe Journey Optimizer o Real-time Customer Data Platform.
>* Puede utilizar el objeto de datos, de forma similar a un flujo de trabajo de migración. Tenga en cuenta que el uso del objeto de datos requiere que asigne cada campo de objeto de datos a un campo de esquema XDM.
>* Puede omitir la implementación de Adobe Analytics por completo y enviar datos a Adobe Experience Platform con su propio esquema. Este enfoque es ideal a largo plazo y permite a su organización empezar a utilizar Customer Journey Analytics.

## Pasos necesarios para implementar la extensión de etiqueta del SDK web

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

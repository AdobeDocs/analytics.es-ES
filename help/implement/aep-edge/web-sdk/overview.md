---
title: Implementar Adobe Analytics mediante el SDK web de Adobe Experience Platform
description: Utilice la extensión del SDK web en la recopilación de datos de Adobe Experience Platform para enviar datos a Adobe Analytics.
source-git-commit: e6b40881a543b43c03b612c7e7b0d9bd09f44c0d
workflow-type: tm+mt
source-wordcount: '782'
ht-degree: 23%

---

# Implementar Adobe Analytics mediante el SDK web de Adobe Experience Platform

Puede utilizar el [SDK web de Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/sdk/overview.html) para enviar datos a Adobe Analytics. Este método de implementación funciona traduciendo el [Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=es) a un formato utilizado por Analytics.

Puede enviar datos a Experience Edge directamente mediante el SDK web o a través de la extensión del SDK web en Etiquetas.

## SDK web

Una visión general de alto nivel de las tareas de implementación:

![Implementar Adobe Analytics mediante el flujo de trabajo del SDK web](../../assets/websdk-annotated.png)

|<div style="width:20px"></div>| Tarea | Más información | |-| —|—| | 1 | Asegúrese de que **definición de un grupo de informes**. | [Administrador del grupo de informes](../../../admin/admin/c-manage-report-suites/report-suites-admin.md) | | 2 | **Configuración de esquemas y conjuntos de datos**. Para estandarizar la recopilación de datos para su uso en todas las aplicaciones que aprovechan Adobe Experience Platform, Adobe ha creado el estándar abierto y documentado públicamente, Experience Data Model (XDM). | [Información general sobre la interfaz de usuario de Esquemas](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=es) y [Información general sobre la interfaz de usuario de conjuntos de datos](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=es) | | 3 | **Creación de una capa de datos** para administrar el seguimiento de los datos del sitio web. | [Creación de una capa de datos](../../prepare/data-layer.md) | | 4 | **Instale la versión independiente precompilada**. Puede hacer referencia a la biblioteca (`alloy.js`) en la CDN directamente en su página o descargue y aloje en su propia infraestructura. Alternativamente, puede utilizar el paquete NPM. | [Instalación de la versión independiente precompilada](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=en#option-2%3A-installing-the-prebuilt-standalone-version) y [Uso del paquete NPM](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=en#option-3%3A-using-the-npm-package)| | 5 | **Configurar un conjunto de datos**. Un conjunto de datos representa la configuración del lado del servidor al implementar el SDK web de Adobe Experience Platform. | [Configurar un conjunto de datos](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en) | | 6 | **Añadir un servicio de Adobe Analytics** al conjunto de datos. Ese servicio controla si los datos se envían a Adobe Analytics y cómo se hacen. | [Añadir el servicio Adobe Analytics a un conjunto de datos](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en#analytics) | | 7 | **Configuración del SDK web**. Asegúrese de que la biblioteca instalada en el paso 4 esté correctamente configurada con el ID del conjunto de datos (anteriormente conocido como id de configuración perimetral (`edgeConfigId`)), id de organización (`orgId`) y otras opciones disponibles. | [Configuración del SDK web](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=es) | | 8 | **Ejecutar, comandos** y/o **seguimiento de eventos**. Una vez implementado el código base en la página web, puede empezar a ejecutar comandos y rastrear eventos con el SDK. | [Ejecutar, comandos](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/executing-commands.html?lang=en) y [Seguimiento de eventos](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=en) | | 9 | **Ampliación y validación de la implementación** antes de llevarlo a producción. | |



## Extensión de SDK web

Una visión general de alto nivel de las tareas de implementación:

![Implementar Adobe Analytics mediante el flujo de trabajo de extensión de SDK web](../../assets/websdk-extension-annotated.png)

|<div style="width:20px"></div> | Tarea | Más información | |-| —|—| | 1 | Asegúrese de que **definición de un grupo de informes**. | [Administrador del grupo de informes](../../../admin/admin/c-manage-report-suites/report-suites-admin.md) | | 2 | **Configuración de esquemas y conjuntos de datos**. Para estandarizar la recopilación de datos para su uso en todas las aplicaciones que aprovechan Adobe Experience Platform, Adobe ha creado el estándar abierto y documentado públicamente, Experience Data Model (XDM). | [Información general sobre la interfaz de usuario de Esquemas](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=es) y [Información general sobre la interfaz de usuario de conjuntos de datos](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=es) | | 3 | **Creación de una capa de datos** para administrar el seguimiento de los datos del sitio web. | [Creación de una capa de datos](../../prepare/data-layer.md) | | 4 | **Configurar un conjunto de datos**. Un conjunto de datos representa la configuración del lado del servidor al implementar el SDK web de Adobe Experience Platform. | [Configurar un conjunto de datos](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en) | | 5 | **Añadir un servicio de Adobe Analytics** al conjunto de datos. Ese servicio controla si los datos se envían a Adobe Analytics y cómo se hacen. | [Añadir el servicio Adobe Analytics a un conjunto de datos](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en#analytics) | | 6 | **Crear una propiedad de etiqueta**. Las propiedades son contenedores generales que se utilizan para hacer referencia a los datos de administración de etiquetas.| [Creación o configuración de una propiedad de etiqueta para la web](https://experienceleague.adobe.com/docs/experience-platform/tags/admin/companies-and-properties.html?lang=en#for-web) | | 7 | **Instalación y configuración de la extensión del SDK web** en la propiedad tag . Configure la extensión del SDK web para enviar datos al conjunto de datos configurado en el paso 4. | [Descripción general de la extensión del SDK web de Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/sdk/overview.html?lang=en) | | 8 | **Iterar, validar y publicar** a producción. Agregue la propiedad tag al sitio web. A continuación, utilice elementos de datos, reglas, etc. para personalizar la implementación. | [Información general sobre la publicación](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=es) |



## Recursos adicionales

Las etiquetas se pueden personalizar en gran medida. Obtenga más información sobre cómo aprovechar al máximo Adobe Analytics mediante la inclusión de los datos adecuados en la implementación.

- [Documentación de etiquetas](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=es#): Descubra cómo funciona la interfaz y qué extensiones están disponibles.

- [Documentación del SDK web de Adobe Experience Platform](https://experienceleague.adobe.com/docs/web-sdk.html?lang=es)

---
title: Implementar Adobe Analytics mediante el SDK móvil de Adobe Experience Platform
description: Utilice la extensión del SDK móvil en la recopilación de datos de Adobe Experience Platform para enviar datos a Adobe Analytics.
source-git-commit: 5adc3fe1eab0a358573ebdc12e51c6753e85b14c
workflow-type: tm+mt
source-wordcount: '579'
ht-degree: 20%

---

# Implementar Adobe Analytics mediante el SDK móvil de Adobe Experience Platform

El SDK móvil de Adobe Experience Platform ayuda a impulsar las soluciones y los servicios Experience Cloud de los Adobes en sus aplicaciones móviles. Está disponible para Android™, iOS y varios marcos de desarrollo entre plataformas. La configuración se administra mediante la recopilación de datos de Adobe Experience Platform.
>[!IMPORTANT]
>
>También hay una extensión de Adobe Analytics disponible en la recopilación de datos de Adobe Experience Platform. Si instala esta extensión, no aprovecha XDM ni la red perimetral.

## SDK de Adobe Experience Platform

Una visión general de alto nivel de las tareas de implementación:

![Adobe Analytics mediante el flujo de trabajo de extensión de Analytics](../../assets/mobilesdk-annotated.png)

| | Tarea | Más información | |-| —|—| | 1 | Asegúrese de que **definición de un grupo de informes**. | [Administrador del grupo de informes](../../../admin/admin/c-manage-report-suites/report-suites-admin.md) | | 2 | **Configuración de esquemas y conjuntos de datos**. Para estandarizar la recopilación de datos para su uso en todas las aplicaciones que aprovechan Adobe Experience Platform, Adobe ha creado el estándar abierto y documentado públicamente, Experience Data Model (XDM). | [Configuración de esquemas y conjuntos de datos](https://developer.adobe.com/client-sdks/documentation/getting-started/set-up-schemas-and-datasets/) | | 3 | **Configurar un conjunto de datos**. Un conjunto de datos representa la configuración del lado del servidor al implementar el SDK web de Adobe Experience Platform. | [Configurar un conjunto de datos](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en) | | 4 | **Añadir un servicio de Adobe Analytics** al conjunto de datos. Ese servicio controla si los datos se envían a Adobe Analytics y cómo se hacen. | [Añadir el servicio Adobe Analytics a un conjunto de datos](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en#analytics) | | 5 | **Crear una propiedad móvil**. Una propiedad es un contenedor que se rellena con extensiones, reglas, elementos de datos y bibliotecas. | [Configuración de una propiedad móvil](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/) | | 6 | **Instalación de la extensión Adobe Experience Platform Edge Network** en la propiedad mobile tag y configure el conjunto de datos en la extensión . | [Adobe Experience Platform Edge Network](https://developer.adobe.com/client-sdks/documentation/edge-network/) | | 7 | **Uso del código en la aplicación** para registrar las extensiones necesarias y cargar la configuración de la etiqueta. | [Configuración](https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#set-up-the-configuration) | | 8 | **Implementación y funcionalidad de prueba** mediante la combinación de elementos de datos de la etiqueta, reglas, extensiones adicionales y llamadas de API de SDK en la aplicación. Inspect, valide y depure la recopilación de datos y experiencias para su aplicación móvil. | [Uso de la aplicación de ejemplo](https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#use-the-sample-application) | | 9 | **Ampliar y validar la implementación de la aplicación móvil** antes de llevarlo a producción. | |


## Extensión de Adobe Analytics.

Una visión general de alto nivel de las tareas de implementación:

![Adobe Analytics mediante el flujo de trabajo de extensión de Analytics](../../assets/mobilesdk-analytics-annotated.png)

| | Tarea | Más información | |-| —|—| | 1 | Asegúrese de que **definición de un grupo de informes**. | [Administrador del grupo de informes](../../../admin/admin/c-manage-report-suites/report-suites-admin.md) | | 2 | **Crear una propiedad móvil**. Una propiedad es un contenedor que se rellena con extensiones, reglas, elementos de datos y bibliotecas. | [Configuración de una propiedad móvil](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/) | | 3 | **Instalación de la extensión de Adobe Analytics** en la propiedad mobile tag y configure la extensión para que apunte al grupo de informes. | [Extensión de Adobe Analytics para la propiedad móvil](https://developer.adobe.com/client-sdks/documentation/adobe-analytics/) | | 4 | **Uso del código en la aplicación** para registrar las extensiones necesarias y cargar la configuración de la etiqueta. | [Configuración](https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#set-up-the-configuration) | | 5 | **Implementación y funcionalidad de prueba** mediante la combinación de elementos de datos de la etiqueta, reglas, extensiones adicionales y llamadas de API de SDK en la aplicación. Inspect, valide y depure la recopilación de datos y experiencias para su aplicación móvil. | [Uso de la aplicación de ejemplo](https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#use-the-sample-application) | | 6 | **Ampliar y validar la implementación de la aplicación móvil** antes de llevarlo a producción. | |

## Recursos adicionales

- [Documentación de etiquetas](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=es#)

- [Documentación de Mobile SDK](https://developer.adobe.com/client-sdks/documentation/)




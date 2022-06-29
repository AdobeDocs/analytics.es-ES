---
title: Implementar Adobe Analytics mediante el SDK móvil de Adobe Experience Platform
description: Utilice la extensión del SDK móvil en la recopilación de datos de Adobe Experience Platform para enviar datos a Adobe Analytics.
exl-id: 516e9a1e-caa7-4f8a-ab8c-6404e9242ccb
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 89%

---

# Implementar Adobe Analytics mediante el SDK móvil de Adobe Experience Platform

El SDK móvil de Adobe Experience Platform ayuda a impulsar las soluciones y los servicios Experience Cloud de los Adobes en sus aplicaciones móviles. Está disponible para Android, iOS y varios marcos de desarrollo entre plataformas. La configuración se gestiona mediante la recopilación de datos de Adobe Experience Platform.

Para enviar datos a Adobe Experience Edge mediante el SDK para móviles:

1. Inicie sesión en [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection).
2. Seleccione la propiedad que desee en la lista o [configure una propiedad móvil](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property).
3. Vaya a la pestaña Extensiones e instale la extensión [Identidad para la red perimetral](https://aep-sdks.gitbook.io/docs/foundation-extensions/identity-for-edge-network).
4. Instale [Adobe Experience Platform Edge Network](https://aep-sdks.gitbook.io/docs/foundation-extensions/experience-platform-extension).
5. [Configure una secuencia de datos](https://aep-sdks.gitbook.io/docs/getting-started/configure-datastreams) y agregue Adobe Analytics como servicio que señala al grupo de informes deseado.
6. [Instale el SDK](https://aep-sdks.gitbook.io/docs/getting-started/get-the-sdk) en su aplicación móvil.

>[!IMPORTANT]
>
>También hay una extensión de Adobe Analytics disponible en la recopilación de datos de Adobe Experience Platform. Si instala esta extensión, no aprovecha XDM ni la red perimetral.

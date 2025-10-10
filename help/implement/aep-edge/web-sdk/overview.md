---
title: Implementar Adobe Analytics mediante el SDK web de Adobe Experience Platform
description: Utilice Web SDK para enviar datos a Adobe Analytics.
exl-id: 97f8d650-247f-4386-b4d2-699f3dab0467
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: d6c16d8841110e3382248f4c9ce3c2f2e32fe454
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 40%

---

# Implementar Adobe Analytics mediante el SDK web de Adobe Experience Platform

Puede utilizar el [SDK web de Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/web-sdk/home.html?lang=es) para enviar datos a Adobe Analytics. Existen dos métodos principales para implementar Web SDK y cada método tiene dos tipos de implementación:

| | **Migrar desde AppMeasurement** | **Implementación limpia de Web SDK** |
| --- | --- | --- |
| **Usar etiquetas** | [Migrar de la extensión de Analytics a la extensión de Web SDK](analytics-extension-to-web-sdk.md) | [Enviar datos a Adobe Analytics mediante la extensión Web SDK](web-sdk-tag-extension.md) |
| **Usar JavaScript** | [Migrar de AppMeasurement a la biblioteca JavaScript de Web SDK](appmeasurement-to-web-sdk.md) | [Enviar datos a Adobe Analytics mediante la biblioteca JavaScript de Web SDK](web-sdk-javascript-library.md) |

Si su organización requiere una nueva implementación de Web SDK y planea utilizar Customer Journey Analytics en el futuro, Adobe recomienda una implementación de Web SDK limpia utilizando su propio esquema. Consulte [Ingesta de datos mediante Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk) en la guía del usuario de Customer Journey Analytics.

## Recursos adicionales

Las etiquetas se pueden personalizar en gran medida. Obtenga más información sobre cómo aprovechar al máximo Adobe Analytics mediante la inclusión de los datos adecuados en la implementación.

- [Documentación de etiquetas](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=es#): descubra cómo funciona la interfaz y qué extensiones están disponibles.

- [Documentación del SDK web de Adobe Experience Platform](https://experienceleague.adobe.com/docs/web-sdk.html?lang=es)

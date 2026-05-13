---
title: Implementar Adobe Analytics mediante el SDK web de Adobe Experience Platform
description: Utilice Web SDK para enviar datos a Adobe Analytics.
exl-id: 97f8d650-247f-4386-b4d2-699f3dab0467
feature: Implementation Basics
role: Admin, Developer, Leader
TQID: https://experienceleague.adobe.com/4pS-q3F3W7D1ojdMkCzgUyZkO3LDt1DpFfxqcTtZXLQ
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: f8a45b24-4be7-4f1b-909b-60d06b483a20id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 242
ht-degree: 42%

---

# Implementar Adobe Analytics mediante el SDK web de Adobe Experience Platform

Puede utilizar el [SDK web de Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/web-sdk/home.html) para enviar datos a Adobe Analytics. Existen dos métodos principales para implementar Web SDK y cada método tiene dos tipos de implementación:

| | **Migrar desde AppMeasurement** | **Implementación limpia de Web SDK** |
| --- | --- | --- |
| **Usar etiquetas** | [Migrar de la extensión de Analytics a la extensión de Web SDK](analytics-extension-to-web-sdk.md) | [Enviar datos a Adobe Analytics mediante la extensión Web SDK](web-sdk-tag-extension.md) |
| **Usar JavaScript** | [Migrar de AppMeasurement a la biblioteca JavaScript de Web SDK](appmeasurement-to-web-sdk.md) | [Enviar datos a Adobe Analytics mediante la biblioteca JavaScript de Web SDK](web-sdk-javascript-library.md) |

Si su organización requiere una nueva implementación de Web SDK y planea utilizar Customer Journey Analytics en el futuro, Adobe recomienda una implementación de Web SDK limpia utilizando su propio esquema. Consulte [Ingesta de datos mediante Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk) en la guía del usuario de Customer Journey Analytics.

## Recursos adicionales

Las etiquetas se pueden personalizar en gran medida. Obtenga más información sobre cómo aprovechar al máximo Adobe Analytics mediante la inclusión de los datos adecuados en la implementación.

- [Documentación de etiquetas](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=es#): descubra cómo funciona la interfaz y qué extensiones están disponibles.

- [Documentación de Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/web-sdk.html?lang=es)

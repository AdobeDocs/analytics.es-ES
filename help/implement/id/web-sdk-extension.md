---
title: Identificación de visitantes con la extensión de etiquetas Web SDK
description: Identifique correctamente a los visitantes al implementar la extensión de etiquetas Web SDK.
exl-id: 65de7fc3-a344-4f04-b523-1f5edf681d2f
TQID: https://experienceleague.adobe.com/W42VkHT5yCW0yO-FbiAFHHKM8dF5NgCveZYGFOs7sYk
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 192
ht-degree: 0%

---

# Identificación de visitantes con la extensión de etiquetas Web SDK

La extensión de etiquetas Web SDK de la recopilación de datos de Adobe Experience Platform permite a las organizaciones implementar Web SDK mediante una interfaz de administración de etiquetas. Los escenarios avanzados, como el uso compartido de ID entre dominios y la migración de perfiles de visitantes, se configuran fácilmente mediante reglas y acciones de extensión. El uso de Web SDK afianza la implementación y permite una actualización perfecta a Customer Journey Analytics.

Los datos de identidad se pueden ampliar para admitir ID personalizados y varias áreas de nombres con `identityMap` de XDM. Adobe recomienda usar el servicio de Adobe Experience Cloud ID como identificador principal para Analytics mediante otras opciones de administración de identidades en escenarios avanzados.

Dado que el servicio de ID de visitante se copia de forma nativa en la extensión de etiqueta, solo requiere que establezca **[!UICONTROL Dominio de Edge]** en el valor deseado. Si este campo está configurado correctamente, la identificación del visitante funciona sin ninguna configuración adicional.

>[!NOTE]
>
>No incluya la extensión de etiqueta del servicio de ID de visitante si utiliza la extensión de etiqueta de Web SDK. La extensión de etiqueta del servicio de ID de visitante solo es necesaria si usa la [extensión de Adobe Analytics](analytics-extension.md).

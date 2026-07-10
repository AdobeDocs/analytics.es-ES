---
title: Identificación de visitantes con la extensión de etiquetas Web SDK
description: Identifique correctamente a los visitantes al implementar la extensión de etiquetas Web SDK.
exl-id: 65de7fc3-a344-4f04-b523-1f5edf681d2f
TQID: 'https://experienceleague.adobe.com/4PVDioBDa-1VXg9Fpy0wA8-RZZYSXzVijj-b2kdEALQ'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
subfeature_v2:
  - id: b3e5f43e-2e2f-43c0-810a-044a5f91e31a
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: a947d2d7f45d4155a61cbfe0f8110851cca32e60
workflow-type: tm+mt
source-wordcount: 197
ht-degree: 0%

---

# Identificación de visitantes con la extensión de etiquetas Web SDK

La extensión de etiquetas Web SDK de la recopilación de datos de Adobe Experience Platform permite a las organizaciones implementar Web SDK mediante una interfaz de administración de etiquetas. Los escenarios avanzados, como el uso compartido de ID entre dominios y la migración de perfiles de visitantes, se configuran fácilmente mediante reglas y acciones de extensión. El uso de Web SDK afianza la implementación y permite una actualización perfecta a Customer Journey Analytics.

Los datos de identidad se pueden ampliar para admitir ID personalizados y varias áreas de nombres con [`identityMap`](https://experienceleague.adobe.com/en/docs/experience-platform/collection/identity/identity-map) de XDM. Adobe recomienda usar ECID como identificador principal para Analytics mediante otras opciones de administración de identidades en escenarios avanzados.

Dado que el servicio de ID de visitante se copia de forma nativa en la extensión de etiqueta, solo requiere que establezca **[!UICONTROL Dominio de Edge]** en el valor deseado. Si este campo está configurado correctamente, la identificación del visitante funciona sin ninguna configuración adicional.

>[!NOTE]
>
>No incluya la extensión de etiqueta del servicio de ID de visitante si utiliza la extensión de etiqueta de Web SDK. La extensión de etiqueta del servicio de ID de visitante solo es necesaria si usa la [extensión de Adobe Analytics](analytics-extension.md).

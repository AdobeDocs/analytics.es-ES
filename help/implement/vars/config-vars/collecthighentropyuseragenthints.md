---
title: collectHighEntropyUserAgentHints
description: Utilice la variable collectHighEntropyUserAgentHints para determinar si Adobe solicitará sugerencias de alta entropía a los exploradores Chromium (por ejemplo, Google Chrome y Microsoft Edge).
exl-id: 97cfa0f9-b35d-4c73-822f-adf30d0b7efc
feature: Appmeasurement Implementation
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/SfKPGVjuEsMzJUVJYSEh9M8eawg0RqLNceSlqrTu3Ps'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 240
ht-degree: 100%

---

# collectHighEntropyUserAgentHints

Adobe Analytics utiliza sugerencias de cliente de alta entropía para mejorar la identificación de dispositivos y exploradores. Esta opción está disponible a partir de la versión 2.23.0 de AppMeasurement.js. Obtenga más información acerca de las sugerencias del cliente en [esta descripción general y preguntas frecuentes](/help/technotes/client-hints.md), así como en el [Blog de Google](https://web.dev/user-agent-client-hints/).

## Recopilación de sugerencias de alta entropía mediante el SDK web

Las sugerencias de cliente de alta entropía forman parte de las categorías de contexto del SDK web. Consulte [Configuración del SDK web de Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=es) para obtener más información.

## Recopilación de sugerencias de alta entropía con la extensión de Adobe Analytics

**[!UICONTROL Recopilar sugerencias de usuario-agente de alta entropía]** es una casilla de verificación en el acordeón General al configurar la extensión de Adobe Analytics.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/#/@adobepm/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la [!UICONTROL propiedad de etiquetas] deseada.
1. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en [!UICONTROL Configurar] en Adobe Analytics.
1. Expanda el acordeón [!UICONTROL General], que revela la casilla de verificación [!UICONTROL Recopilar sugerencias de agente de usuario de alta entropía]. De forma predeterminada, está desactivada.

## collectHighEntropyUserAgentHints en AppMeasurement

La variable `s.collectHighEntropyUserAgentHints` determina si AppMeasurement solicita sugerencias de alta entropía a los exploradores Chromium (por ejemplo, Google Chrome y Microsoft Edge). Adobe Analytics utiliza estas sugerencias para mejorar la identificación de dispositivos y exploradores.

Si se establece en `true`, se solicitarán al explorador todas las sugerencias de alta entropía.

```js
s.collectHighEntropyUserAgentHints = true;
```

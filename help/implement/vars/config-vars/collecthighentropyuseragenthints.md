---
title: collectHighEntropyUserAgentHints
description: Utilice la variable collectHighEntropyUserAgentHints para determinar si Adobe solicitará sugerencias de alta entropía a los exploradores Chromium (por ejemplo, Google Chrome y Microsoft Edge).
exl-id: 97cfa0f9-b35d-4c73-822f-adf30d0b7efc
feature: Appmeasurement Implementation
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '215'
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

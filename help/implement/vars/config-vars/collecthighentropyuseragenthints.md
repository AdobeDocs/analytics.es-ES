---
title: collectHighEntropyUserAgentHints
description: Utilice la variable collectHighEntropyUserAgentHints para determinar si el Adobe solicitará sugerencias de alta entropía a los navegadores Chromium (por ejemplo, Google Chrome y Microsoft Edge).
source-git-commit: 0a23ad56a661a420dd44e2875c22927f9734dedf
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 3%

---


# collectHighEntropyUserAgentHints

Adobe Analytics utiliza sugerencias de cliente de alta entropía para mejorar la identificación de dispositivos y exploradores. Obtenga más información sobre las sugerencias del cliente en [esta descripción general y preguntas frecuentes](/help/technotes/client-hints.md) así como [Blog de Google](https://web.dev/user-agent-client-hints/).

## Recopilación de sugerencias de alta entropía mediante el SDK web

Las sugerencias de cliente de alta entropía forman parte de las categorías de contexto del SDK web. Consulte [Configuración del SDK web de Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=en) para obtener más información.

## Recopilar sugerencias de alta entropía con la extensión de Adobe Analytics

**[!UICONTROL Recopilar sugerencias de usuario-agente de alta entropía]** es una casilla de verificación en el acordeón General al configurar la extensión de Adobe Analytics.

1. Iniciar sesión en [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/#/@adobepm/data-collection) uso de sus credenciales de Adobe ID.

1. Haga clic en el [!UICONTROL tag, propiedad].

1. Vaya a la [!UICONTROL Extensiones] a continuación, haga clic en [!UICONTROL Configurar] en Adobe Analytics.

1. Expanda el [!UICONTROL General] el acordeón, que revela la variable [!UICONTROL Recopilar sugerencias de usuario-agente de alta entropía] en el Navegador. De forma predeterminada, está desactivada.

## collectHighEntropyUserAgentHints en AppMeasurement

La variable `s.collectHighEntropyUserAgentHints` determina si AppMeasurement solicita sugerencias de alta entropía a los exploradores Chromium (por ejemplo, Google Chrome y Microsoft Edge). Adobe Analytics utiliza estas sugerencias para mejorar la identificación de dispositivos y exploradores.

Si se establece en TRUE , todas las sugerencias de entropía alta se solicitarán al explorador.

`s.collectHighEntropyUserAgentHints = TRUE`

`s.collectHighEntropyUserAgentHints = FALSE`
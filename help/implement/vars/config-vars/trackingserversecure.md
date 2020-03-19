---
title: trackingServerSecure
description: Determinar la ubicación en la que se envían las solicitudes de imagen en páginas HTTPS.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# trackingServerSecure

Adobe recopila datos en el sitio mediante la recepción de una solicitud de imagen generada por el visitante. La `trackingServerSecure` variable determina la ubicación en la que se envía una solicitud de imagen a través de HTTPS. También determina la ubicación en la que se almacenan las cookies de los visitantes. Si esta variable no se define correctamente, la implementación puede experimentar una pérdida de datos.

> [!IMPORTANT] Si se cambia este valor, AppMeasurement buscará cookies en una ubicación diferente. El recuento de visitantes únicos puede aumentar temporalmente en los informes a medida que las cookies de los visitantes se establecen en la nueva ubicación.

## Servidor de seguimiento SSL en Adobe Experience Platform Launch

[!UICONTROL SSL Tracking Server] es un campo bajo el [!UICONTROL General] acordeón al configurar la extensión de Adobe Analytics.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Haga clic en la propiedad que desee.
3. Vaya a la [!UICONTROL Extensions] ficha y, a continuación, haga clic en el [!UICONTROL Configure] botón situado debajo de Adobe Analytics.
4. Expanda el [!UICONTROL General] acordeón, que muestra el [!UICONTROL SSL Tracking Server] campo.

Si este campo se deja en blanco, el valor predeterminado es el valor en la [`trackingServer`](trackingserver.md) variable.

## s.trackingServerSecure en AppMeasurement e inicie el editor de código personalizado

La `s.trackingServerSecure` variable es una cadena que contiene la ubicación para enviar solicitudes de imagen. Es casi siempre un subdominio del sitio. Las prácticas de privacidad modernas en los navegadores suelen hacer que las cookies de terceros no sean fiables. Si esta variable está en blanco, utiliza el valor en la `s.trackingServer` variable.

El valor de esta variable es casi siempre un dominio de origen, como `data.example.com`. Consulte Cookies de [origen en Experience Cloud](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-first-party.html) en la guía del usuario de los servicios principales para obtener más información sobre el proceso de cookies de origen.

El individuo que configura inicialmente la implementación de cookie de origen también define el dominio y subdominio utilizados. Por ejemplo:

```js
s.trackingServerSecure = "data.example.com";
```

Los registros CNAME normalmente apuntan a un subdominio en `ssl.d1.sc.omtrdc.net`.

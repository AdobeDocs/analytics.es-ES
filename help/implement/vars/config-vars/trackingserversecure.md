---
title: trackingServerSecure
description: Determinar la ubicación a la que se envían las solicitudes de imagen en páginas HTTPS.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# trackingServerSecure

Adobe recopila datos en el sitio mediante la recepción de una solicitud de imagen generada por el visitante. La variable `trackingServerSecure` determina la ubicación en la que se envía una solicitud de imagen a través de HTTPS. También determina la ubicación en la que se almacenan las cookies de los visitantes. Si esta variable no se define correctamente, la implementación puede experimentar una pérdida de datos.

>[!IMPORTANT] Si se cambia este valor, AppMeasurement buscará cookies en una ubicación diferente. El recuento de visitantes únicos puede aumentar temporalmente en los informes a medida que las cookies de los visitantes se establecen en la nueva ubicación.

## Servidor de seguimiento SSL en Adobe Experience Platform Launch

[!UICONTROL SSL Tracking Server] es un campo bajo el [!UICONTROL General] acordeón al configurar la extensión de Adobe Analytics.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad deseada.
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. Expanda el [!UICONTROL General] acordeón, que muestra el [!UICONTROL SSL Tracking Server] campo.

Si este campo se deja en blanco, el valor predeterminado es el valor en la variable [`trackingServer`](trackingserver.md).

## s.trackingServerSecure en el editor de código personalizado de AppMeasurement y Launch

La variable `s.trackingServerSecure` es una cadena que contiene la ubicación para enviar solicitudes de imagen. Es casi siempre un subdominio del sitio. Las prácticas de privacidad modernas en los navegadores suelen hacer que las cookies de terceros no sean fiables. Si esta variable está en blanco, utiliza el valor en la variable `s.trackingServer`.

El valor de esta variable es casi siempre un dominio de origen, como `data.example.com`. Consulte [Cookies de origen en Experience Cloud](https://docs.adobe.com/content/help/es-ES/core-services/interface/ec-cookies/cookies-first-party.html) en la guía del usuario de servicios principales para obtener más información sobre el proceso de cookies de origen.

El usuario que configura inicialmente la implementación de cookies de origen también define el dominio y subdominio utilizados. Por ejemplo:

```js
s.trackingServerSecure = "data.example.com";
```

Los registros CNAME normalmente apuntan a un subdominio en `ssl.d1.sc.omtrdc.net`.

---
title: trackingServerSecure
description: Determinar la ubicación a la que se envían las solicitudes de imagen en páginas HTTPS.
exl-id: d5b112f9-f3f6-43ac-8ee5-d9ad8062e380
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 97%

---

# trackingServerSecure

Adobe recopila datos en el sitio mediante la recepción de una solicitud de imagen generada por el visitante. La variable `trackingServerSecure` determina la ubicación en la que se envía una solicitud de imagen a través de HTTPS. También determina la ubicación en la que se almacenan las cookies de los visitantes. Si esta variable no se define correctamente, la implementación puede experimentar una pérdida de datos.

>[!IMPORTANT]
>
>Si se cambia este valor, AppMeasurement buscará cookies en una ubicación diferente. La cantidad de visitantes únicos puede aumentar temporalmente en los informes a medida que las cookies de los visitantes se establecen en la nueva ubicación.

## Servidor de seguimiento SSL en Adobe Experience Platform Launch

[!UICONTROL El servidor de seguimiento SSL] es un campo del acordeón [!UICONTROL General] al configurar la extensión de Adobe Analytics.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad deseada.
3. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Configurar] en Adobe Analytics.
4. Expanda el acordeón [!UICONTROL General], que muestra el campo [!UICONTROL Servidor de seguimiento SSL].

Si este campo se deja en blanco, el valor predeterminado es el valor en la variable [`trackingServer`](trackingserver.md).

## s.trackingServerSecure en el editor de código personalizado de AppMeasurement y Launch

La variable `s.trackingServerSecure` es una cadena que contiene la ubicación para enviar solicitudes de imagen. Es casi siempre un subdominio del sitio. Las prácticas de privacidad modernas en los navegadores suelen hacer que las cookies de terceros no sean fiables. Si esta variable está en blanco, utiliza el valor en la variable `s.trackingServer`.

El valor de esta variable es casi siempre un dominio de origen, como `data.example.com`. Consulte [Cookies de origen en Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html) en la guía del usuario de servicios principales para obtener más información sobre el proceso de cookies de origen.

El usuario que configura inicialmente la implementación de cookies de origen también define el dominio y subdominio utilizados. Por ejemplo:

```js
s.trackingServerSecure = "data.example.com";
```

Los registros CNAME normalmente apuntan a un subdominio en `data.adobedc.net`, `sc.adobedc.net` o `2o7.net`.

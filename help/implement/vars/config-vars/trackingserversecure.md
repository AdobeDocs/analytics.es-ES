---
title: trackingServerSecure
description: Determinar la ubicación a la que se envían las solicitudes de imagen en páginas HTTPS.
feature: Variables
exl-id: d5b112f9-f3f6-43ac-8ee5-d9ad8062e380
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 66%

---

# trackingServerSecure

Adobe recopila datos en el sitio mediante la recepción de una solicitud de imagen generada por el visitante. La variable `trackingServerSecure` determina la ubicación en la que se envía una solicitud de imagen a través de HTTPS. También determina la ubicación en la que se almacenan las cookies de los visitantes. Si esta variable no se define correctamente, la implementación puede experimentar una pérdida de datos.

>[!WARNING]
>
>Si se cambia este valor, AppMeasurement buscará cookies en una ubicación diferente. La cantidad de visitantes únicos puede aumentar temporalmente en los informes a medida que las cookies de los visitantes se establecen en la nueva ubicación.

## Dominio de Edge que utiliza la extensión del SDK web

El SDK web usa [!UICONTROL dominio de Edge] para administrar tanto el servidor de seguimiento como el servidor de seguimiento seguro. Puede establecer el valor [!UICONTROL dominio de Edge] deseado al configurar la extensión del SDK web.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad de etiquetas deseada.
1. Vaya a la pestaña [!UICONTROL Extensions] y, a continuación, haga clic en el botón **[!UICONTROL Configure]** en [!UICONTROL Adobe Experience Platform Web SDK].
1. Establezca el campo de texto **[!UICONTROL dominio de Edge]** deseado.

Consulte [Configurar la extensión del SDK web de Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html?lang=es) en la documentación del SDK web para obtener más información.

>[!TIP]
>
>Si su organización cambia al SDK web desde una implementación de extensión de AppMeasurement o Analytics, este campo puede utilizar el mismo valor contenido en `trackingServerSecure` (o `trackingServer`).

## Dominio de Edge que implementa manualmente el SDK web

Configure el SDK con [`edgeDomain`](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=es). El campo es una cadena que determina el dominio al que se envían los datos.

```json
alloy("configure", {
  "edgeDomain": "data.example.com"
});
```

## Servidor de seguimiento SSL con la extensión de Adobe Analytics

[!UICONTROL El servidor de seguimiento SSL] es un campo del acordeón [!UICONTROL General] al configurar la extensión de Adobe Analytics.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad de etiquetas deseada.
3. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón **[!UICONTROL Configurar]** en Adobe Analytics.
4. Expanda el acordeón [!UICONTROL General], que muestra el campo [!UICONTROL Servidor de seguimiento SSL].

Si este campo se deja en blanco, el valor predeterminado es el valor en la variable [`trackingServer`](trackingserver.md).

## s.trackingServerSecure en el AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `s.trackingServerSecure` es una cadena que contiene la ubicación para enviar solicitudes de imagen. Es casi siempre un subdominio del sitio. Las prácticas de privacidad modernas en los navegadores suelen hacer que las cookies de terceros no sean fiables. Si esta variable está en blanco, utiliza el valor en la variable `s.trackingServer`.

El valor de esta variable es casi siempre un dominio de origen, como `data.example.com`. Consulte [Cookies de origen en Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html?lang=es) en la guía del usuario de servicios principales para obtener más información sobre el proceso de cookies de origen.

El usuario que configura inicialmente la implementación de cookies de origen también define el dominio y subdominio utilizados. Por ejemplo:

```js
s.trackingServerSecure = "data.example.com";
```

Los registros CNAME normalmente apuntan a un subdominio en `data.adobedc.net`, `sc.adobedc.net` o `2o7.net`.

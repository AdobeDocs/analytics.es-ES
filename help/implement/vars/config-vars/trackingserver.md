---
title: trackingServer
description: Determinar la ubicación en la que se envían las solicitudes de imagen.
feature: Variables
exl-id: bcc23286-4dd5-45ac-ac6f-7b60e95cb798
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 69%

---

# trackingServer

Adobe recopila datos en el sitio mediante la recepción de una solicitud de imagen generada por el visitante. La variable `trackingServer` determina la ubicación a la que se envía una solicitud de imagen. Si esta variable no se define correctamente, la implementación puede experimentar una pérdida de datos.

>[!WARNING]
>
>Si se cambia este valor, AppMeasurement buscará cookies en una ubicación diferente. La cantidad de visitantes únicos puede aumentar temporalmente en los informes a medida que las cookies de los visitantes se establecen en la nueva ubicación.

## Dominio perimetral con la extensión SDK web

El SDK web utiliza [!UICONTROL Dominio perimetral] para gestionar el servidor de seguimiento y el servidor de seguimiento seguro. Puede configurar la [!UICONTROL Dominio perimetral] al configurar la extensión del SDK web.

1. Iniciar sesión en [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) uso de sus credenciales de Adobe ID.
1. Haga clic en la propiedad de etiquetas deseada.
1. Vaya a la [!UICONTROL Extensiones] y, a continuación, haga clic en la pestaña **[!UICONTROL Configurar]** botón debajo de [!UICONTROL SDK web de Adobe Experience Platform].
1. Configure los **[!UICONTROL Dominio perimetral]** campo de texto.

Consulte [Configurar la extensión del SDK web de Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html) en la documentación del SDK web para obtener más información.

>[!TIP]
>
>Si su organización se traslada al SDK web desde una implementación de extensión de AppMeasurement o Analytics, este campo puede utilizar el mismo valor contenido en `trackingServerSecure` (o `trackingServer`).

## Dominio perimetral que implementa manualmente el SDK web

Configuración del SDK mediante [`edgeDomain`](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=es). El campo es una cadena que determina el dominio al que enviar los datos.

```json
alloy("configure", {
  "edgeDomain": "data.example.com"
});
```

## Servidor de seguimiento con la extensión Adobe Analytics

Servidor de seguimiento es un campo del acordeón [!UICONTROL General] al configurar la extensión de Adobe Analytics.

1. Iniciar sesión en [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) uso de sus credenciales de Adobe ID.
2. Haga clic en la propiedad de etiquetas deseada.
3. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón **[!UICONTROL Configurar]** en Adobe Analytics.
4. Expanda el acordeón [!UICONTROL General], que muestra el campo [!UICONTROL Servidor de seguimiento].

Si este campo se deja en blanco, el valor predeterminado es `[rsid].data.adobedc.net`.

## s.trackingServer en AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `s.trackingServer` es una cadena que contiene la ubicación para enviar datos.

## Determinar el valor de `trackingServer`

El valor de esta variable depende de si utiliza cookies de origen o cookies de terceros. Adobe recomienda usar cookies de origen en la implementación.

### Cookies de origen

Si utiliza una implementación de cookies de origen, es probable que alguien de su organización ya haya completado el proceso de cookies de origen. Consulte [Cookies de origen en Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html?lang=es) en la guía del usuario de servicios principales para obtener más información sobre el proceso de cookies de origen.

El usuario que configura inicialmente la implementación de cookies de origen también define el dominio y subdominio utilizados. Por ejemplo:

```js
s.trackingServer = "data.example.com";
```

### Cookies de terceros

>[!TIP]
>
>El aumento de las prácticas de privacidad en los exploradores modernos hace que las cookies de terceros sean menos fiables. Adobe recomienda seguir el flujo de trabajo de las cookies de origen.

Si utiliza una implementación de cookies de terceros, el valor para `trackingServer` es un subdominio de `data.adobedc.net`. Por ejemplo:

```js
s.trackingServer = "example.data.adobedc.net";
```

Elija un subdominio único de su organización, que es poco probable que elija otra organización que utilice Adobe Analytics.  Se recomienda el área de nombres del visitante asignado a su organización.  Asegúrese de que todas las implementaciones de su organización utilicen el mismo servidor de seguimiento. Puede resultar útil mantener esta información en un [documento de diseño de solución](../../prepare/solution-design.md).

Es posible que su organización ya esté utilizando un servidor de seguimiento de terceros en los dominios `sc.omtrdc.net` o `2o7.net`.  Estos se utilizaban principalmente en versiones anteriores de Adobe Analytics y siguen siendo válidos.

>[!NOTE]
>
>No utilice subdominios más profundos que `example.data.adobedc.net`. Por ejemplo, `custom.example.data.adobedc.net` no es un servidor de seguimiento válido.

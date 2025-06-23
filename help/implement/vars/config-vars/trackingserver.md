---
title: trackingServer
description: Determinar la ubicación en la que se envían las solicitudes de imagen.
feature: Appmeasurement Implementation
exl-id: bcc23286-4dd5-45ac-ac6f-7b60e95cb798
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '702'
ht-degree: 52%

---

# trackingServer

Adobe recopila datos en el sitio mediante la recepción de una solicitud de imagen generada por el visitante. La variable `trackingServer` determina la ubicación a la que se envía una solicitud de imagen. Si esta variable no se define correctamente, la implementación puede experimentar una pérdida de datos.

>[!WARNING]
>
>Si se cambia este valor, AppMeasurement buscará cookies en una ubicación diferente. La cantidad de visitantes únicos puede aumentar temporalmente en los informes a medida que las cookies de los visitantes se establecen en la nueva ubicación.

## Dominio de Edge que utiliza la extensión de Web SDK

Web SDK usa [!UICONTROL dominio de Edge] para administrar tanto el servidor de seguimiento como el servidor de seguimiento seguro. Puede establecer el valor [!UICONTROL dominio de Edge] deseado al configurar la extensión de Web SDK.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad de etiquetas deseada.
1. Vaya a la pestaña [!UICONTROL Extensions] y, a continuación, haga clic en el botón **[!UICONTROL Configure]** en [!UICONTROL Adobe Experience Platform Web SDK].
1. Establezca el campo de texto **[!UICONTROL dominio de Edge]** deseado.

Consulte [Configurar la extensión de Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html?lang=es) en la documentación de Web SDK para obtener más información.

>[!TIP]
>
>Si su organización se desplaza a Web SDK desde una implementación de extensión de AppMeasurement o Analytics, este campo puede utilizar el mismo valor contenido en `trackingServerSecure` (o `trackingServer`).

## Dominio de Edge que implementa manualmente Web SDK

Configure SDK usando [`edgeDomain`](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=es). El campo es una cadena que determina el dominio al que se envían los datos.

```json
alloy("configure", {
  "edgeDomain": "data.example.com"
});
```

## Servidor de seguimiento con la extensión de Adobe Analytics

Servidor de seguimiento es un campo del acordeón [!UICONTROL General] al configurar la extensión de Adobe Analytics.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad de etiquetas deseada.
3. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón **[!UICONTROL Configurar]** en Adobe Analytics.
4. Expanda el acordeón [!UICONTROL General], que muestra el campo [!UICONTROL Servidor de seguimiento].

Si este campo se deja en blanco, el valor predeterminado es `[rsid].data.adobedc.net`.

## s.trackingServer en el editor de código personalizado de la extensión de AppMeasurement

La variable `s.trackingServer` es una cadena que contiene la ubicación para enviar datos.

## Consideraciones para determinar el valor de `trackingServer`

Puede elegir utilizar los dominios del servidor de seguimiento de Adobe (por ejemplo, `adobedc.net`) o puede pasar por un proceso especial para configurar un servidor de seguimiento que coincida con el dominio de sus sitios (por ejemplo, `data.mydomain.com`), también conocido como implementación CNAME. Tener un servidor de seguimiento que coincida con el dominio del sitio puede tener algunas ventajas según otros aspectos de la implementación. Cuando el servidor de seguimiento no coincide con el dominio de la página actual, las cookies configuradas por AppMeasurement deben configurarse como de terceros. Si el explorador no admite cookies de terceros, esta discrepancia puede interferir con ciertas funciones de Analytics:

- Configuración de identificadores: Si utiliza el servicio de identidad de Experience Cloud, el servidor de seguimiento no afecta a la forma en que se configuran las cookies. Sin embargo, si utiliza identificadores heredados de Analytics (también conocidos como cookie `s_vi`) y el servidor de recopilación no coincide con el dominio actual, las cookies deben configurarse como de terceros. En este caso, si el explorador bloquea las cookies de terceros, Analytics establece un identificador de reserva (`s_fid`) de origen en lugar de la cookie estándar `s_vi`.
- El seguimiento de vínculos no funciona para vínculos internos.
- Activity Map no funciona para vínculos internos.
- Comprobación de cookies.

### Cookies de origen

Si utiliza una implementación de cookies de origen, es probable que alguien de su organización ya haya completado el proceso de cookies de origen. Consulte [Cookies de origen en Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html?lang=es) en la guía del usuario de servicios principales para obtener más información sobre el proceso de cookies de origen.

El usuario que configura inicialmente la implementación de cookies de origen también define el dominio y subdominio utilizados. Por ejemplo:

```js
s.trackingServer = "data.example.com";
```

### Servidor de seguimiento de terceros

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

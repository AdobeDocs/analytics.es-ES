---
title: trackingServer
description: Determinar la ubicación en la que se envían las solicitudes de imagen.
translation-type: tm+mt
source-git-commit: dfe2b09b2ee287219d18099c51b6fbd7c86bab21
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 91%

---


# trackingServer

Adobe recopila datos en el sitio mediante la recepción de una solicitud de imagen generada por el visitante. La variable `trackingServer` determina la ubicación a la que se envía una solicitud de imagen. Si esta variable no se define correctamente, la implementación puede experimentar una pérdida de datos.

>[!IMPORTANT]
>
>Si se cambia este valor, AppMeasurement buscará cookies en una ubicación diferente. El recuento de visitantes únicos puede aumentar temporalmente en los informes a medida que las cookies de los visitantes se establecen en la nueva ubicación.

## Servidor de seguimiento en Adobe Experience Platform Launch

Servidor de seguimiento es un campo del acordeón [!UICONTROL General] al configurar la extensión de Adobe Analytics.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad deseada.
3. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Configurar] en Adobe Analytics.
4. Expanda el acordeón [!UICONTROL General], que muestra el campo [!UICONTROL Servidor de seguimiento].

Si este campo se deja en blanco, el valor predeterminado es `[rsid]sc.adobedc.net`.

## s.trackingServer en el editor de código personalizado de AppMeasurement y Launch

La variable `s.trackingServer` es una cadena que contiene la ubicación para enviar datos.

>[!TIP]
>
>Algunas implementaciones dirigen los datos a `2o7.net`. Aunque este dominio de recopilación de datos es válido, no utiliza la recopilación de datos regionales. Las implementaciones que utilizan `2o7.net` sufren tiempos de respuesta de solicitudes de imagen ligeramente más altos.

## Determinar el valor de trackingServer

El valor de esta variable depende de si utiliza cookies de origen o cookies de terceros. Adobe recomienda usar cookies de origen en la implementación.

### Cookies de origen

Si utiliza una implementación de cookies de origen, es probable que alguien de su organización ya haya completado el proceso de cookies de origen. Consulte [Cookies de origen en Experience Cloud](https://docs.adobe.com/content/help/es-ES/core-services/interface/ec-cookies/cookies-first-party.html) en la guía del usuario de servicios principales para obtener más información sobre el proceso de cookies de origen.

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

Elija un subdominio exclusivo de su organización, que es poco probable que elija otra organización que utilice Adobe Analytics.  Se recomienda la Área de nombres de visitante asignada a su organización.  Asegúrese de que todas las implementaciones de su organización utilicen el mismo servidor de seguimiento. Puede resultar útil mantener esta información en un [documento de diseño de solución](../../prepare/solution-design.md).

Es posible que su organización ya esté utilizando un servidor de seguimiento de terceros en los `sc.adobedc.net` dominios o `2o7.net` .  Estos se utilizaban principalmente en versiones anteriores de Adobe Analytics y siguen siendo válidos.

>[!NOTE]
>
>No utilice subdominios más profundos que `example.data.adobedc.net`. Por ejemplo, `custom.example.data.adobedc.net` no es un servidor de seguimiento válido.

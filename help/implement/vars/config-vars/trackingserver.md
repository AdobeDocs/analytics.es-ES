---
title: trackingServer
description: Determinar la ubicación en la que se envían las solicitudes de imagen.
translation-type: tm+mt
source-git-commit: 979a95ca749a3e21c4ddf48ba2d2a95672938a20

---


# trackingServer

Adobe recopila datos en el sitio mediante la recepción de una solicitud de imagen generada por el visitante. La `trackingServer` variable determina la ubicación en la que se envía una solicitud de imagen. Si esta variable no se define correctamente, la implementación puede experimentar una pérdida de datos.

> [!IMPORTANT] Si se cambia este valor, AppMeasurement buscará cookies en una ubicación diferente. El recuento de visitantes únicos puede aumentar temporalmente en los informes a medida que las cookies de los visitantes se establecen en la nueva ubicación.

## Servidor de seguimiento en Adobe Experience Platform Launch

Servidor de seguimiento es un campo de acuerdo [!UICONTROL General] al configurar la extensión de Adobe Analytics.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Haga clic en la propiedad que desee.
3. Vaya a la ficha [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Configurar] en Adobe Analytics.
4. Expanda el acordeón [!UICONTROL General] , que muestra el campo Servidor [!UICONTROL de] seguimiento.

Si este campo se deja en blanco, el valor predeterminado es `[rsid].112.2o7.net`.

## s.trackingServer en AppMeasurement e inicie el editor de código personalizado

La `s.trackingServer` variable es una cadena que contiene la ubicación para enviar datos.

> [!TIP] Algunas implementaciones señalan los datos a `2o7.net`. Aunque este dominio de recopilación de datos es válido, no utiliza la recopilación de datos regionales. Las implementaciones que utilizan `2o7.net` ven tiempos de respuesta de solicitudes de imagen ligeramente más altos.

## Determinar el valor de trackingServer

El valor de esta variable depende de si utiliza cookies de origen o cookies de terceros. Adobe recomienda encarecidamente usar cookies de origen en la implementación.

### Cookies de origen

Si utiliza una implementación de cookie de origen, es probable que alguien de su organización ya haya completado el proceso de cookie de origen. Consulte Cookies de [origen en Experience Cloud](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-first-party.html) en la guía del usuario de los servicios principales para obtener más información sobre el proceso de cookies de origen.

El individuo que configura inicialmente la implementación de cookie de origen también define el dominio y subdominio utilizados. Por ejemplo:

```js
s.trackingServer = "data.example.com";
```

Normalmente, los registros CNAME ya están configurados y apuntan a `sc.omtrdc.net`. El dominio `2o7.net` es también un destino CNAME válido, que se utiliza principalmente en versiones anteriores de Adobe Analytics.

### Cookies de terceros

> [!TIP] El aumento de las prácticas de privacidad en los exploradores modernos hace que las cookies de terceros sean menos confiables. Adobe recomienda seguir el flujo de trabajo de las cookies de origen.

Si utiliza una implementación de cookies de terceros, el valor para `trackingServer` es un subdominio de `sc.omtrdc.net`. Por ejemplo:

```js
s.trackingServer = "example.sc.omtrdc.net";
```

Elija un subdominio exclusivo de su organización, que es poco probable que elija otra organización que utilice Adobe Analytics. Asegúrese de que todas las implementaciones de su organización utilicen el mismo servidor de seguimiento. Puede resultar útil mantener esta información en un documento [de diseño de](../../prepare/solution-design.md)solución.

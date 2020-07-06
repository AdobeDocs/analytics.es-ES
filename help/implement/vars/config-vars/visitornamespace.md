---
title: visitorNameSpace
description: Variable retirada que determinó el dominio de la cookie.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 100%

---


# visitorNamespace

>[!IMPORTANT]
>
>Esta variable está retirada. Utilice [`trackingServer`](trackingserver.md) en su lugar.

En versiones anteriores de Adobe Analytics, AppMeasurement utilizaba la variable `visitorNameSpace` para ayudar a determinar el subdominio de `2o7.net` donde se almacenan las cookies de los visitantes. El aumento de las prácticas de privacidad en los exploradores modernos hace que las cookies de terceros sean menos fiables. Con la introducción de las variables `trackingServer` y [`trackingServerSecure`](trackingserversecure.md), ya no es necesario `visitorNameSpace`.

>[!TIP]
>
>Adobe recomienda el uso de cookies de origen en el sitio. Las cookies de origen no utilizan esta variable.

## Espacio de nombres de visitante en Adobe Experience Platform Launch

El [!UICONTROL espacio de nombres del visitante] es un campo en el acordeón [!UICONTROL Cookies] al configurar la extensión de Adobe Analytics.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad deseada.
3. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Configurar] en Adobe Analytics.
4. Expanda el acordeón [!UICONTROL Cookies], que muestra el campo [!UICONTROL Espacio de nombres del visitante].

Adobe recomienda evitar este campo. Utilice `trackingServer` y `trackingServerSecure` en su lugar.

## s.visitorNamespace en el editor de código personalizado de AppMeasurement y Launch

La variable `s.visitorNamespace` es una cadena que contiene un valor único por organización. Las bibliotecas antiguas de AppMeasurement incluían automáticamente este valor único al descargarlo de versiones anteriores de Adobe Analytics. Las bibliotecas actuales de AppMeasurement no utilizan esta variable a menos que `trackingServer` y `trackingServerSecure` se establezcan.

Si su organización aún requiere esta variable, elija un valor que represente a su organización. Puede almacenar este valor en un [documento de diseño de solución](../../prepare/solution-design.md).

```js
// If trackingServer is not set, cookies are stored under example.112.2o7.net
s.visitorNameSpace = "example";
```

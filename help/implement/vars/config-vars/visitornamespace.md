---
title: visitorNameSpace
description: Variable retirada que determinó el dominio de la cookie.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# visitorNamespace

> [!IMPORTANT] Esta variable está retirada. Use [`trackingServer`](trackingserver.md) en su lugar.

En versiones anteriores de Adobe Analytics, AppMeasurement utilizaba la `visitorNameSpace` variable para determinar el subdominio del `2o7.net` lugar donde se almacenan las cookies de los visitantes. El aumento de las prácticas de privacidad en los exploradores modernos hace que las cookies de terceros sean menos confiables. Con la introducción de las `trackingServer` variables y [`trackingServerSecure`](trackingserversecure.md) , ya no `visitorNameSpace` es necesario.

> [!TIP] Adobe recomienda el uso de cookies de origen en el sitio. Las cookies de origen no utilizan esta variable.

## Espacio de nombres de visitante en Adobe Experience Platform Launch

[!UICONTROL Visitor Namespace] es un campo bajo el [!UICONTROL Cookies] acordeón al configurar la extensión de Adobe Analytics.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Haga clic en la propiedad que desee.
3. Vaya a la [!UICONTROL Extensions] ficha y, a continuación, haga clic en el [!UICONTROL Configure] botón situado debajo de Adobe Analytics.
4. Expanda el [!UICONTROL Cookies] acordeón, que muestra el [!UICONTROL Visitor Namespace] campo.

Adobe recomienda no utilizar este campo. Utilice `trackingServer` y `trackingServerSecure` en su lugar.

## s.visitorNamespace en el editor de código personalizado AppMeasurement e Launch

La `s.visitorNamespace` variable es una cadena que contiene un valor único por organización. Las bibliotecas antiguas de AppMeasurement incluían automáticamente este valor único al descargarlo de versiones anteriores de Adobe Analytics. Las bibliotecas actuales de AppMeasurement no utilizan esta variable a menos `trackingServer` que `trackingServerSecure` se establezcan.

Si su organización aún requiere esta variable, elija un valor que represente a su organización. Puede almacenar este valor en un documento [de diseño de](../../prepare/solution-design.md)solución.

```js
// If trackingServer is not set, cookies are stored under example.112.2o7.net
s.visitorNameSpace = "example";
```

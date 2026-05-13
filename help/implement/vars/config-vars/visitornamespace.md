---
title: visitorNameSpace
description: (Retirado) Se ha ayudado a determinar el dominio de cookies de terceros.
feature: Appmeasurement Implementation
exl-id: 4fea35c0-9998-4438-a2ca-af65a35a449e
role: Admin, Developer
TQID: https://experienceleague.adobe.com/y9oXzSzgN-s8gVrdHs0nFRm0ASSbUPzlkW-V6u1GnMg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 226
ht-degree: 89%

---

# visitorNamespace

>[!IMPORTANT]
>
>Esta variable está retirada. Utilice [`trackingServer`](trackingserver.md) en su lugar.

En versiones anteriores de Adobe Analytics, AppMeasurement utilizaba la variable `visitorNameSpace` para ayudar a determinar el subdominio de `2o7.net` donde se almacenan las cookies de los visitantes. El aumento de las prácticas de privacidad en los exploradores modernos hace que las cookies de terceros sean menos fiables. Con la introducción de las variables `trackingServer` y [`trackingServerSecure`](trackingserversecure.md), ya no es necesario `visitorNameSpace`.

>[!TIP]
>
>Adobe recomienda el uso de cookies de origen en el sitio. Las cookies de origen no utilizan esta variable.

## Espacio de nombres de visitante con la extensión Adobe Analytics

El [!UICONTROL espacio de nombres del visitante] es un campo en el acordeón [!UICONTROL Cookies] al configurar la extensión de Adobe Analytics.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad de etiquetas deseada.
3. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón **[!UICONTROL Configurar]** en Adobe Analytics.
4. Expanda el acordeón [!UICONTROL Cookies], que muestra el campo [!UICONTROL Espacio de nombres del visitante].

Adobe recomienda evitar este campo. Utilice `trackingServer` y `trackingServerSecure` en su lugar.

## s.visitorNamespace en AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `s.visitorNamespace` es una cadena que contiene un valor único por organización. Las bibliotecas antiguas de AppMeasurement incluían automáticamente este valor único al descargarlo de versiones anteriores de Adobe Analytics. Las bibliotecas actuales de AppMeasurement no utilizan esta variable a menos que `trackingServer` y `trackingServerSecure` se establezcan.

Si su organización aún requiere esta variable, elija un valor que represente a su organización. Puede almacenar este valor en un [documento de diseño de solución](../../prepare/solution-design.md).

```js
// If trackingServer is not set, cookies are stored under example.112.2o7.net
s.visitorNameSpace = "example";
```

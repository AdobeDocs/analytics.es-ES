---
title: linkURL
description: Omitir la URL del vínculo generado automáticamente que AppMeasurement utiliza en las llamadas de seguimiento de vínculos.
feature: Appmeasurement Implementation
exl-id: 15d6e423-d9fc-4f84-ad39-0bd91399cde4
role: Admin, Developer
TQID: https://experienceleague.adobe.com/O8Bd28njZQDnffeUwCiNGNSNRHk4FU-z48r4pt7Eths
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 204
ht-degree: 34%

---

# linkURL

Cada vez que se envía una llamada de seguimiento de vínculos a Adobe, AppMeasurement detecta la dirección URL en la que se hizo clic. Esta dirección URL ayuda a determinar el tipo de vínculo, como los vínculos de descarga y de salida. Utilice la variable `linkURL` para anular la dirección URL detectada.

No hay dimensiones en Analysis Workspace que informen sobre esta variable. Rellena la columna `page_event_var1` en [Fuentes de datos](/help/export/analytics-data-feed/data-feed-overview.md). Si desea rastrear la dirección URL de un vínculo en el que se hizo clic, Adobe recomienda usar una variable personalizada, como [Prop](../page-vars/prop.md). El uso de [Activity Map](/help/analyze/activity-map/overview.md) puede ayudar a optimizar la recopilación de datos para los vínculos en los que se hizo clic.

## Vincular URL mediante Web SDK

La dirección URL del vínculo está asignada a las siguientes variables:

* [objeto XDM](/help/implement/aep-edge/xdm-var-mapping.md): `web.webInteraction.URL`
* [Objeto de datos](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.linkURL` o `data.__adobe.analytics.pev1`

## URL de vínculo con la extensión Adobe Analytics

No hay ningún campo dedicado en la extensión de Adobe Analytics para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.linkURL en AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `s.linkURL` es una cadena que contiene la dirección URL completa del vínculo donde se hizo clic. Esta variable no rellena ninguna dimensión disponible en los informes.

```js
s.linkURL = "https://example.com";
```

Si no se establece el tercer argumento del método [tl()](../functions/tl-method.md), se utiliza la variable `linkURL` en su lugar.

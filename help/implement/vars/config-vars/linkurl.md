---
title: linkURL
description: Omitir la URL del vínculo generado automáticamente que AppMeasurement utiliza en las llamadas de seguimiento de vínculos.
feature: Appmeasurement Implementation
exl-id: 15d6e423-d9fc-4f84-ad39-0bd91399cde4
role: Admin, Developer
source-git-commit: 7176e068dd05c5589d741f3194d2ad5d795e017d
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 37%

---

# linkURL

Cada vez que se envía una llamada de seguimiento de vínculos a Adobe, AppMeasurement detecta la dirección URL en la que se hizo clic. Esta dirección URL ayuda a determinar el tipo de vínculo, como los vínculos de descarga y de salida. Utilice la variable `linkURL` para anular la dirección URL detectada.

No hay dimensiones en Analysis Workspace que informen sobre esta variable. Rellena la columna `page_event_var1` en [Fuentes de datos](/help/export/analytics-data-feed/data-feed-overview.md). Si desea rastrear la dirección URL de un vínculo en el que se hizo clic, Adobe recomienda usar una variable personalizada, como [Prop](../page-vars/prop.md).

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

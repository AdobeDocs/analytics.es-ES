---
title: linkURL
description: Omitir la URL del vínculo generado automáticamente que AppMeasurement utiliza en las llamadas de seguimiento de vínculos.
feature: Variables
exl-id: 15d6e423-d9fc-4f84-ad39-0bd91399cde4
role: Admin, Developer
source-git-commit: 8be75c04177e97949811c17c7a87b04cce7b3de4
workflow-type: tm+mt
source-wordcount: '158'
ht-degree: 65%

---

# linkURL

Cada vez que se envía una llamada de seguimiento de vínculos a Adobe, los servidores de recopilación de datos detectan automáticamente la dirección URL. Utilice la variable `linkURL` para anular la dirección URL detectada.

No hay dimensiones en Analysis Workspace que informen sobre esta variable. Se rellena el `page_event_var1` columna en [Fuentes de datos](/help/export/analytics-data-feed/data-feed-overview.md).

## Vincular URL mediante el SDK web

La dirección URL del vínculo está asignada a las siguientes variables:

* [Objeto XDM](/help/implement/aep-edge/xdm-var-mapping.md): `web.webInteraction.URL`
* [Objeto de datos](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.linkURL` o `data.__adobe.analytics.pev1`

## URL de vínculo con la extensión Adobe Analytics

No hay ningún campo dedicado en la extensión de Adobe Analytics para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.linkURL en el AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `s.linkURL` es una cadena que contiene la dirección URL del explorador cuando se hizo clic en el vínculo. Esta variable no rellena ninguna dimensión disponible en los informes.

```js
s.linkURL = "https://example.com";
```

Si no se establece el tercer argumento del método [tl()](../functions/tl-method.md), se utiliza la variable `linkURL` en su lugar.

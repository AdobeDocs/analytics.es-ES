---
title: linkURL
description: Omitir la URL del vínculo generado automáticamente que AppMeasurement utiliza en las llamadas de seguimiento de vínculos.
feature: Variables
exl-id: 15d6e423-d9fc-4f84-ad39-0bd91399cde4
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '144'
ht-degree: 61%

---

# linkURL

Cada vez que se envía una llamada de seguimiento de vínculos a Adobe, los servidores de recopilación de datos detectan automáticamente la dirección URL. Utilice la variable `linkURL` para anular la dirección URL detectada.

## Vincular URL con el SDK web

La dirección URL del vínculo es [asignado para Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) en el campo XDM `web.webInteraction.URL`.

## URL de vínculo con la extensión de Adobe Analytics

No hay un campo específico en la extensión de Adobe Analytics para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.linkURL en AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `s.linkURL` es una cadena que contiene la dirección URL del explorador cuando se hizo clic en el vínculo. Esta variable no rellena ninguna dimensión disponible en los informes.

```js
s.linkURL = "https://example.com";
```

Si no se establece el tercer argumento del método [tl()](../functions/tl-method.md), se utiliza la variable `linkURL` en su lugar.

---
title: trackExternalLinks
description: Habilite o deshabilite el seguimiento automático de vínculos de salida.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# trackExternalLinks

Adobe ofrece la capacidad de rastrear vínculos salientes sin configurar manualmente el [`tl()`](../functions/tl-method.md) método para cada vínculo de salida. Active esta variable si desea utilizar el seguimiento automático de vínculos para los vínculos de salida.

Cuando está habilitado, AppMeasurement compara cualquier URL de vínculo en el que se haga clic con los valores en [`linkInternalFilters`](linkinternalfilters.md) y [`linkExternalFilters`](linkexternalfilters.md). Si hay una coincidencia, se activa automáticamente una llamada de seguimiento de vínculos de salida.

## Seguimiento de vínculos salientes en Adobe Experience Platform Launch

Rastrear vínculos salientes es una casilla de verificación debajo del [!UICONTROL Link Tracking] acordeón al configurar la extensión de Adobe Analytics.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Haga clic en la propiedad que desee.
3. Vaya a la [!UICONTROL Extensions] ficha y, a continuación, haga clic en el [!UICONTROL Configure] botón situado debajo de Adobe Analytics.
4. Expanda el [!UICONTROL Link Tracking] acordeón, que muestra la [!UICONTROL Track outbound links] casilla de verificación.

Haga clic en la casilla de verificación para habilitar el seguimiento automático de vínculos de salida.

## s.trackExternalLinks en AppMeasurement e inicie el editor de código personalizado

El `s.trackExternalLinks` es un booleano que habilita o deshabilita el seguimiento automático de vínculos de salida. Si no desea rastrear los vínculos salientes o prefiere llamar manualmente al `tl()` método para rastrear los vínculos de salida, establezca esta variable en `false`.

```js
s.trackDownloadLinks = true;
```

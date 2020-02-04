---
title: trackExternalLinks
description: Habilite o deshabilite el seguimiento automático de vínculos de salida.
translation-type: tm+mt
source-git-commit: 04b97e93a95691132680d4da197dc62eb2b9fdd1

---


# trackExternalLinks

Adobe ofrece la capacidad de rastrear vínculos salientes sin configurar manualmente la `tl()` función para cada vínculo de salida. Active esta variable si desea utilizar el seguimiento automático de vínculos para los vínculos de salida.

Cuando está habilitado, AppMeasurement compara cualquier URL de vínculo en el que se haga clic con los valores en `linkInternalFilters` y `linkExternalFilters`. Si hay una coincidencia, se activa automáticamente una llamada de seguimiento de vínculos de salida.

## Seguimiento de vínculos salientes en Adobe Experience Platform Launch

Rastrear vínculos salientes es una casilla de verificación bajo el [!UICONTROL acordeón Seguimiento] de vínculos al configurar la extensión de Adobe Analytics.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Haga clic en la propiedad que desee.
3. Vaya a la ficha [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Configurar] en Adobe Analytics.
4. Expanda el [!UICONTROL acordeón Seguimiento] de vínculos, que muestra la casilla [!UICONTROL Rastrear vínculos] salientes.

Haga clic en la casilla de verificación para habilitar el seguimiento automático de vínculos de salida.

## s.trackExternalLinks en AppMeasurement e inicie el editor de código personalizado

El `s.trackExternalLinks` es un booleano que habilita o deshabilita el seguimiento automático de vínculos de salida. Si no desea rastrear los vínculos salientes o prefiere llamar manualmente a la `tl()` función para rastrear los vínculos de salida, establezca esta variable en `false`.

```js
s.trackDownloadLinks = true;
```

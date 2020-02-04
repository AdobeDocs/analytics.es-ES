---
title: trackDownloadLinks
description: Habilite o deshabilite el seguimiento automático de vínculos para los vínculos de descarga.
translation-type: tm+mt
source-git-commit: 04b97e93a95691132680d4da197dc62eb2b9fdd1

---


# trackDownLoadLinks

Adobe ofrece la posibilidad de rastrear los vínculos de descarga sin configurar manualmente la `tl()` función para cada vínculo de descarga. Active esta variable si desea utilizar el seguimiento automático de vínculos para los vínculos de descarga.

Cuando está habilitado, AppMeasurement compara cualquier URL de vínculo donde se haga clic con los valores de `downloadLinkFileTypes`. Si hay una coincidencia, se activa automáticamente una llamada de seguimiento de vínculos de descarga.

## Seguimiento de vínculos de descarga en Adobe Experience Platform Launch

Rastrear vínculos de descarga es una casilla de verificación bajo el [!UICONTROL acordeón Seguimiento] de vínculos al configurar la extensión de Adobe Analytics.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Haga clic en la propiedad que desee.
3. Vaya a la ficha [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Configurar] en Adobe Analytics.
4. Expanda el [!UICONTROL acordeón Seguimiento] de vínculos, que muestra la casilla [!UICONTROL Rastrear vínculos] de descarga.

Haga clic en la casilla de verificación para habilitar el seguimiento automático de vínculos de descarga.

## s.trackDownloadLinks en AppMeasurement e inicie el editor de código personalizado

El `s.trackDownloadLinks` es un booleano que habilita o deshabilita el seguimiento automático de vínculos de descarga. Si no desea rastrear los vínculos de descarga o prefiere llamar manualmente a la `tl()` función para rastrear las descargas, establezca esta variable en `false`.

```js
s.trackDownloadLinks = true;
```

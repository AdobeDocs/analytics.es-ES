---
title: trackInlineStats
description: Habilite o deshabilite Activity Map en la implementación.
translation-type: tm+mt
source-git-commit: 979a95ca749a3e21c4ddf48ba2d2a95672938a20

---


# trackInlineStats

Activity Map es una función de Adobe Analytics que recopila datos sobre dónde hacen clic los visitantes y en qué hacen clic. Puede ver estos datos en los informes de Analytics o mediante una superposición de extensión de explorador. Active esta variable si desea utilizar las funciones de Activity Map.

Cuando se habilita, AppMeasurement recopila información sobre el vínculo y envía esos datos en la siguiente solicitud de imagen. La información de cada clic se almacena en una cookie etiquetada `s_sq`.

## Habilitar Clickmap en el lanzamiento de Adobe Experience Platform

[!UICONTROL Al configurar la extensión de Adobe Analytics, la casilla de verificación Habilitar Clickmap] se encuentra debajo del [!UICONTROL acordeón Seguimiento] de vínculos.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Haga clic en la propiedad que desee.
3. Vaya a la ficha [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Configurar] en Adobe Analytics.
4. Amplíe el acordeón Seguimiento [!UICONTROL de] vínculos, que muestra la casilla de verificación [!UICONTROL Activar ClickMap] .

Haga clic en la casilla de verificación para habilitar el seguimiento de Activity Map.

## s.trackInlineStats en el editor de código personalizado AppMeasurement e Launch

El `s.trackInlineStats` es un booleano que habilita o deshabilita el seguimiento de Activity Map. Its default value is `false`. Establezca este valor en `true` si desea habilitar la recopilación de datos de Activity Map.

```js
s.trackInlineStats = true;
```

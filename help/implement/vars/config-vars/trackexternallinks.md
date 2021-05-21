---
title: trackExternalLinks
description: Habilite o deshabilite el seguimiento automático de vínculos de salida.
exl-id: a34d4ffa-ff82-460e-af7d-1a4be85fc631
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '185'
ht-degree: 100%

---

# trackExternalLinks

Adobe ofrece la capacidad de rastrear vínculos salientes sin configurar manualmente el método [`tl()`](../functions/tl-method.md) para cada vínculo de salida. Active esta variable si desea utilizar el seguimiento automático de vínculos para los vínculos de salida.

Cuando está habilitado, AppMeasurement compara cualquier URL de vínculo en el que se haga clic con los valores en [`linkInternalFilters`](linkinternalfilters.md) y [`linkExternalFilters`](linkexternalfilters.md). Si hay una coincidencia, se activa automáticamente una llamada de seguimiento de vínculos de salida.

## Seguimiento de vínculos de salida en Adobe Experience Platform Launch

Rastrear vínculos de salida es una casilla de verificación bajo el acordeón de [!UICONTROL Seguimiento de vínculos] al configurar la extensión de Adobe Analytics.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad deseada.
3. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Configurar] en Adobe Analytics.
4. Expanda el acordeón de [!UICONTROL Seguimiento de vínculos], que muestra la casilla [!UICONTROL Rastrear vínculos de salida].

Haga clic en la casilla de verificación para habilitar el seguimiento automático de vínculos de salida.

## s.trackExternalLinks en el editor de código personalizado de AppMeasurement y Launch

El `s.trackExternalLinks` es un booleano que habilita o deshabilita el seguimiento automático de vínculos de salida. Si no desea rastrear los vínculos de salida o prefiere llamar manualmente al método `tl()` para rastrear los vínculos de salida, debe establecer esta variable como `false`.

```js
s.trackExternalLinks = true;
```

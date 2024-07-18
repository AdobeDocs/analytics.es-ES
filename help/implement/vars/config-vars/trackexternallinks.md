---
title: trackExternalLinks
description: Habilite o deshabilite el seguimiento automático de vínculos de salida.
feature: Variables
exl-id: a34d4ffa-ff82-460e-af7d-1a4be85fc631
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 60%

---

# trackExternalLinks

Adobe ofrece la capacidad de rastrear vínculos salientes sin configurar manualmente el método [`tl()`](../functions/tl-method.md) para cada vínculo de salida. Active esta variable si desea utilizar el seguimiento automático de vínculos para los vínculos de salida.

Cuando está habilitado, AppMeasurement compara cualquier URL de vínculo en el que se haga clic con los valores en [`linkInternalFilters`](linkinternalfilters.md) y [`linkExternalFilters`](linkexternalfilters.md). Si hay una coincidencia, se activa automáticamente una llamada de seguimiento de vínculos de salida.

## Habilitar o deshabilitar la recopilación de clics mediante la extensión del SDK web

Utilice la casilla de verificación [!UICONTROL Habilitar la recopilación de datos con clic] al configurar el SDK web. Esta casilla de verificación gestiona los vínculos de salida y de descarga.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad de etiquetas deseada.
1. Vaya a la pestaña [!UICONTROL Extensions] y, a continuación, haga clic en el botón **[!UICONTROL Configure]** en [!UICONTROL Adobe Experience Platform Web SDK].
1. En [!UICONTROL Recopilación de datos], haga clic en la casilla de verificación **[!UICONTROL Habilitar la recopilación de datos con clic]**.

## Habilitar o deshabilitar la recopilación de clics manualmente mediante la implementación del SDK web

Configure el SDK con [`clickCollectionEnabled`](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html#clickCollectionEnabled). El campo es un booleano que determina si los datos asociados con los clics en vínculos se recopilan automáticamente. Su valor predeterminado es `true`. Establezca este valor en `false` si desea deshabilitar el seguimiento automático de vínculos. Esta configuración administra el seguimiento automático de vínculos tanto para los vínculos de descarga como de salida.

```json
alloy("configure", {
  "clickCollectionEnabled": true
});
```

## Seguimiento de vínculos de salida con la extensión Adobe Analytics

Rastrear vínculos de salida es una casilla de verificación bajo el acordeón de [!UICONTROL Seguimiento de vínculos] al configurar la extensión de Adobe Analytics.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad de etiquetas deseada.
3. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón **[!UICONTROL Configurar]** en Adobe Analytics.
4. Expanda el acordeón de [!UICONTROL Seguimiento de vínculos], que muestra la casilla [!UICONTROL Rastrear vínculos de salida].

Haga clic en la casilla de verificación para habilitar el seguimiento automático de vínculos de salida.

## s.trackExternalLinks en el AppMeasurement y el editor de código personalizado de la extensión de Analytics

El `s.trackExternalLinks` es un booleano que habilita o deshabilita el seguimiento automático de vínculos de salida. Si no desea rastrear los vínculos de salida o prefiere llamar manualmente al método `tl()` para rastrear los vínculos de salida, debe establecer esta variable como `false`.

```js
s.trackExternalLinks = true;
```

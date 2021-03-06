---
title: trackDownloadLinks
description: Habilite o deshabilite el seguimiento automático de vínculos para los vínculos de descarga.
feature: Variables
exl-id: d92f722b-d605-40ad-bb55-ec71219a47e3
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 51%

---

# trackDownLoadLinks

Adobe ofrece la posibilidad de rastrear los vínculos de descarga sin configurar manualmente el método [`tl()`](../functions/tl-method.md) para cada vínculo de descarga. Active esta variable si desea utilizar el seguimiento automático de vínculos para los vínculos de descarga.

Cuando está habilitado, AppMeasurement compara cualquier URL de vínculo donde se haga clic con los valores de [`linkDownloadFileTypes`](linkdownloadfiletypes.md). Si hay una coincidencia, se activa automáticamente una llamada de seguimiento de vínculos de descarga.

## Habilitar o deshabilitar la recopilación de clics mediante la extensión Web SDK

Utilice la variable [!UICONTROL Habilitar la recopilación de datos de clic] al configurar el SDK web. Esta casilla de verificación controla los vínculos de salida y de descarga.

1. Iniciar sesión en [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) uso de sus credenciales de Adobe ID.
1. Haga clic en la propiedad de etiquetas deseada.
1. Vaya a la [!UICONTROL Extensiones] y, a continuación, haga clic en la pestaña **[!UICONTROL Configurar]** botón debajo de [!UICONTROL SDK web de Adobe Experience Platform].
1. En [!UICONTROL Recopilación de datos], haga clic en **[!UICONTROL Habilitar la recopilación de datos de clic]** casilla de verificación.

## Habilitar o deshabilitar la colección de clics implementando manualmente el SDK web

Configuración del SDK mediante [`clickCollectionEnabled`](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html#clickCollectionEnabled). El campo es un booleano que determina si los datos asociados con clics en vínculos se recopilan automáticamente. Su valor predeterminado es `true`. Establezca este valor como `false` si desea deshabilitar el seguimiento automático de vínculos. Esta configuración administra el seguimiento automático de vínculos tanto de descarga como de salida.

```json
alloy("configure", {
  "clickCollectionEnabled": true
});
```

## Seguimiento de vínculos de descarga con la extensión Adobe Analytics

Rastrear vínculos de descarga es una casilla de verificación en el acordeón [!UICONTROL Seguimiento de vínculos] al configurar la extensión de Adobe Analytics.

1. Iniciar sesión en [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) uso de sus credenciales de Adobe ID.
2. Haga clic en la propiedad de etiquetas deseada.
3. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón **[!UICONTROL Configurar]** en Adobe Analytics.
4. Expanda el acordeón [!UICONTROL Seguimiento de vínculos], que muestra la casilla [!UICONTROL Rastrear vínculos de descarga].

Haga clic en la casilla de verificación para habilitar el seguimiento automático de vínculos de descarga.

## s.trackDownloadLinks en AppMeasurement y el editor de código personalizado de la extensión de Analytics

El `s.trackDownloadLinks` es un booleano que habilita o deshabilita el seguimiento automático de vínculos de descarga. Si no desea rastrear los vínculos de descarga o prefiere llamar manualmente al método `tl()` para rastrear las descargas, establezca esta variable como `false`.

```js
s.trackDownloadLinks = true;
```

---
title: trackDownloadLinks
description: Habilite o deshabilite el seguimiento automático de vínculos para los vínculos de descarga.
feature: Appmeasurement Implementation
exl-id: d92f722b-d605-40ad-bb55-ec71219a47e3
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 59%

---

# trackDownLoadLinks

Adobe ofrece la posibilidad de rastrear los vínculos de descarga sin configurar manualmente el método [`tl()`](../functions/tl-method.md) para cada vínculo de descarga. Active esta variable si desea utilizar el seguimiento automático de vínculos para los vínculos de descarga.

Cuando está habilitado, AppMeasurement compara cualquier URL de vínculo donde se haga clic con los valores de [`linkDownloadFileTypes`](linkdownloadfiletypes.md). Si hay una coincidencia, se activa automáticamente una llamada de seguimiento de vínculos de descarga.

## Habilite o deshabilite la recopilación de clics mediante la extensión Web SDK

Utilice la casilla de verificación [!UICONTROL Habilitar la recopilación de datos con clic] al configurar Web SDK. Esta casilla de verificación gestiona los vínculos de salida y de descarga.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad de etiquetas deseada.
1. Vaya a la pestaña [!UICONTROL Extensions] y, a continuación, haga clic en el botón **[!UICONTROL Configure]** en [!UICONTROL Adobe Experience Platform Web SDK].
1. En [!UICONTROL Recopilación de datos], haga clic en la casilla de verificación **[!UICONTROL Habilitar la recopilación de datos con clic]**.

## Habilitar o deshabilitar la recopilación de clics manualmente al implementar Web SDK

Configure SDK usando [`clickCollectionEnabled`](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html#clickCollectionEnabled). El campo es un booleano que determina si los datos asociados con los clics en vínculos se recopilan automáticamente. Su valor predeterminado es `true`. Establezca este valor en `false` si desea deshabilitar el seguimiento automático de vínculos. Esta configuración administra el seguimiento automático de vínculos tanto para los vínculos de descarga como de salida.

```json
alloy("configure", {
  "clickCollectionEnabled": true
});
```

## Seguimiento de vínculos de descarga con la extensión Adobe Analytics

Rastrear vínculos de descarga es una casilla de verificación en el acordeón [!UICONTROL Seguimiento de vínculos] al configurar la extensión de Adobe Analytics.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad de etiquetas deseada.
3. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón **[!UICONTROL Configurar]** en Adobe Analytics.
4. Expanda el acordeón [!UICONTROL Seguimiento de vínculos], que muestra la casilla [!UICONTROL Rastrear vínculos de descarga].

Haga clic en la casilla de verificación para habilitar el seguimiento automático de vínculos de descarga.

## s.trackDownloadLinks en AppMeasurement y el editor de código personalizado de la extensión de Analytics

El `s.trackDownloadLinks` es un booleano que habilita o deshabilita el seguimiento automático de vínculos de descarga. Si no desea rastrear los vínculos de descarga o prefiere llamar manualmente al método `tl()` para rastrear las descargas, establezca esta variable como `false`.

```js
s.trackDownloadLinks = true;
```

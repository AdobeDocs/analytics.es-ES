---
title: trackDownloadLinks
description: Habilite o deshabilite el seguimiento automático de vínculos para los vínculos de descarga.
exl-id: d92f722b-d605-40ad-bb55-ec71219a47e3
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '183'
ht-degree: 100%

---

# trackDownLoadLinks

Adobe ofrece la posibilidad de rastrear los vínculos de descarga sin configurar manualmente el método [`tl()`](../functions/tl-method.md) para cada vínculo de descarga. Active esta variable si desea utilizar el seguimiento automático de vínculos para los vínculos de descarga.

Cuando está habilitado, AppMeasurement compara cualquier URL de vínculo donde se haga clic con los valores de [`linkDownloadFileTypes`](linkdownloadfiletypes.md). Si hay una coincidencia, se activa automáticamente una llamada de seguimiento de vínculos de descarga.

## Seguimiento de vínculos de descarga en Adobe Experience Platform Launch

Rastrear vínculos de descarga es una casilla de verificación en el acordeón [!UICONTROL Seguimiento de vínculos] al configurar la extensión de Adobe Analytics.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad deseada.
3. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Configurar] en Adobe Analytics.
4. Expanda el acordeón [!UICONTROL Seguimiento de vínculos], que muestra la casilla [!UICONTROL Rastrear vínculos de descarga].

Haga clic en la casilla de verificación para habilitar el seguimiento automático de vínculos de descarga.

## s.trackDownloadLinks en el editor de código personalizado de AppMeasurement y Launch

El `s.trackDownloadLinks` es un booleano que habilita o deshabilita el seguimiento automático de vínculos de descarga. Si no desea rastrear los vínculos de descarga o prefiere llamar manualmente al método `tl()` para rastrear las descargas, establezca esta variable como `false`.

```js
s.trackDownloadLinks = true;
```

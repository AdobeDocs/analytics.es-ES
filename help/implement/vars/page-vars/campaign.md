---
title: campaign
description: Rellene la dimensión “Código de seguimiento”.
translation-type: tm+mt
source-git-commit: 7220b99268532adb2e425d52744dbc3efb615953

---


# campaign

La variable `campaign` está dedicada a recopilar códigos de seguimiento en el sitio. En versiones anteriores de Adobe Analytics, se le aplicaba un tratamiento especial en el que podía utilizarse como desglose de la mayoría de las dimensiones. En la versión actual de Adobe Analytics, actúa igual que una eVar.

Esta variable rellena la dimensión “Código de seguimiento”.

## Campaign en Adobe Experience Platform Launch

Puede establecer la campaña durante la configuración de la extensión de Analytics (variables globales) o en reglas.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad deseada.
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. En [!UICONTROL Actions], haga clic en una [!UICONTROL Adobe Analytics - Set Variables] acción existente o en el icono &#39;+&#39;.
5. Establezca el [!UICONTROL Extension] menú desplegable en Adobe Analytics y el valor [!UICONTROL Action Type] en [!UICONTROL Set Variables].
6. Locate the [!UICONTROL Campaign] section.

Puede establecer la campaña como un valor o un parámetro de cadena de consulta.

## s.campaign en el editor de código personalizado de AppMeasurement y Launch

La variable `s.campaign` es una cadena que generalmente contiene un código de seguimiento utilizado en los esfuerzos de marketing. Su longitud máxima es de 255 bytes; los valores superiores a 255 bytes se truncan automáticamente cuando se envían a Adobe.

```js
// Set the campaign variable to a static value
s.campaign = "abc123";

// Collect the cid query string parameter value from the URL
// https://example.com?cid=abc123
s.campaign = s.Util.getQueryParam("cid");
```

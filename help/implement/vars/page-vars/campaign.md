---
title: campaign
description: Rellene la dimensión 'Código de seguimiento'.
translation-type: tm+mt
source-git-commit: c5a60bc9756af2742740dbc6a26a081f55ee3235

---


# campaign

La `campaign` variable está dedicada a recopilar códigos de seguimiento en el sitio. En versiones anteriores de Adobe Analytics, se le aplicaba un tratamiento especial en el que podía utilizarse como desglose de la mayoría de las dimensiones. En la versión actual de Adobe Analytics, actúa igual que una eVar.

Esta variable rellena la dimensión &#39;Código de seguimiento&#39;.

## Campaign en Adobe Experience Platform Launch

Puede configurar la campaña durante la configuración de la extensión de Analytics (variables globales) o en reglas.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Haga clic en la propiedad que desee.
3. Vaya a la ficha [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en una acción existente de [!UICONTROL Adobe Analytics - Establecer variables] o haga clic en el icono &#39;+&#39;.
5. Defina el menú desplegable [!UICONTROL Extensión] en Adobe Analytics y el tipo [!UICONTROL de] acción en [!UICONTROL Establecer variables].
6. Busque la sección [!UICONTROL Campaña] .

Puede establecer campaign en un valor o un parámetro de cadena de consulta.

## s.campaign en el editor de código personalizado AppMeasurement e Launch

La `s.campaign` variable es una cadena que generalmente contiene un código de seguimiento utilizado en los esfuerzos de mercadotecnia. Su longitud máxima es de 255 bytes; los valores superiores a 100 bytes se truncan automáticamente cuando se envían a Adobe.

```js
// Set the campaign variable to a static value
s.campaign = "abc123";

// Collect the cid query string parameter value from the URL
// https://example.com?cid=abc123
s.campaign = s.Util.getQueryParam("cid");
```

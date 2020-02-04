---
title: clearVars
description: Borra los valores siguientes del objeto de instancia. Esta función elimina los elementos (los establece como “undefined”).
translation-type: tm+mt
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# clearVars

Algunas implementaciones, como en aplicaciones de una sola página, requieren que se envíen varias visitas en la misma carga de página. Utilice el `clearVars` método para borrar los valores de las variables de modo que no persistan en las visitas posteriores.

Este método no toma ningún argumento y no devuelve ningún valor. Su único propósito es borrar los valores de variables del objeto de instancia. Este método establece los siguientes elementos en `undefined`:

* `prop1` - `prop75`
* `eVar` - `eVar250`
* `hier1` - `hier5`
* `list1` - `list3`
* `events`
* `products`
* `channel`
* `purchaseID`
* `transactionID`
* `state`
* `zip`
* `campaign`

## Borrar variables en el lanzamiento de Adobe Experience Platform

Configure la acción Borrar variables al configurar una regla.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Haga clic en la propiedad que desee.
3. Vaya a la ficha [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en el icono &#39;+&#39;
5. Defina el menú desplegable [!UICONTROL Extensión] en Adobe Analytics y el tipo [!UICONTROL de] acción en [!UICONTROL Borrar variables].

## s.clearVars() en el editor de código personalizado AppMeasurement e Launch

Puede llamar al `s.clearVars()` método desde cualquier lugar de la implementación después de crear una instancia de objeto de Analytics.

```js
s.clearVars();
```

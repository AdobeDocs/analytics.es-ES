---
title: clearVars
description: Borra los valores siguientes del objeto de instancia. Esta función elimina los elementos (los establece como “undefined”).
feature: Variables
exl-id: 8ecb2b2d-7b66-4232-b0ea-b8c6cdcc1515
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 100%

---

# clearVars

Algunas implementaciones, como en aplicaciones de una sola página, requieren que se envíen varias visitas en la misma carga de página. Utilice el método `clearVars()` para borrar los valores de las variables de modo que no persistan en las visitas posteriores.

Este método no toma ningún argumento y no devuelve ningún valor. Su único propósito es borrar los valores de variables del objeto de instancia. Este método establece los siguientes elementos como `undefined`:

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

## Borrado de variables mediante etiquetas en Adobe Experience Platform

Establezca la acción Borrar variables al configurar una regla.

1. Inicie sesión en la [IU de recopilación de datos](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad deseada.
3. Vaya a la pestaña [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en el icono “+”.
5. Establezca el menú desplegable [!UICONTROL Extensión] en Adobe Analytics y el [!UICONTROL tipo de acción] en [!UICONTROL Borrar variables].

## s.clearVars() en el editor de código personalizado de AppMeasurement y 

Puede llamar al método `s.clearVars()` desde cualquier lugar de la implementación después de crear una instancia de objeto de Analytics.

```js
s.clearVars();
```

---
title: clearVars
description: Borra los valores siguientes del objeto de instancia. Esta función elimina los elementos (los establece como “undefined”).
feature: Variables
exl-id: 8ecb2b2d-7b66-4232-b0ea-b8c6cdcc1515
source-git-commit: 6de20d2fbbab6ded6c92f0c6f3536671f4b2ae46
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 72%

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

## Borrado de variables mediante el SDK web

Cuando se envían datos a Adobe mediante el SDK web, todos los datos XDM se borran automáticamente.

## Borrar variables con la extensión Adobe Analytics

Establezca la acción Borrar variables al configurar una regla.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad de etiquetas deseada.
3. Vaya a la pestaña [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en el icono “+”.
5. Configure las variables [!UICONTROL Extensión] lista desplegable de Adobe Analytics y [!UICONTROL Tipo de acción] a [!UICONTROL Borrar variables].

## s.clearVars() en AppMeasurement y el editor de código personalizado de la extensión de Analytics

Puede llamar al método `s.clearVars()` desde cualquier lugar de la implementación después de crear una instancia de objeto de Analytics.

```js
s.clearVars();
```

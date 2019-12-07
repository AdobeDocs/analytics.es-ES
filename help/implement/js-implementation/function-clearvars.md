---
description: Borra los valores siguientes del objeto de instancia. Esta función elimina los elementos (los establece como “undefined”).
keywords: Analytics Implementation
title: Función s.clearVars()
topic: Developer and implementation
uuid: 43c425bc-15ae-4892-a5a5-e1defcb25ff4
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Función s.clearVars()

Borra los valores siguientes del objeto de instancia. Esta función elimina los elementos (los establece como “undefined”).

* `props`
* `eVars`
* `hier`
* `list`
* `events`
* `eventList`
* `products`
* `productsList`
* `channel`
* `purchaseID`
* `transactionID`
* `state`
* `zip`
* `campaign`

Por ejemplo:

```js
s.clearVars()
```

>[!NOTE]
>
>`clearVars()` se incluye en [AppMeasurement para JavaScript](/help/implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md), pero no está disponible en código H y en versiones anteriores.


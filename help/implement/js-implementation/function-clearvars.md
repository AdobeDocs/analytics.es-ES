---
description: Borra los valores siguientes del objeto de instancia. Esta función elimina los elementos (los establece como “undefined”).
keywords: Implementación de Analytics
seo-description: Borra los valores siguientes del objeto de instancia. Esta función elimina los elementos (los establece como “undefined”).
seo-title: Función s.clearVars()
solution: Analytics
title: Función s.clearVars()
topic: Desarrollador e implementación
uuid: 43c425bc-15ae-4892-a5a5-e1defcb25ff4
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

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

> [!NOTE] `clearVars()` se incluye en [AppMeasurement para JavaScript](../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8), pero no está disponible en código H y en versiones anteriores.


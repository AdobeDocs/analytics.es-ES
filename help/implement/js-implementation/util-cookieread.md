---
description: Obtiene el valor de una cookie.
keywords: Analytics Implementation
subtopic: JavaScript AppMeasurement
title: Util.cookieRead
topic: Developer and implementation
uuid: 825a75c6-b804-4bfe-b23a-907113b8bfa6
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Util.cookieRead

Obtiene el valor de una cookie.

**Sintaxis:**

```
s.Util.cookieRead(key)
```

**Parámetros:**

| Parámetro | Descripción |
|---|---|
| key | (obligatorio) clave para escribir un valor en las cookies. |

**Devuelve:**

Valor de la cookie o una cadena vacía si no se encuentra la cookie.

**Ejemplo:**

```js
var myCookie = s.Util.cookieRead("my_cookie");
```


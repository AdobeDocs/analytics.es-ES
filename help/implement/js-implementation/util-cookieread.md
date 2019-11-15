---
description: Obtiene el valor de una cookie.
keywords: Analytics Implementation
solution: Analytics
subtopic: JavaScript AppMeasurement
title: Util.cookieRead
topic: Developer and implementation
uuid: 825a75c6-b804-4bfe-b23a-907113b8bfa6
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

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


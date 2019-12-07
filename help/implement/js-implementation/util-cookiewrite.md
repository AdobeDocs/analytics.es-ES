---
description: Escribe un valor en una cookie.
keywords: Analytics Implementation
subtopic: JavaScript AppMeasurement
title: Util.cookieWrite
topic: Developer and implementation
uuid: 8d526e4c-6d7a-4119-9434-d7ce4fbb7577
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Util.cookieWrite

Escribe un valor en una cookie.

**Sintaxis:**

```
s.Util.cookieWrite(key, value [,expire])
```

**Parámetros:**

| Parámetro | Descripción |
|---|---|
| key | (obligatorio) clave para escribir un valor en las cookies. |
| valor | (opcional) valor para escribir en las cookies. |
| expire | (opcional) objeto de fecha que contiene la fecha de caducidad de la cookie. De forma predeterminada, se usa una cookie de sesión. |

**Devuelve:**

**Ejemplo:**

```js
//set a cookie with an expiration 6 months from now 
var date = new Date(); 
date.setMonth(date.getMonth() + 6); 
var success = s.Util.cookieWrite("my_cookie", "my_value", date);
```


---
description: Escribe un valor en una cookie.
keywords: Implementación de Analytics
seo-description: Escribe un valor en una cookie.
seo-title: Util.cookieWrite
solution: Analytics
subtopic: JavaScript AppMeasurement
title: Util.cookieWrite
topic: Desarrollador e implementación
uuid: 8d526e4c-6d7a-4119-9434-d7ce4fbb7577
translation-type: ht
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

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


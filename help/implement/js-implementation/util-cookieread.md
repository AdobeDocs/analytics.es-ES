---
description: Obtiene el valor de una cookie.
keywords: Implementación de Analytics
seo-description: Obtiene el valor de una cookie.
seo-title: Util.cookieRead
solution: Analytics
subtopic: JavaScript AppMeasurement
title: Util.cookieRead
topic: Desarrollador e implementación
uuid: 825a75c6-b804-4bfe-b23a-907113b8bfa6
translation-type: ht
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

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


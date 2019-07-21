---
description: Obtiene el valor de una cookie.
keywords: Implementación de Analytics
seo-description: Obtiene el valor de una cookie.
seo-title: Util.cookieRead
solution: Analytics
subtopic: JavaScript AppMeasurement
title: Util.cookieRead
topic: Desarrollador e implementación
uuid: 825 a 75 c 6-b 804-4 bfe-b 23 a -907113 b 8 bfa 6
translation-type: tm+mt
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

**Valores devueltos:**

Valor de la cookie o una cadena vacía si no se encuentra la cookie.

**Ejemplo:**

```js
var myCookie = s.Util.cookieRead("my_cookie");
```


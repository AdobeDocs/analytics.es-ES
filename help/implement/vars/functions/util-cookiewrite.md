---
title: Util.cookieWrite
description: Escribe un valor para una cookie.
exl-id: 079dbe50-5568-467b-a67c-f44481a4a20b
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: ht
source-wordcount: '131'
ht-degree: 100%

---

# Util.cookieWrite

Las cookies pueden almacenar y recuperar información entre páginas del mismo dominio. Utilice el método `Util.cookieWrite()` para establecer un valor en una cookie. Puede utilizar el método [`Util.cookieRead()`](util-cookieread.md) para recuperar los valores establecidos mediante `Util.cookieWrite()`.

## Configuración de cookies mediante etiquetas en Adobe Experience Platform

La IU de recopilación de datos no permite establecer cookies en la interfaz. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.Util.cookieWrite() en el editor de código personalizado de AppMeasurement y 

Llame al método `s.Util.cookieWrite()` para configurar una cookie como el valor deseado.

```js
s.Util.cookieWrite("example_cookie","Example cookie value")
```

Hay disponible un tercer argumento opcional que determina cuándo caduca la cookie. Las cookies configuradas con `s.Util.cookieWrite()` expiran al final de la sesión del explorador de forma predeterminada.

```js
// Set a cookie with an expiration 6 months from now
var cookieDate = new Date();
cookieDate.setMonth(cookieDate.getMonth() + 6);
s.Util.cookieWrite("example_cookie","Example 6-month cookie",cookieDate);
```

## Ejemplos

Puede crear una instancia de una variable una vez que se haya escrito correctamente una cookie. Esta variable es booleana.

```js
var success = s.Util.cookieWrite("example_cookie","Example cookie value");
if (success) {
  console.log("Cookie written successfully");
} else {
  console.log("Cookie write failed");
}
```

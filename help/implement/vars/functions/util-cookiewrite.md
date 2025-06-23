---
title: Util.cookieWrite
description: Escribe un valor para una cookie.
feature: Appmeasurement Implementation
exl-id: 079dbe50-5568-467b-a67c-f44481a4a20b
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 70%

---

# Util.cookieWrite

Las cookies pueden almacenar y recuperar información entre páginas del mismo dominio. Utilice el método `Util.cookieWrite()` para establecer un valor en una cookie. Puede utilizar el método [`Util.cookieRead()`](util-cookieread.md) para recuperar los valores establecidos mediante `Util.cookieWrite()`.

## Establecer cookies mediante la extensión de Adobe Analytics y la extensión de Web SDK

La recopilación de datos de Adobe Experience Platform no permite establecer cookies en la interfaz.

## s.Util.cookieWrite() en AppMeasurement y el editor de código personalizado de la extensión de Analytics

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

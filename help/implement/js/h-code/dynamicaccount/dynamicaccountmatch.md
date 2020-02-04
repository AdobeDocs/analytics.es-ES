---
title: dynamicAccountMatch
description: La variable dynamicAccountMatch determina el valor que se debe ver en las cuentas dinámicas.
translation-type: tm+mt
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# dynamicAccountMatch

> [!IMPORTANT] Las cuentas dinámicas solo se admiten mediante implementaciones de JavaScript heredadas (código H). Estas variables no son compatibles con las bibliotecas de AppMeasurement actuales ni con Adobe Experience Platform Launch.

La `dynamicAccountMatch` variable es el valor que `dynamicAccountList` observa y compara sus valores. Si no `dynamicAccountSelection` se establece en `true`, se omite esta variable.

Si esta variable no está definida, su valor predeterminado es `window.location.host`.

## Sintaxis

```js
s.dynamicAccountMatch=[DOM object]
```

## Ejemplos

```js
// Look at the URL path to determine report suite
s.dynamicAccountMatch = location.pathname;

// Use a query string
s.dynamicAccountMatch = location.search;

// Use the full URL
s.dynamicAccountMatch = location.href;

// Use concatenated variables
s.dynamicAccountMatch =  location.hostname + location.pathname + location.search;
```

## Notas adicionales

* Las páginas guardadas en una unidad de disco duro no tienen varias `location` variables definidas (por ejemplo, `location.host` está en blanco). Asegúrese de `s_account` que contiene un grupo de informes predeterminado.
* Cuando una página se traduce a través de un motor de traducción web, como Google, la selección de cuentas dinámicas no funciona según lo diseñado. Para un seguimiento más preciso, rellene el lado del servidor de la variable `s_account`.

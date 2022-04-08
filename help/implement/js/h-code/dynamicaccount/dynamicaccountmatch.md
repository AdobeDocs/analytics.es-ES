---
title: dynamicAccountMatch
description: La variable dynamicAccountMatch determina el valor que se debe ver en las cuentas dinámicas.
feature: Implementation Basics
exl-id: 3b68f2e6-1bd9-4b16-9d03-a87c9217e1b7
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: ht
source-wordcount: '127'
ht-degree: 100%

---

# dynamicAccountMatch

>[!IMPORTANT]
>
>Las cuentas dinámicas solo se admiten mediante implementaciones de JavaScript heredadas (código H). Estas variables no son compatibles con las bibliotecas de AppMeasurement actuales o con las etiquetas de Adobe Experience Platform.

La variable `dynamicAccountMatch` es el valor que `dynamicAccountList` analiza y compara sus valores. Si no se establece `dynamicAccountSelection` como `true`, se omite esta variable.

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

* Las páginas guardadas en una unidad de disco duro no tienen diferentes variables `location` definidas (por ejemplo, `location.host` está en blanco). Asegúrese de que `s_account` contiene un grupo de informes predeterminado.
* Cuando se traduce una página con un motor de traducción web, como Google, la selección de cuentas dinámicas no funciona como está previsto. Para un seguimiento más preciso, rellene el lado del servidor de la variable `s_account`.

---
title: dynamicAccountSelection
description: La variable dynamicAccountSelection habilita o deshabilita la selección dinámica de cuentas.
translation-type: tm+mt
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# dynamicAccountSelection

> [!IMPORTANT] Las cuentas dinámicas solo se admiten mediante implementaciones de JavaScript heredadas (código H). Estas variables no son compatibles con las bibliotecas de AppMeasurement actuales ni con Adobe Experience Platform Launch.

La `dynamicAccountSelection` variable es un booleano que determina si se utiliza la selección dinámica de cuentas.

Si se establece en `true`, el archivo JavaScript busca `dynamicAccountMatch` y `dynamicAccountList`.

Si se establece en `false`, o si no se define esta variable, se omiten las variables `dynamicAccountMatch` y `dynamicAccountList` .

Si no se define esta variable, el valor predeterminado es `false`.

## Sintaxis

```js
s.dynamicAccountSelection = [boolean];
```

## Ejemplo

```js
s.dynamicAccountSelection = true;
```

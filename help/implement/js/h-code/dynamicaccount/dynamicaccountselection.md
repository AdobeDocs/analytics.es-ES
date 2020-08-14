---
title: dynamicAccountSelection
description: La variable dynamicAccountSelection habilita o deshabilita la selección dinámica de cuentas.
translation-type: ht
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: ht
source-wordcount: '85'
ht-degree: 100%

---


# dynamicAccountSelection

>[!IMPORTANT]
>
>Las cuentas dinámicas solo se admiten mediante implementaciones de JavaScript heredadas (código H). Estas variables no son compatibles con las bibliotecas de AppMeasurement actuales ni con Adobe Experience Platform Launch.

La variable `dynamicAccountSelection` es un valor booleano que determina si se utiliza la selección dinámica de cuentas.

Si se establece como `true`, el archivo JavaScript busca `dynamicAccountMatch` y `dynamicAccountList`.

Si se establece como `false`, o si no se define esta variable, se omiten las variables `dynamicAccountMatch` y `dynamicAccountList`.

Si no se define esta variable, el valor predeterminado es `false`.

## Sintaxis

```js
s.dynamicAccountSelection = [boolean];
```

## Ejemplo

```js
s.dynamicAccountSelection = true;
```

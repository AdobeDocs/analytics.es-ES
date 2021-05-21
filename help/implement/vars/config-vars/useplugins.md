---
title: usePlugins
description: Habilite o deshabilite la función doPlugins().
exl-id: e8499acf-d8b9-490c-9f67-ad9a8f6ca7df
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '95'
ht-degree: 100%

---

# usePlugins

Si `usePlugins` está habilitada, la función [`doPlugins()`](../functions/doplugins.md) se ejecuta justo antes de que AppMeasurement compile y envíe una visita a Adobe. Active esta variable si utiliza la función `doPlugins()`.

## Uso de complementos en Adobe Experience Platform Launch

No hay un campo específico en Launch para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.usePlugins en el editor de código personalizado de AppMeasurement y Launch

La variable `s.usePlugins` es un booleano que determina si AppMeasurement llama a la función `doPlugins()`. Su valor predeterminado es `false`. Establezca esta variable como `true` si utiliza la función `doPlugins()` en la implementación.

```js
s.usePlugins = true;
```

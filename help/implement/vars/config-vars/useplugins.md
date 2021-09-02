---
title: usePlugins
description: Habilite o deshabilite la función doPlugins().
exl-id: e8499acf-d8b9-490c-9f67-ad9a8f6ca7df
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: ht
source-wordcount: '98'
ht-degree: 100%

---

# usePlugins

Si `usePlugins` está habilitada, la función [`doPlugins()`](../functions/doplugins.md) se ejecuta justo antes de que AppMeasurement compile y envíe una visita a Adobe. Active esta variable si utiliza la función `doPlugins()`.

## Uso de complementos con etiquetas en Adobe Experience Platform

No hay ningún campo específico en la IU de recopilación de datos para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.usePlugins en el editor de código personalizado de AppMeasurement y 

La variable `s.usePlugins` es un booleano que determina si AppMeasurement llama a la función `doPlugins()`. Su valor predeterminado es `false`. Establezca esta variable como `true` si utiliza la función `doPlugins()` en la implementación.

```js
s.usePlugins = true;
```

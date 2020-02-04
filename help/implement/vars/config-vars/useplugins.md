---
title: usePlugins
description: Habilite o deshabilite la función doPlugins().
translation-type: tm+mt
source-git-commit: a02fb674ea71a05e085c8e9b2dc4460f62f2cd51

---


# usePlugins

Si `usePlugins` está habilitada, la `doPlugins()` función se ejecuta justo antes de que AppMeasurement compila y envíe una visita a Adobe. Active esta variable si utiliza la `doPlugins()` función.

## Uso de complementos en Adobe Experience Platform Launch

No hay un campo dedicado en Launch para utilizar esta variable. Utilice el editor de código personalizado, siguiendo la sintaxis de AppMeasurement.

## s.usePlugins en el editor de código personalizado AppMeasurement e Launch

La `s.usePlugins` variable es un booleano que determina si AppMeasurement llama a la `doPlugins()` función. Its default value is `false`. Configure esta variable en `true` si utiliza la `doPlugins()` función en la implementación.

```js
s.usePlugins = true;
```

---
title: usePlugins
description: Habilite o deshabilite la función doPlugins().
feature: Variables
exl-id: e8499acf-d8b9-490c-9f67-ad9a8f6ca7df
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 43%

---

# usePlugins

Si `usePlugins` está habilitada, la función [`doPlugins()`](../functions/doplugins.md) se ejecuta justo antes de que AppMeasurement compile y envíe una visita a Adobe. Active esta variable si utiliza la función `doPlugins()`.

## Utilice la variable `onBeforeEventSend` llamada de retorno mediante el SDK web

Aunque el SDK web no tiene un booleano para gestionar la ejecución de lógica adicional antes de que se envíen los datos al Adobe, puede registrar la variable `onBeforeEventSend` llamada de retorno para modificar los datos. Consulte [Modificación global de eventos](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) en la documentación del SDK web para obtener más información.

## Uso de complementos con la extensión de Adobe Analytics

No hay un campo específico en la extensión de Adobe Analytics para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.usePlugins en AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `s.usePlugins` es un booleano que determina si AppMeasurement llama a la función `doPlugins()`. Su valor predeterminado es `false`. Establezca esta variable como `true` si utiliza la función `doPlugins()` en la implementación.

```js
s.usePlugins = true;
```

---
title: usePlugins
description: Habilite o deshabilite la función doPlugins().
feature: Variables
exl-id: e8499acf-d8b9-490c-9f67-ad9a8f6ca7df
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 34%

---

# usePlugins

Si `usePlugins` está habilitada, la función [`doPlugins()`](../functions/doplugins.md) se ejecuta justo antes de que AppMeasurement compile y envíe una visita a Adobe. Active esta variable si utiliza la función `doPlugins()`.

## Usar la llamada de retorno `onBeforeEventSend` mediante el SDK web

Aunque el SDK web no tiene un valor booleano para controlar la ejecución de lógica adicional antes de que los datos se envíen al Adobe, puede registrar la llamada de retorno `onBeforeEventSend` para modificar los datos. Consulte [Modificación de eventos globalmente](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=es#modifying-events-globally) en la documentación del SDK web para obtener más información.

## Uso de complementos con la extensión de Adobe Analytics

El Adobe de proporciona una extensión denominada &quot;Complementos comunes de Analytics&quot; que le permite llamar a la mayoría de [complementos](../plugins/impl-plugins.md). Instale la extensión de y llame al complemento que desee dentro de una regla.

Si el complemento deseado no se incluye en la extensión de Adobe, utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.usePlugins en el AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `s.usePlugins` es un booleano que determina si AppMeasurement llama a la función `doPlugins()`. Su valor predeterminado es `false`. Establezca esta variable como `true` si utiliza la función `doPlugins()` en la implementación.

```js
s.usePlugins = true;
```

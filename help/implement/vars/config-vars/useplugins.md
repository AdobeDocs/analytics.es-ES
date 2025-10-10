---
title: usePlugins
description: Habilite o deshabilite la función doPlugins().
feature: Appmeasurement Implementation
exl-id: e8499acf-d8b9-490c-9f67-ad9a8f6ca7df
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 34%

---

# usePlugins

Si `usePlugins` está habilitada, la función [`doPlugins()`](../functions/doplugins.md) se ejecuta justo antes de que AppMeasurement compile y envíe una visita a Adobe. Habilite esta variable si utiliza la función `doPlugins()`.

## Usar la llamada de retorno `onBeforeEventSend` mediante Web SDK

Aunque Web SDK no tiene un valor booleano para controlar la ejecución de lógica adicional antes de enviar los datos a Adobe, puede registrar la devolución de llamada `onBeforeEventSend` para modificar los datos. Consulte [Modificación de eventos globalmente](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) en la documentación de Web SDK para obtener más información.

## Uso de complementos con la extensión de Adobe Analytics

Adobe proporciona una extensión denominada &quot;Complementos comunes de Analytics&quot; que le permite llamar a la mayoría de [complementos](../plugins/impl-plugins.md). Instale la extensión de y llame al complemento que desee dentro de una regla.

Si el complemento deseado no se incluye en la extensión de Adobe, utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.usePlugins en AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `s.usePlugins` es un booleano que determina si AppMeasurement llama a la función `doPlugins()`. Su valor predeterminado es `false`. Establezca esta variable como `true` si utiliza la función `doPlugins()` en la implementación.

```js
s.usePlugins = true;
```

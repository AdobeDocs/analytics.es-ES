---
title: usePlugins
description: Habilite o deshabilite la función doPlugins().
feature: Appmeasurement Implementation
exl-id: e8499acf-d8b9-490c-9f67-ad9a8f6ca7df
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/7ofbF5EloAUlvCmGv-CaTFxxZELX0wydJ8HzmU2f6EQ'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 187
ht-degree: 32%

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

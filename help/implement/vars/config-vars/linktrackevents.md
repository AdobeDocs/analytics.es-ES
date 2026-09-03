---
title: linkTrackEvents
description: Determine qué eventos incluir en las solicitudes de imagen de seguimiento de vínculos.
feature: Appmeasurement Implementation
exl-id: 53c9e122-425c-4ec3-8a32-96e4d112f348
role: Admin, Developer
TQID: https://experienceleague.adobe.com/7BKaDxchTRu39doWzm8f32DOemgpvj1s-4uzfjJkOEA
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
  - id: df312454-73c4-43f6-a90e-18f5043f074c
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 325
ht-degree: 66%

---

# linkTrackEvents

Algunas implementaciones no desean incluir todas las variables en todas las solicitudes de imagen de seguimiento de vínculos. Utilice las variables [`linkTrackVars`](linktrackvars.md) y `linkTrackEvents` para incluir selectivamente dimensiones y métricas en las llamadas [`tl()`](../functions/tl-method.md).

Esta variable no se utiliza para las llamadas de vista de página (método [`t()`](../functions/t-method.md)).

## Determine qué eventos de Analytics incluir en un evento XDM mediante la SDK web

Web SDK no excluye determinados campos para las llamadas de seguimiento de vínculos. Sin embargo, puede usar la llamada de retorno `onBeforeEventSend` para borrar o establecer los campos deseados antes de que se envíen los datos a Adobe. Consulte [Modificación de eventos globalmente](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=es#modifying-events-globally) en la documentación de Web SDK para obtener más información.

## Eventos en llamadas de seguimiento de vínculos mediante la extensión de Adobe Analytics

Adobe Experience Platform incluye automáticamente eventos definidos en las visitas de seguimiento de vínculos si no utiliza código personalizado.

>[!IMPORTANT]
>
>Si establece eventos en el editor de código personalizado de la extensión de Analytics, también debe incluir el evento en `linkTrackEvents` mediante código personalizado.

## s.linkTrackEvents en AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `s.linkTrackEvents` es una cadena que contiene una lista delimitada por comas de los eventos que desea incluir en las solicitudes de imagen de seguimiento de vínculos (método `tl()`). Se deben cumplir los tres criterios siguientes para incluir métricas en las visitas de seguimiento de vínculos:

* Configure el evento deseado en la variable [`events`](../page-vars/events/events-overview.md). Por ejemplo: `s.events = "event1";`.
* Establezca la variable `events` en `linkTrackVars`. Por ejemplo: `s.linkTrackVars = "events";`.
* Configure el evento deseado en la variable `linkTrackEvents`. Por ejemplo: `s.linkTrackEvents = "event1";`.

```js
s.linkTrackEvents = "event1,event2,event3,purchase";
```

El valor predeterminado de esta variable es una cadena vacía. Si no se define esta variable, todos los eventos se incluyen en las solicitudes de imagen de seguimiento de vínculos. Tenga en cuenta que la recopilación de datos rellena automáticamente esta variable en función de los eventos establecidos en la interfaz, por lo que siempre se establece para implementaciones que utilizan etiquetas en Adobe Experience Platform.

>[!TIP]
>
>Evite utilizar el identificador de objeto (`s.`) de Analytics al especificar eventos en esta variable. Por ejemplo, `s.linkTrackEvents = "event1";` es correcto, mientras que `s.linkTrackEvents = "s.event1";` es incorrecto.

## Ejemplo

La siguiente función de seguimiento de vínculos solo incluye `event1` (no `event2`) en la solicitud de imagen enviada a Adobe:

```js
s.events = "event1,event2";
s.linkTrackVars = "events";
s.linkTrackEvents = "event1";
s.tl(this,"o","Example Custom Link");
```

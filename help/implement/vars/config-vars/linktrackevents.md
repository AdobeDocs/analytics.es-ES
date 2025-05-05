---
title: linkTrackEvents
description: Determine qué eventos incluir en las solicitudes de imagen de seguimiento de vínculos.
feature: Variables
exl-id: 53c9e122-425c-4ec3-8a32-96e4d112f348
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 68%

---

# linkTrackEvents

Algunas implementaciones no desean incluir todas las variables en todas las solicitudes de imagen de seguimiento de vínculos. Utilice las variables [`linkTrackVars`](linktrackvars.md) y `linkTrackEvents` para incluir selectivamente dimensiones y métricas en las llamadas [`tl()`](../functions/tl-method.md).

Esta variable no se utiliza para las llamadas de vista de página (método [`t()`](../functions/t-method.md)).

## Determine qué eventos de Analytics incluir en un evento XDM mediante el SDK web

El SDK web no excluye ciertos campos para las llamadas de seguimiento de vínculos. Sin embargo, puede usar la llamada de retorno `onBeforeEventSend` para borrar o establecer los campos deseados antes de que los datos se envíen al Adobe. Consulte [Modificación de eventos globalmente](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=es#modifying-events-globally) en la documentación del SDK web para obtener más información.

## Eventos en llamadas de seguimiento de vínculos mediante la extensión de Adobe Analytics

Adobe Experience Platform incluye automáticamente eventos definidos en las visitas de seguimiento de vínculos si no utiliza código personalizado.

>[!IMPORTANT]
>
>Si establece eventos en el editor de código personalizado de la extensión de Analytics, también debe incluir el evento en `linkTrackEvents` mediante código personalizado.

## s.linkTrackEvents en el AppMeasurement y el editor de código personalizado de la extensión de Analytics

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

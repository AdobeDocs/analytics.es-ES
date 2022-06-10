---
title: linkTrackEvents
description: Determine qué eventos incluir en las solicitudes de imagen de seguimiento de vínculos.
feature: Variables
exl-id: 53c9e122-425c-4ec3-8a32-96e4d112f348
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 67%

---

# linkTrackEvents

Algunas implementaciones no desean incluir todas las variables en todas las solicitudes de imagen de seguimiento de vínculos. Utilice las variables [`linkTrackVars`](linktrackvars.md) y `linkTrackEvents` para incluir selectivamente dimensiones y métricas en las llamadas [`tl()`](../functions/tl-method.md).

Esta variable no se utiliza para las llamadas de vista de página (método [`t()`](../functions/t-method.md)).

## Determinar qué eventos de Analytics incluir en un evento XDM mediante el SDK web

El SDK web no excluye determinados campos para las llamadas de seguimiento de vínculos. Sin embargo, puede usar la variable `onBeforeEventSend` llamada de retorno para borrar o establecer los campos deseados antes de que los datos se envíen a Adobe. Consulte [Modificación global de eventos](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) en la documentación del SDK web para obtener más información.

## Eventos en llamadas de seguimiento de vínculos con la extensión Adobe Analytics

Adobe Experience Platform incluye automáticamente eventos definidos en las visitas de seguimiento de vínculos si no utiliza código personalizado.

>[!IMPORTANT]
>
>Si establece eventos en el editor de código personalizado de la extensión de Analytics, debe incluir el evento en `linkTrackEvents` también se usa código personalizado.

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

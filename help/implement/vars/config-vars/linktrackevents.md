---
title: linkTrackEvents
description: Determine qué eventos incluir en las solicitudes de imagen de seguimiento de vínculos.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# linkTrackEvents

Algunas implementaciones no desean incluir todas las variables en todas las solicitudes de imagen de seguimiento de vínculos. Utilice las variables [`linkTrackVars`](linktrackvars.md) y `linkTrackEvents` para incluir selectivamente dimensiones y métricas en las llamadas [`tl()`](../functions/tl-method.md).

This variable is not used for page view calls ([`t()`](../functions/t-method.md) method).

## Eventos en llamadas de seguimiento de vínculos mediante Adobe Experience Platform Launch

Launch detecta automáticamente los eventos definidos en la interfaz y los incluye en las visitas de seguimiento de vínculos.

>[!IMPORTANT] Si establece eventos en Launch mediante el editor de código personalizado, también debe incluir el evento en `linkTrackEvents` mediante el uso del código personalizado.

## s.linkTrackEvents en el editor de código personalizado de AppMeasurement y Launch

The `s.linkTrackEvents` variable is a string containing a comma-delimited list of events that you want to include in link tracking image requests (`tl()` method). Se deben cumplir los tres criterios siguientes para incluir métricas en las visitas de seguimiento de vínculos:

* Configure el evento deseado en la variable [`events`](../page-vars/events/events-overview.md). Por ejemplo: `s.events = "event1";`.
* Establezca la variable `events` en `linkTrackVars`. Por ejemplo: `s.linkTrackVars = "events";`.
* Configure el evento deseado en la variable `linkTrackEvents`. Por ejemplo: `s.linkTrackEvents = "event1";`.

```js
s.linkTrackEvents = "event1,event2,event3,purchase";
```

El valor predeterminado de esta variable es una cadena vacía. Si no se define esta variable, todos los eventos se incluyen en las solicitudes de imagen de seguimiento de vínculos. Tenga en cuenta que Launch rellena automáticamente esta variable en función de los eventos establecidos en la interfaz, por lo que siempre se establece en implementaciones que utilizan Launch.

>[!TIP] Evite utilizar el identificador de objeto (`s.`) de Analytics al especificar eventos en esta variable. Por ejemplo, `s.linkTrackEvents = "event1";` es correcto, mientras que `s.linkTrackEvents = "s.event1";` es incorrecto.

## Ejemplo

La siguiente función de seguimiento de vínculos solo incluye `event1` (no `event2`) en la solicitud de imagen enviada a Adobe:

```js
s.events = "event1,event2";
s.linkTrackVars = "events";
s.linkTrackEvents = "event1";
s.tl(this,"o","Example Custom Link");
```

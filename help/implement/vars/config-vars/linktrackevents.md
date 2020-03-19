---
title: linkTrackEvents
description: Determine qué eventos incluir en las solicitudes de imagen de seguimiento de vínculos.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# linkTrackEvents

Algunas implementaciones no desean incluir todas las variables en todas las solicitudes de imagen de seguimiento de vínculos. Utilice las variables [`linkTrackVars`](linktrackvars.md) y `linkTrackEvents` para incluir de forma selectiva dimensiones y métricas en [`tl()`](../functions/tl-method.md) las llamadas.

Esta variable no se utiliza para las llamadas de vista de página ([`t()`](../functions/t-method.md) método).

## Eventos en llamadas de seguimiento de vínculos mediante Adobe Experience Platform Launch

Launch detecta automáticamente los eventos definidos en la interfaz y los incluye en las visitas de seguimiento de vínculos.

> [!IMPORTANT] Si establece eventos en Launch mediante el editor de código personalizado, debe incluir el evento en `linkTrackEvents` el uso del código personalizado.

## s.linkTrackEvents en AppMeasurement e inicie el editor de código personalizado

La `s.linkTrackEvents` variable es una cadena que contiene una lista delimitada por comas de los eventos que desea incluir en las solicitudes de imagen de seguimiento de vínculos (`tl()` método). Se deben cumplir los tres criterios siguientes para incluir métricas en las visitas de seguimiento de vínculos:

* Configure el evento deseado en la [`events`](../page-vars/events/events-overview.md) variable. Por ejemplo: `s.events = "event1";`.
* Set the `events` variable in `linkTrackVars`. Por ejemplo: `s.linkTrackVars = "events";`.
* Configure el evento deseado en la `linkTrackEvents` variable. Por ejemplo: `s.linkTrackEvents = "event1";`.

```js
s.linkTrackEvents = "event1,event2,event3,purchase";
```

El valor predeterminado de esta variable es una cadena vacía. Si no se define esta variable, todos los eventos se incluyen en las solicitudes de imagen de seguimiento de vínculos. Tenga en cuenta que Launch rellena automáticamente esta variable en función de los eventos establecidos en la interfaz, por lo que siempre se configura en implementaciones que utilizan Launch.

> [!TIP] Evite utilizar el identificador de objeto (`s.`) de Analytics al especificar eventos en esta variable. Por ejemplo, `s.linkTrackEvents = "event1";` es correcto, mientras que `s.linkTrackEvents = "s.event1";` es incorrecto.

## Ejemplo

La siguiente función de seguimiento de vínculos solo incluye `event1` (no `event2`) en la solicitud de imagen enviada a Adobe:

```js
s.events = "event1,event2";
s.linkTrackVars = "events";
s.linkTrackEvents = "event1";
s.tl(this,"o","Example Custom Link");
```

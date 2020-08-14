---
title: linkTrackEvents
description: Determine qué eventos incluir en las solicitudes de imagen de seguimiento de vínculos.
translation-type: ht
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: ht
source-wordcount: '246'
ht-degree: 100%

---


# linkTrackEvents

Algunas implementaciones no desean incluir todas las variables en todas las solicitudes de imagen de seguimiento de vínculos. Utilice las variables [`linkTrackVars`](linktrackvars.md) y `linkTrackEvents` para incluir selectivamente dimensiones y métricas en las llamadas [`tl()`](../functions/tl-method.md).

Esta variable no se utiliza para las llamadas de vista de página (método [`t()`](../functions/t-method.md)).

## Eventos en llamadas de seguimiento de vínculos mediante Adobe Experience Platform Launch

Launch detecta automáticamente los eventos definidos en la interfaz y los incluye en las visitas de seguimiento de vínculos.

>[!IMPORTANT]
>
>Si establece eventos en Launch mediante el editor de código personalizado, también debe incluir el evento en `linkTrackEvents` mediante el uso del código personalizado.

## s.linkTrackEvents en el editor de código personalizado de AppMeasurement y Launch

La variable `s.linkTrackEvents` es una cadena que contiene una lista delimitada por comas de los eventos que desea incluir en las solicitudes de imagen de seguimiento de vínculos (método `tl()`). Se deben cumplir los tres criterios siguientes para incluir métricas en las visitas de seguimiento de vínculos:

* Configure el evento deseado en la variable [`events`](../page-vars/events/events-overview.md). Por ejemplo: `s.events = "event1";`.
* Establezca la variable `events` en `linkTrackVars`. Por ejemplo: `s.linkTrackVars = "events";`.
* Configure el evento deseado en la variable `linkTrackEvents`. Por ejemplo: `s.linkTrackEvents = "event1";`.

```js
s.linkTrackEvents = "event1,event2,event3,purchase";
```

El valor predeterminado de esta variable es una cadena vacía. Si no se define esta variable, todos los eventos se incluyen en las solicitudes de imagen de seguimiento de vínculos. Tenga en cuenta que Launch rellena automáticamente esta variable en función de los eventos establecidos en la interfaz, por lo que siempre se establece en implementaciones que utilizan Launch.

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

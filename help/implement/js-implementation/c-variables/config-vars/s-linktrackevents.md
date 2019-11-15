---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Analytics Implementation
solution: null
title: Variables dinámicas
translation-type: tm+mt
source-git-commit: ca0797a353661a72d4064aa5aa84c3d9b7eb38a5

---


# s.linkTrackEvents

La variable es una lista de eventos separados por comas que se envían con un vínculo personalizado, de salida, o de descarga. The `linkTrackEvents` parameter should include each event you want to track with every file download, exit link, and custom link. Cuando se da uno de estos tipos de vínculo, el valor actual de cada variable se identifica como seguido. Esta variable solo se tiene en cuenta si [`linkTrackVars`](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html) contiene “events”.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | N.D. | Conversión | "Ninguna" |

If an event is not in `linkTrackEvents`, it is not sent to Analytics, even if it is populated in the `onClick` event of a link, as shown in the following example:

```js
s.linkTrackVars="events" 
s.events="event1,event2" 
s.t() // both event1 and event2 are recorded 
<a href="help.php" onClick="s=s_gi('rs1');s.tl(this,'o')">event1 is recorded</a> 
<a href="test.php" onClick="s=s_gi('rs1');s.events='event2';s.tl(this,'o')">No events are recorded</a> 
```

The values of [`linkTrackVars`](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html) and `linkTrackEvents` override the settings in the JS file and ensure only the variables and events specified in the custom link code are set for the specific link. La configuración de ambos afecta a cada descarga de archivo, vínculo de salida y vínculo personalizado. Las instancias de cada variable y evento se pueden aumentar en situaciones en las que la variable (o el evento) se aplique a la página actual pero no a la descarga de archivo, el vínculo de salida o el vínculo personalizado en particular.

Para asegurarse de que están definidas las variables correctas con el código de vínculo personalizado, Adobe recomienda configurar *`linkTrackVars`* and *`linkTrackEvents`* within the custom link code, as follows:

```js
<a href="index.html" onClick=" 
var s=s_gi('rsid'); 
s.linkTrackVars='prop1,prop2,eVar1,eVar2,events'; 
s.linkTrackEvents='event1'; 
s.prop1='Custom Property of Link'; 
s.events='event1'; 
s.tl(this,'o','Link Name'); 
">My Page 
```

In the above example, the value for `prop1` is set within the custom link code itself. The value of `prop2` comes from the current value of the variable as set on the page.

*Nota: Si`linkTrackVars`(o`linkTrackEvents`) es nulo (o una cadena vacía como ""), se realiza el seguimiento de todas las variables (o eventos) de Analytics definidas para la página actual. En otras palabras, todas las variables que tienen valores se enviarán con datos de vínculo. Es muy probable que esto aumente las instancias de cada variable. Para evitar una inflación de instancias o vistas de página asociadas con otras variables, Adobe recomienda rellenar`linkTrackVars`y`linkTrackEvents`en el evento`onClick`de un vínculo que se utiliza para el seguimiento de vínculos.*

Todas las variables se envíen con datos de vínculo (vínculos personalizados, de salida y de descarga) deben incluirse en `linkTrackVars`. Si `linkTrackEvents` se utiliza, `linkTrackVars` debe contener “events”.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | N.D. | Cualquiera | "Ninguna" |

When populating `linkTrackEvents`, do not use the 's.' prefix for variables. Por ejemplo, en lugar de rellenarlo con "s.event1", debe rellenarlo con "event1". El siguiente ejemplo ilustra cómo debe utilizarse.

```js
s.linkTrackVars="eVar1,events" 
s.linkTrackEvents="event1" 
s.events="event1" 
s.eVar1="value A" 
s.eVar2="value B" 
s.t() // eVar1, event1 and event2 are recorded 
<a href="https://google.com">event1 and eVar1 are recorded</a> 
<a href="test.php" onClick="s=s_gi('rs1');s.eVar1='value C';s.events='';s.tl(this,'o')">eVar1 is recorded</a> 
```

En el primer vínculo, observe que la variable events retiene el valor que se configuró antes de hacer clic en el vínculo. This allows `event1` to be sent with the custom link. In the second example, the link to `event2` is not recorded because it is not listed in `linkTrackEvents`.

Para evitar confusiones y posibles problemas, se recomienda rellenar [`linkTrackVars`](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html) y `linkTrackEvents` en el evento `onClick` de un vínculo que se utiliza para el seguimiento de vínculos.

## Sintaxis y valores posibles

La variable *`linkTrackEvents`* es una lista de eventos separados por comas (sin espacios).

```
s.linkTrackEvents="event1[,event2[,event3[...]]]"
```

Solo se permiten nombres de evento en `linkTrackEvents`. Estos eventos se incluyen en [Eventos](https://docs.adobe.com/content/help/en/analytics/implementation/analytics-basics/ref-events.html). Si aparece un espacio antes o después del nombre del evento, el evento no se puede enviar con ninguna solicitud de imagen de vínculo.

## Ejemplos

To track `prop1`, `eVar1`, and `event1` with every file download, exit link, and custom link, use the following settings within the global JS file:

```
s.linkTrackVars="prop1,eVar1,events"
```

```
s.linkTrackEvents="event1"
```

**Más ejemplos**

```
s.linkTrackEvents="purchase,event1"
```

```
s.linkTrackEvents="scAdd,scCheckout,purchase,event14"
```

## Parámetros de configuración

Ninguna

## Problemas, preguntas y consejos

* El archivo JavaScript solo utiliza `linkTrackEvents` si `linkTrackVars` contiene la variable “events”. “events” debe incluirse en `linkTrackVars` solo cuando `linkTrackEvents` se defina.

* Tenga cuidado si se activa un evento en una página y está incluido en `linkTrackEvents`. Ese evento se registra de nuevo con los vínculos de salida, descarga o personalizados a menos que la variable de eventos se restablezca antes de dicho evento (en el evento `onClick` de un vínculo o después de la llamada a la función `t()`).

* Si `linkTrackEvents` contiene espacios entre los nombres de evento, los eventos no se registran.

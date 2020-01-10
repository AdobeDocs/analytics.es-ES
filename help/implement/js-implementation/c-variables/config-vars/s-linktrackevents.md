---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Analytics Implementation
solution: null
title: Variables dinámicas
translation-type: ht
source-git-commit: ca0797a353661a72d4064aa5aa84c3d9b7eb38a5

---


# s.linkTrackEvents

La variable es una lista de eventos separados por comas que se envían con un vínculo personalizado, de salida, o de descarga. El parámetro `linkTrackEvents` debe incluir cada evento que se desea seguir con cada descarga de archivo, vínculo de salida y vínculo personalizado. Cuando se da uno de estos tipos de vínculo, el valor actual de cada variable se identifica como seguido. Esta variable solo se tiene en cuenta si [`linkTrackVars`](https://docs.adobe.com/content/help/es-ES/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html) contiene “events”.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N/A | N/A | Conversión | "Ninguna" |

Si el evento no aparece en `linkTrackEvents`, no se envía a Analytics, aunque esté relleno en el evento `onClick` de un vínculo, como se muestra en el ejemplo siguiente:

```js
s.linkTrackVars="events" 
s.events="event1,event2" 
s.t() // both event1 and event2 are recorded 
<a href="help.php" onClick="s=s_gi('rs1');s.tl(this,'o')">event1 is recorded</a> 
<a href="test.php" onClick="s=s_gi('rs1');s.events='event2';s.tl(this,'o')">No events are recorded</a> 
```

Los valores de [`linkTrackVars`](https://docs.adobe.com/content/help/es-ES/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html) y `linkTrackEvents` anulan la configuración del archivo JS y se aseguran de que solo están definidas las variables y los eventos especificados en el código de vínculo personalizado para el vínculo en particular. La configuración de ambos afecta a cada descarga de archivo, vínculo de salida y vínculo personalizado. Las instancias de cada variable y evento se pueden aumentar en situaciones en las que la variable (o el evento) se aplique a la página actual pero no a la descarga de archivo, el vínculo de salida o el vínculo personalizado en particular.

Para asegurarse de que están definidas las variables correctas con el código de vínculo personalizado, Adobe recomienda configurar *`linkTrackVars`* y *`linkTrackEvents`* dentro del código de vínculo personalizado, así:

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

En el ejemplo anterior, el valor de `prop1` se configura en el propio código de vínculo personalizado. El valor de `prop2` proviene del valor actual de la variable, según se ha definido en la página.

*Nota: Si`linkTrackVars`(o`linkTrackEvents`) tiene un valor nulo (o una cadena vacía como ""), se realiza el seguimiento de todas las variables (o eventos) de Analytics que están definidas para la página actual. En otras palabras, todas las variables que tienen valores se enviarán con los datos del vínculo. Es muy probable que esto aumente las instancias de cada variable. Para evitar una inflación de instancias o vistas de página asociadas con otras variables, Adobe recomienda rellenar`linkTrackVars`y`linkTrackEvents`en el evento`onClick`de un vínculo que se utiliza para el seguimiento de vínculos.*

Todas las variables se envíen con datos de vínculo (vínculos personalizados, de salida y de descarga) deben incluirse en `linkTrackVars`. Si `linkTrackEvents` se utiliza, `linkTrackVars` debe contener “events”.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N/A | N/A | Cualquiera | "Ninguna" |

Cuando rellene `linkTrackEvents`, no use el prefijo “s.” de las variables. Por ejemplo: en lugar de rellenar con “s.prop1”, debe rellenarlo con “event1”. El siguiente ejemplo ilustra cómo debe usarse.

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

En el primer vínculo, verá que la variable de eventos retiene el valor que se configuró antes de hacer clic en el vínculo. Esto permite enviar `event1` con el vínculo personalizado. En el segundo ejemplo, el vínculo a `event2` no se registra porque no está en la lista de `linkTrackEvents`.

Para evitar confusiones y posibles problemas, se recomienda rellenar [`linkTrackVars`](https://docs.adobe.com/content/help/es-ES/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html) y `linkTrackEvents` en el evento `onClick` de un vínculo que se utiliza para el seguimiento de vínculos.

## Sintaxis y valores posibles

La variable *`linkTrackEvents`* es una lista de eventos separados por comas (sin espacios).

```
s.linkTrackEvents="event1[,event2[,event3[...]]]"
```

Solo se permiten nombres de evento en `linkTrackEvents`. Estos eventos se incluyen en [Eventos](https://docs.adobe.com/content/help/es-ES/analytics/implementation/analytics-basics/ref-events.html). Si aparece un espacio antes o después del nombre de evento, el evento no se puede enviar con ninguna solicitud de imagen de vínculo.

## Ejemplos

Para realizar el seguimiento de `prop1`, `eVar1` y `event1` con cada uno de los vínculos de salida, vínculos personalizados y descarga de archivos, utilice la configuración siguiente en el archivo JS global:

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

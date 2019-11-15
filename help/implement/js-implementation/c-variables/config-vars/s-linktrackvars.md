---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Analytics Implementation
solution: null
title: Variables dinámicas
translation-type: tm+mt
source-git-commit: f1ebe5e89f62957c8bcc829be4b1a97463210f93

---


# s.linkTrackVars

La variable es una lista de variables separadas por coma que se envían con vínculos personalizados, de salida y de descarga.

The [`linkTrackVars`](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html) parameter should include each variable that you want to track with every file download, exit link, and custom link.

The settings for `linkTrackVars` and `linkTrackEvents` within the JS file affect every file download, exit link, and custom link. Las instancias de cada variable y evento se pueden aumentar en situaciones en las que la variable (o el evento) se aplique a la página actual pero no a la descarga de archivo, el vínculo de salida o el vínculo personalizado en particular.

Para asegurarse de que las variables correctas se establecen con el código de vínculo personalizado, Adobe recomienda configurar `linkTrackVars` y `linkTrackEvents` dentro del código de vínculo personalizado de la siguiente manera:

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

En el ejemplo anterior, el valor de prop1 se establece dentro del propio código de vínculo personalizado. El valor de prop2 proviene del valor actual de la variable, según se ha definido en la página.

The values of `linkTrackVars` and `linkTrackEvents` override the settings in the JS file and ensure only the variables and events specified in the custom link code are set for the specific link.

*Nota: Si`linkTrackVars`(o`linkTrackEvents`) es nulo (o una cadena vacía como ""), se realiza el seguimiento de todas las variables (o eventos) de Analytics definidas para la página actual. En otras palabras, todas las variables que tienen valores se enviarán con datos de vínculo. Es muy probable que esto aumente las instancias de cada variable. Para evitar una inflación de instancias o vistas de página asociadas con otras variables, Adobe recomienda rellenar`linkTrackVars`y`linkTrackEvents`en el evento[!UICONTROL onClick]de un vínculo que se utiliza para el seguimiento de vínculos.*

Todas las variables se envíen con datos de vínculo (vínculos personalizados, de salida y de descarga) deben incluirse en `linkTrackVars`. Si `linkTrackEvents` se utiliza, `linkTrackVars` debe contener “events”.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | N.D. | Cualquiera | "Ninguna" |

When populating `linkTrackVars`, do not use the 's.' prefix for variables. Por ejemplo: en lugar de rellenar `linkTrackVars` con “s.prop1”, debe rellenarlo con “prop1”. El siguiente ejemplo ilustra cómo debe usarse `linkTrackVars`.

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

Puesto que el vínculo a google.com es un vínculo de salida (a menos que usted sea Google), event1 y eVar1 se envían con los datos del vínculo de salida, lo que aumenta las instancias asociadas a eVar1 y el número de veces que se activa event1. En el vínculo a [!DNL test.php][!UICONTROL , se envía eVar1] con un valor de “value C” porque ese es el valor actual de eVar1 en el momento de la llamada a `tl()`.

## Sintaxis y valores posibles

La variable `linkTrackVars` es una lista de nombres de variable separados por coma, que distingue entre mayúsculas y minúsculas y sin prefijo de nombre de objeto. Use 'eVar1' en lugar de 's.eVar1'.

```
s.linkTrackVars="variable_name[,variable_name[...]]"
```

La variable `linkTrackVars` variable may contain only variables that are sent to [!DNL Analytics], namely: `events`, `campaign`, `purchaseID`, `products`, `eVar1-75`, `prop1-75`, `hier1-5`, `channel`, `server`, `state`, `zip`, and `pageType`.

## Ejemplos

```
s.linkTrackVars="events,prop1,eVar49"
```

```
s.linkTrackVars="products"
```

## Parámetros de configuración

Ninguna

## Problemas, preguntas y consejos

* Si `linkTrackVars` está en blanco, se realiza el seguimiento de todas las variables que tienen valores con todas las llamadas al servidor.
* Cualquier variable de `linkTrackVars` que tenga un valor en el momento del vínculo de descarga, salida o personalizado se siguen.
* Si `linkTrackEvents` se utiliza, `linkTrackVars` debe contener “events”.

* No use el prefijo "s." ni "s_objectname." para las variables.

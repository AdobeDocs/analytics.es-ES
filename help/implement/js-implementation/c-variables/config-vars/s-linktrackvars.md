---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Implementación de Analytics
seo-description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
solution: null
title: Variables dinámicas
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# s.linkTrackVars

La variable es una lista de variables separadas por coma que se envían con vínculos personalizados, de salida y de descarga.

Si *`linkTrackVars`* se configura como “”, todas las variables que tienen valores se envían con los datos del vínculo. Para evitar una inflación de instancias o vistas de página asociadas con otras variables, Adobe recomienda rellenar *`linkTrackVars`* y *`linkTrackEvents`* en el evento [!UICONTROL onClick] de un vínculo que se utiliza para el seguimiento de vínculos.

Todas las variables se envíen con datos de vínculo (vínculos personalizados, de salida y de descarga) deben incluirse en *`linkTrackVars`*. Si *`linkTrackEvents`* se utiliza, *`linkTrackVars`* debe contener “events”.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | N.D. | Cualquiera | "Ninguna" |

When populating *`linkTrackVars`*, do not use the 's.' prefix for variables. Por ejemplo: en lugar de rellenar *`linkTrackVars`* con “s.prop1”, debe rellenarlo con “prop1”. El siguiente ejemplo ilustra cómo debe usarse *`linkTrackVars`*.

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

Puesto que el vínculo a google.com es un vínculo de salida (a menos que usted sea Google), event1 y eVar1 se envían con los datos del vínculo de salida, lo que aumenta las instancias asociadas a eVar1 y el número de veces que se activa event1. En el vínculo a [!DNL test.php][!UICONTROL , se envía eVar1] con un valor de “value C” porque ese es el valor actual de [!UICONTROL eVar1] en el momento de la llamada a *`tl()`*.

## Sintaxis y valores posibles

La variable *`linkTrackVars`* es una lista de nombres de variable separados por coma, que distingue entre mayúsculas y minúsculas y sin prefijo de nombre de objeto. Use 'eVar1' en lugar de 's.eVar1'.

```js
s.linkTrackVars="variable_name[,variable_name[...]]"
```

La variable *`linkTrackVars`* contiene solo las variables enviadas a [!DNL Analytics], es decir: *`events`*, *`campaign`*, *`purchaseID`*, *`products`*, [!UICONTROL eVar1-75], [!UICONTROL prop1-75], [!UICONTROL hier1-5], *`channel`*, *`server`*, *`state`*, *`zip`* y *`pageType`*.

## Ejemplos

```js
s.linkTrackVars="events,prop1,eVar49"
```

```js
s.linkTrackVars="products"
```

## Parámetros de configuración

Ninguna

## Problemas, preguntas y consejos

* Si *`linkTrackVars`* está en blanco, se realiza el seguimiento de todas las variables que tienen valores con todas las llamadas al servidor.
* Cualquier variable de *`linkTrackVars`* que tenga un valor en el momento del vínculo de descarga, salida o personalizado se siguen.
* Si *`linkTrackEvents`* se utiliza, *`linkTrackVars`* debe contener “events”.

* No use el prefijo "s." ni "s_objectname." para las variables.

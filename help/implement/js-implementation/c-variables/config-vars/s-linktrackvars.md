---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Implementación de análisis
seo-description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
solution: null
title: Variables dinámicas
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# s.linkTrackVars

La variable es una lista de variables separadas por coma que se envían con vínculos personalizados, de salida y de descarga.

If *`linkTrackVars`* is set to "", all variables that have values are sent with link data. To avoid inflation of instances or page views associated with other variables, Adobe recommends populating  and  in the onClick event of a link that is used for link tracking.*`linkTrackVars`**`linkTrackEvents`*

All variables that should be sent with link data (custom, exit, and download links) should be listed in *`linkTrackVars`*. If  is used,  should contain "events."*`linkTrackEvents`**`linkTrackVars`*

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | N.D. | Cualquiera | "None" |

Al rellenar *`linkTrackVars`*, do not use the 's.' prefix for variables. Por ejemplo: en lugar de rellenar *`linkTrackVars`* "s.prop1", debe rellenarlo con "prop1". The following example illustrates how  should be used.*`linkTrackVars`*

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

Puesto que el vínculo a google.com es un vínculo de salida (a menos que usted sea Google), event1 y eVar1 se envían con los datos del vínculo de salida, lo que aumenta las instancias asociadas a eVar1 y el número de veces que se activa event1. In the link to [!DNL test.php], [!UICONTROL eVar1] is sent with a value of 'value C' because that is the current value of [!UICONTROL eVar1] at the time that *`tl()`* is called.

## Sintaxis y valores posibles

La sintaxis de la variable *`linkTrackVars`* es una lista de nombres de variable separados por coma, que distingue entre mayúsculas y minúsculas y sin prefijo de nombre de objeto. Use 'eVar1' en lugar de 's.eVar1'.

```js
s.linkTrackVars="variable_name[,variable_name[...]]"
```

La variable *`linkTrackVars`* puede contener solamente variables que se envían a [!DNL Analytics], a saber: *`events`*, *`campaign`*, *`purchaseID`*, *`products`*, [!UICONTROL eVar1-75], [!UICONTROL prop1-75], [!UICONTROL hier1-5]*`channel`**`server`**`state`**`zip`**`pageType`*,,,, y.

## Ejemplos

```js
s.linkTrackVars="events,prop1,eVar49"
```

```js
s.linkTrackVars="products"
```

## Parámetros de configuración

Ninguno.

## Problemas, preguntas y consejos

* If *`linkTrackVars`* is blank, all variables that have values are tracked with all server calls.
* Any variable listed in *`linkTrackVars`* that has a value at the time of any download, exit, or custom link, are tracked.
* Si *`linkTrackEvents`* se utiliza, *`linkTrackVars`* debe contener "events".

* No use el prefijo "s." ni "s_objectname." para las variables.
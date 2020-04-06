---
title: linkTrackVars
description: Especifique qué variables se incluirán en las solicitudes de imagen de seguimiento de vínculos.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# linkTrackVars

Algunas implementaciones no desean incluir todas las variables en todas las solicitudes de imagen de seguimiento de vínculos. Utilice las variables `linkTrackVars` y [`linkTrackEvents`](linktrackevents.md) para incluir selectivamente dimensiones y métricas en las llamadas [`tl()`](../functions/tl-method.md).

This variable is not used for page view calls (`t()` method).

## Variables en llamadas de seguimiento de vínculos que utilizan Adobe Experience Platform Launch

Launch rellena automáticamente esta variable en el servidor en función de las variables establecidas en la interfaz, por lo que siempre se establece en implementaciones que utilizan Launch.

>[!IMPORTANT] Si establece variables en Launch mediante el editor de código personalizado, debe incluir la variable en `linkTrackVars` mediante el uso del código personalizado.

## s.linkTrackVars en el editor de código personalizado de AppMeasurement y Launch

The `s.linkTrackVars` variable is a string containing a comma-delimited list of variables that you want to include in link tracking image requests (`tl()` method). Se deben cumplir los dos criterios siguientes para incluir dimensiones en las visitas de seguimiento de vínculos:

* Establezca el valor de variable deseado. Por ejemplo: `s.eVar1 = "Example value";`.
* Configure la variable deseada en la variable `linkTrackVars`. Por ejemplo: `s.linkTrackEvents = "eVar1";`.

```js
s.linkTrackVars = "eVar1,eVar2,events,channel,products";
```

El valor predeterminado de esta variable es una cadena vacía. Sin embargo, Adobe proporcionó código de AppMeasurement en el Administrador de códigos donde esta variable está configurada en `"None"`. Los valores válidos son cualquier variable de nivel de página que rellena una dimensión.

* Si esta variable no está definida o configurada como una cadena vacía, *todas* las variables se incluyen en las solicitudes de imagen de seguimiento de vínculos.
* Si esta variable está configurada como `"None"`, *no se incluyen variables* en las solicitudes de imagen de seguimiento de vínculos.

>[!TIP] Evite utilizar el identificador de objetos (`s.`) de Analytics al especificar variables en esta variable. Por ejemplo, `s.linkTrackVars = "eVar1";` es correcto, mientras que `s.linkTrackVars = "s.eVar1";` es incorrecto.

## Ejemplo

La siguiente función de seguimiento de vínculos solo incluye `eVar1` (no `eVar2`) en la solicitud de imagen enviada a Adobe:

```js
s.eVar1 = "Example value 1";
s.eVar2 = "Example value 2";
s.linkTrackVars = "eVar1";
s.tl(this,"o","Example Custom Link");
```

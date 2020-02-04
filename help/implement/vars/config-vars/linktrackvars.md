---
title: linkTrackVars
description: Especifique qué variables se incluirán en las solicitudes de imagen de seguimiento de vínculos.
translation-type: tm+mt
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# linkTrackVars

Algunas implementaciones no desean incluir todas las variables en todas las solicitudes de imagen de seguimiento de vínculos. Utilice las variables `linkTrackVars` y `linkTrackEvents` para incluir de forma selectiva dimensiones y métricas en `tl()` las llamadas.

Esta variable no se utiliza para las llamadas de vista de página (`t()` función).

## Variables en llamadas de seguimiento de vínculos que utilizan Adobe Experience Platform Launch

Launch rellena automáticamente esta variable en el servidor en función de las variables establecidas en la interfaz, por lo que siempre se establece en implementaciones que utilizan Launch.

> [!IMPORTANT] Si establece variables en Launch mediante el editor de código personalizado, debe incluir la variable en `linkTrackVars` el uso del código personalizado.

## s.linkTrackVars en AppMeasurement e inicie el editor de código personalizado

La `s.linkTrackVars` variable es una cadena que contiene una lista delimitada por comas de variables que desea incluir en las solicitudes de imagen de seguimiento de vínculos (`tl()` función). Se deben cumplir los dos criterios siguientes para incluir dimensiones en las visitas de seguimiento de vínculos:

* Establezca el valor de variable deseado. Por ejemplo: `s.eVar1 = "Example value";`.
* Configure la variable deseada en la `linkTrackVars` variable. Por ejemplo: `s.linkTrackEvents = "eVar1";`.

```js
s.linkTrackVars = "eVar1,eVar2,events,channel,products";
```

El valor predeterminado de esta variable es una cadena vacía. Sin embargo, Adobe proporcionó código de AppMeasurement en el Administrador de códigos donde esta variable está configurada en `"None"`. Los valores válidos son cualquier variable de nivel de página que rellena una dimensión.

* Si esta variable no está definida o está configurada en una cadena vacía, *todas* las variables se incluyen en las solicitudes de imagen de seguimiento de vínculos.
* Si esta variable está configurada en `"None"`, *no se incluyen* variables en las solicitudes de imagen de seguimiento de vínculos.

> [!TIP] Evite utilizar el identificador de objeto (`s.`) de Analytics al especificar variables en esta variable. Por ejemplo, `s.linkTrackVars = "eVar1";` es correcto, mientras que `s.linkTrackVars = "s.eVar1";` es incorrecto.

## Ejemplo

La siguiente función de seguimiento de vínculos solo incluye `eVar1` (no `eVar2`) en la solicitud de imagen enviada a Adobe:

```js
s.eVar1 = "Example value 1";
s.eVar2 = "Example value 2";
s.linkTrackVars = "eVar1";
s.tl(this,"o","Example Custom Link");
```

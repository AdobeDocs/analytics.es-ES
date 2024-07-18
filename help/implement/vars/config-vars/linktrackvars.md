---
title: linkTrackVars
description: Especifique qué variables se incluirán en las solicitudes de imagen de seguimiento de vínculos.
feature: Variables
exl-id: b884f6e9-45d9-49f0-ac74-ea6f4f01020a
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 62%

---

# linkTrackVars

Algunas implementaciones no desean incluir todas las variables en todas las solicitudes de imagen de seguimiento de vínculos. Utilice las variables `linkTrackVars` y [`linkTrackEvents`](linktrackevents.md) para incluir selectivamente dimensiones y métricas en las llamadas [`tl()`](../functions/tl-method.md).

Esta variable no se utiliza para las llamadas de vista de página (método [`t()`](../functions/t-method.md)).

## Determine qué variables se incluirán en un evento XDM mediante el SDK web

El SDK web no excluye ciertos campos para las llamadas de seguimiento de vínculos. Sin embargo, puede usar la llamada de retorno `onBeforeEventSend` para borrar o establecer los campos deseados antes de que los datos se envíen al Adobe. Consulte [Modificación de eventos globalmente](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) en la documentación del SDK web para obtener más información.

## Variables en llamadas de seguimiento de vínculos que utilizan la extensión de Adobe Analytics

Esta variable se rellena automáticamente en el servidor en función de las variables establecidas en la interfaz, por lo que siempre se establece en implementaciones que utilizan la extensión de Adobe Analytics.

>[!IMPORTANT]
>
>Si establece variables mediante el editor de código personalizado, debe incluir las variables de `linkTrackVars` mediante el uso del código personalizado.

## s.linkTrackVars en el AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `s.linkTrackVars` es una cadena que contiene una lista delimitada por comas de variables que desea incluir en las solicitudes de imagen de seguimiento de vínculos (método `tl()`). Se deben cumplir los dos criterios siguientes para incluir dimensiones en las visitas de seguimiento de vínculos:

* Establezca el valor de variable deseado. Por ejemplo: `s.eVar1 = "Example value";`.
* Configure la variable deseada en la variable `linkTrackVars`. Por ejemplo: `s.linkTrackVars = "eVar1";`.

```js
s.linkTrackVars = "eVar1,eVar2,events,channel,products";
```

El valor predeterminado de esta variable es una cadena vacía. Sin embargo, Adobe proporcionó código de AppMeasurement en el Administrador de códigos donde esta variable está configurada en `"None"`. Los valores válidos son cualquier variable de nivel de página que rellena una dimensión.

* Si esta variable no está definida o configurada como una cadena vacía, *todas* las variables se incluyen en las solicitudes de imagen de seguimiento de vínculos.
* Si esta variable está configurada como `"None"`, *no se incluyen variables* en las solicitudes de imagen de seguimiento de vínculos.

>[!TIP]
>
>Evite utilizar el identificador de objetos (`s.`) de Analytics al especificar variables en esta variable. Por ejemplo, `s.linkTrackVars = "eVar1";` es correcto, mientras que `s.linkTrackVars = "s.eVar1";` es incorrecto.

## Ejemplo

La siguiente función de seguimiento de vínculos solo incluye `eVar1` (no `eVar2`) en la solicitud de imagen enviada a Adobe:

```js
s.eVar1 = "Example value 1";
s.eVar2 = "Example value 2";
s.linkTrackVars = "eVar1";
s.tl(this,"o","Example Custom Link");
```

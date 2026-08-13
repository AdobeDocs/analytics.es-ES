---
title: linkTrackVars
description: Especifique qué variables se incluirán en las solicitudes de imagen de seguimiento de vínculos.
feature: Appmeasurement Implementation
exl-id: b884f6e9-45d9-49f0-ac74-ea6f4f01020a
role: Admin, Developer
TQID: https://experienceleague.adobe.com/B3So-VtGCz2klaFJT2a1zA3-AzSPaM9R-0jafXNsrVE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 344
ht-degree: 60%

---

# linkTrackVars

Algunas implementaciones no desean incluir todas las variables en todas las solicitudes de imagen de seguimiento de vínculos. Utilice las variables `linkTrackVars` y [`linkTrackEvents`](linktrackevents.md) para incluir selectivamente dimensiones y métricas en las llamadas [`tl()`](../functions/tl-method.md).

Esta variable no se utiliza para las llamadas de vista de página (método [`t()`](../functions/t-method.md)).

## Determine qué variables se incluirán en un evento XDM mediante la SDK web

Web SDK no excluye determinados campos para las llamadas de seguimiento de vínculos. Sin embargo, puede usar la llamada de retorno `onBeforeEventSend` para borrar o establecer los campos deseados antes de que se envíen los datos a Adobe. Consulte [Modificación de eventos globalmente](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=es#modifying-events-globally) en la documentación de Web SDK para obtener más información.

## Variables en llamadas de seguimiento de vínculos que utilizan la extensión de Adobe Analytics

Esta variable se rellena automáticamente en el servidor en función de las variables establecidas en la interfaz, por lo que siempre se establece en implementaciones que utilizan la extensión de Adobe Analytics.

>[!IMPORTANT]
>
>Si establece variables mediante el editor de código personalizado, debe incluir las variables de `linkTrackVars` mediante el uso del código personalizado.

## s.linkTrackVars en AppMeasurement y el editor de código personalizado de la extensión de Analytics

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

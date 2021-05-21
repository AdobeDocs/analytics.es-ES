---
title: abort
description: La variable abort es un booleano que evita que se envíe una visita a los servidores de recopilación de datos de Adobe.
exl-id: e4e25a89-272b-4444-b52b-c7fe2478ff30
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '183'
ht-degree: 100%

---

# abort

La variable `abort` es un booleano que puede evitar que la siguiente llamada de seguimiento se envíe a Adobe.

## Uso de la variable abort en Adobe Experience Platform Launch

No hay un campo específico en Launch para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## Sintaxis de AppMeasurement y editor de código personalizado en Launch

La variable `abort` es booleana. Su valor predeterminado es `false`.

* Si se establece como `true`, la siguiente llamada de seguimiento ([`t()`](../functions/t-method.md) o [`tl()`](../functions/tl-method.md)) no envía ningún dato a Adobe.
* Si se establece el valor como `false` o no se establece ninguno, esta variable no hace nada.

```js
s.abort = true;
```

>[!NOTE]
>
>La variable `abort` se restablece como `false` después de cada llamada de seguimiento. Si necesita cancelar llamadas de seguimiento subsiguientes en la misma página, establezca `abort` nuevamente como `true`.

## Ejemplo

La variable `abort` se puede establecer en la función [`doPlugins()`](../functions/doplugins.md), que es la última función que se ejecuta antes de que se envíe una solicitud de imagen a Adobe.

```js
s.doPlugins = function(s) {
     s.campaign = s.Util.getQueryParam("cid");
     if ((!s.campaign) && (!s.events)) {
          s.abort = true;
     }
};
```

Puede centralizar la lógica utilizada para identificar la actividad que no se quiere seguir, como algunos vínculos personalizados o vínculos externos para mostrar anuncios.

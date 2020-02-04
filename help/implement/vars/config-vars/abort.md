---
title: abort
description: La variable abort es un booleano que evita que se envíe una visita a los servidores de recopilación de datos de Adobe.
translation-type: tm+mt
source-git-commit: f769da139d9890fd736a9b277934b11aa131e166

---


# abort

La `abort` variable es un booleano que puede evitar que la siguiente llamada de seguimiento se envíe a Adobe.

## Uso de la variable abort en Adobe Experience Platform Launch

No hay un campo dedicado en Launch para utilizar esta variable. Utilice el editor de código personalizado, siguiendo la sintaxis de AppMeasurement.

## Sintaxis de AppMeasurement y editor de código personalizado en Launch

La `abort` variable es booleana. Its default value is `false`.

* Si se establece en `true`, la siguiente llamada de seguimiento (`t()` o `tl()`) no envía ningún dato a Adobe.
* Si se define como `false` o no, esta variable no hace nada.

```js
s.abort = true;
```

> [!NOTE] La `abort` variable se restablece `false` después de cada llamada de seguimiento. Si necesita cancelar llamadas de seguimiento subsiguientes en la misma página, establezca `abort` nuevamente en `true` .

## Ejemplo

La `abort` variable se puede establecer en la `doPlugins()` función, que es la última función que se ejecuta antes de que se envíe una solicitud de imagen a Adobe.

```js
s.doPlugins = function(s) {
     s.campaign = s.Util.getQueryParam("cid");
     if ((!s.campaign) && (!s.events)) {
          s.abort = true;
     }
};
```

Puede centralizar la lógica que utiliza para identificar la actividad que no desea rastrear, como algunos vínculos personalizados o vínculos externos en los anuncios en pantalla.

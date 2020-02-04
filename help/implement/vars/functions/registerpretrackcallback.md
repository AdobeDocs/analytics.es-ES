---
title: registerPreTrackCallback
description: Cree funciones de llamada de retorno antes de enviar una visita a Adobe.
translation-type: tm+mt
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# registerPreTrackCallback

La `registerPreTrackCallback` variable permite a la organización conectar una función de JavaScript después de compilar una dirección URL de solicitud de imagen pero antes de enviarla. Puede utilizar esta variable para enviar datos recopilados por AppMeasurement a un socio o a una infraestructura interna.

> [!IMPORTANT] No llame a ninguna función de seguimiento como `t` o `tl` dentro de la `registerPostTrackCallback` variable. Las funciones de seguimiento en esta variable provocan un bucle infinito de solicitudes de imagen.

Cada vez que llama a la `registerPreTrackCallback` variable, vincula esa función para que se ejecute cada vez que se compile una URL de solicitud de imagen. Evite registrar la misma función varias veces en la misma carga de página.

> [!NOTE] No se garantiza el tiempo y el orden de las funciones activadas entre `registerPreTrackCallback` y `registerPostTrackCallback` . Evite las dependencias entre estas dos funciones.

## Registrar llamada de retorno previa al seguimiento en Adobe Experience Platform Launch

No hay un campo dedicado en Launch para utilizar esta variable. Utilice el editor de código personalizado, siguiendo la sintaxis de AppMeasurement.

## s.registerPreTrackCallback en el editor de código personalizado AppMeasurement e Launch

La `s.registerPreTrackCallback` es una función que toma una función como su único argumento. La función anidada se ejecuta justo antes de que se envíe una solicitud de imagen.

```js
s.registerPreTrackCallback(function(){/* Desired code */});
```

Si desea utilizar la URL de solicitud de imagen en el código, haga referencia al argumento de la `requestUrl` cadena dentro de la función anidada. Puede analizar la `requestUrl` variable para el uso deseado; el ajuste de esta variable no afecta a la recopilación de datos.

```js
s.registerPreTrackCallback(function(requestUrl){
  console.log(requestUrl); // Outputs the full image request URL
});
```

Se pueden incluir argumentos adicionales en la `s.registerPreTrackCallback` función, que se puede utilizar en la función anidada:

```js
s.registerPreTrackCallback(function(requestUrl,a,b,c) {
    console.log(requestUrl); // Full image request URL
    console.log(a); // param1
    console.log(b); // param2
    console.log(c); // param3
}, "param1", "param2", "param3");
```

> [!NOTE] La configuración de variables de página o la modificación de la `requestUrl` cadena dentro de esta función *no afectan* a la solicitud de imagen enviada poco después de esta llamada de función.

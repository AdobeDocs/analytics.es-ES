---
title: registerPostTrackCallback
description: Cree funciones de llamada de retorno después de enviar una visita a Adobe.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# registerPostTrackCallback

La `registerPostTrackCallback` variable permite a su organización conectar una función de JavaScript inmediatamente después de que una visita se envíe correctamente a Adobe. Si falla una llamada de seguimiento, esta función no se ejecuta. Puede utilizar esta variable para enviar los datos recopilados por AppMeasurement a un socio o a una infraestructura interna, o para limpiar los valores de las variables en aplicaciones de una sola página.

> [!IMPORTANT] No llame a ninguna llamada de seguimiento como [`t()`](t-method.md) o [`tl()`](tl-method.md) dentro de la `registerPostTrackCallback` variable. Las funciones de seguimiento en esta variable provocan un bucle infinito de solicitudes de imagen.

Cada vez que llama a la `registerPostTrackCallback` variable, vincula esa función para que se ejecute inmediatamente después de que se envíe correctamente una solicitud de imagen. Evite registrar la misma función varias veces en la misma carga de página.

> [!NOTE] No se garantiza el tiempo y el orden de las funciones activadas entre [`registerPreTrackCallback`](registerpretrackcallback.md) y `registerPostTrackCallback` . Evite las dependencias entre estas dos funciones.

## Registrar llamada de retorno de seguimiento de anuncio en Adobe Experience Platform Launch

No hay un campo dedicado en Launch para utilizar esta variable. Utilice el editor de código personalizado, siguiendo la sintaxis de AppMeasurement.

## s.registerPostTrackCallback en el editor de código personalizado AppMeasurement e Launch

La `s.registerPostTrackCallback` es una función que toma una función como su único argumento. La función anidada se ejecuta justo antes de que se envíe una solicitud de imagen.

```js
s.registerPostTrackCallback(function(){/* Desired code */});
```

Si desea utilizar la URL de solicitud de imagen en el código, haga referencia al argumento de la `requestUrl` cadena dentro de la función anidada. Puede analizar la `requestUrl` variable para el uso deseado; el ajuste de esta variable no afecta a la recopilación de datos.

```js
s.registerPostTrackCallback(function(requestUrl){
  console.log(requestUrl); // Outputs the full image request URL
});
```

Se pueden incluir argumentos adicionales en la `s.registerPostTrackCallback` función, que se puede utilizar en la función anidada:

```js
s.registerPostTrackCallback(function(requestUrl,a,b,c) {
    console.log(requestUrl); // Full image request URL
    console.log(a); // param1
    console.log(b); // param2
    console.log(c); // param3
}, "param1", "param2", "param3");
```

## Ejemplo de caso de uso

El registro de la [`clearVars()`](clearvars.md) función en la llamada de retorno de seguimiento de anuncio puede ser beneficioso para aplicaciones de una sola página. Cada vez que envía una visita a Adobe, se ejecuta la `clearVars()` función. La implementación puede luego definir las variables de nuevo sin preocuparse por los valores que persisten incorrectamente.

```js
s.registerPostTrackCallback(function(){s.clearVars();});
```

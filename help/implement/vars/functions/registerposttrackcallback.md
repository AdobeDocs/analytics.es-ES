---
title: registerPostTrackCallback
description: Cree funciones de llamada de retorno después de enviar una visita a Adobe.
feature: Appmeasurement Implementation
exl-id: b2124b89-2bab-4cca-878c-18d62377a8f3
role: Admin, Developer
TQID: https://experienceleague.adobe.com/gBtDAy-MkoRGQNdG2L2zNp7jX8OjpZGAMnyRstgX6z0
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 367
ht-degree: 70%

---

# registerPostTrackCallback

La variable `registerPostTrackCallback` permite a su organización conectar una función de JavaScript inmediatamente después de que una visita se envíe correctamente a Adobe. Si falla una llamada de seguimiento, esta función no se ejecuta. Puede utilizar esta variable para enviar los datos recopilados por AppMeasurement a un socio o a una infraestructura interna, o para limpiar los valores de las variables en aplicaciones de una sola página.

>[!WARNING]
>
>No realice llamadas de seguimiento como [`t()`](t-method.md) o [`tl()`](tl-method.md) dentro de la variable `registerPostTrackCallback`. La configuración de llamadas de seguimiento en esta variable provoca un bucle infinito de solicitudes de imagen.

Cada vez que llama a la variable `registerPostTrackCallback`, vincula esa función para que se ejecute de forma inmediata después de que se envíe correctamente una solicitud de imagen. Evite registrar la misma función varias veces en la misma carga de página.

>[!NOTE]
>
>No se garantiza el tiempo y el orden de las funciones activadas entre [`registerPreTrackCallback`](registerpretrackcallback.md) y `registerPostTrackCallback`. Evite las dependencias entre estas dos funciones.

## Llamada de retorno posterior al seguimiento con la extensión Web SDK

¡Muy pronto!

## Llamada de retorno posterior al seguimiento implementando manualmente Web SDK

Puede utilizar una promesa de JavaScript al enviar un evento para registrar una función después de que los datos se envíen correctamente a Adobe.

```js
alloy("sendEvent",{
  "xdm": {}
}).then(function(result) {
  Console.Log("Data was successfully sent.");
});
```

Consulte [Gestión de respuestas de eventos](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#handling-responses-from-events) en la documentación de Web SDK para obtener más información.

## Registro de devoluciones de llamada posterior al seguimiento con la extensión Adobe Analytics

No hay ningún campo dedicado en la extensión de Adobe Analytics para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.registerPostTrackCallback en AppMeasurement y el editor de código personalizado de la extensión de Analytics

`s.registerPostTrackCallback` es una función que toma una función como su único argumento. La función anidada se ejecuta justo después de que se envíe una solicitud de imagen.

```js
s.registerPostTrackCallback(function(){/* Desired code */});
```

Si desea utilizar la URL de solicitud de imagen en el código, haga referencia al argumento de la cadena `requestUrl` dentro de la función anidada. Puede analizar la variable `requestUrl` para el uso deseado; el ajuste de esta variable no afecta a la recopilación de datos.

```js
s.registerPostTrackCallback(function(requestUrl){
  console.log(requestUrl); // Outputs the full image request URL
});
```

Se pueden incluir argumentos adicionales en la función `s.registerPostTrackCallback`, que se puede utilizar en la función anidada:

```js
s.registerPostTrackCallback(function(requestUrl,a,b,c) {
    console.log(requestUrl); // Full image request URL
    console.log(a); // param1
    console.log(b); // param2
    console.log(c); // param3
}, "param1", "param2", "param3");
```

## Caso de uso

El registro de la función [`clearVars()`](clearvars.md) en la devolución de llamada posterior al seguimiento puede ser beneficioso para aplicaciones de una sola página. Cada vez que envía una visita a Adobe, se ejecuta la función `clearVars()`. La implementación puede definir las variables de nuevo sin preocuparse por los valores que persisten incorrectamente.

```js
s.registerPostTrackCallback(function(){s.clearVars();});
```

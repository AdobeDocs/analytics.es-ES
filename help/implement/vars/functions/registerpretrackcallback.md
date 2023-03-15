---
title: registerPreTrackCallback
description: Cree funciones de devolución de llamada antes de enviar una visita a Adobe.
feature: Variables
exl-id: 11c960d7-ded4-441a-822f-463d3a137d2d
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 61%

---

# registerPreTrackCallback

La variable `registerPreTrackCallback` permite a la organización conectar una función de JavaScript después de compilar una dirección URL de solicitud de imagen pero antes de enviarla. Puede utilizar esta variable para enviar datos recopilados por AppMeasurement a un socio o a una infraestructura interna.

>[!WARNING]
>
>No llame ninguna llamada de seguimiento como [`t()`](t-method.md) o [`tl()`](tl-method.md) dentro de la variable [`registerPostTrackCallback`](registerposttrackcallback.md). Las funciones de seguimiento en esta variable provocan un bucle infinito de solicitudes de imagen.

Cada vez que llama a la variable `registerPreTrackCallback`, vincula esa función para que se ejecute cada vez que se compile una URL de solicitud de imagen. Evite registrar la misma función varias veces en la misma carga de página.

>[!NOTE]
>
>No se garantiza el tiempo y el orden de las funciones activadas entre `registerPreTrackCallback` y `registerPostTrackCallback`. Evite las dependencias entre estas dos funciones.

## Realizar un seguimiento previo de las llamadas de retorno mediante la extensión SDK web

El SDK web no tiene la capacidad de conectar una función después de compilar los datos pero antes de enviarlos al Adobe. Sin embargo, puede utilizar `onBeforeEventSend` para registrar una función para ejecutarla justo antes de enviar los datos.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad de etiquetas deseada.
1. Vaya a la [!UICONTROL Extensiones] y, a continuación, haga clic en **[!UICONTROL Configurar]** botón debajo de [!UICONTROL SDK web de Adobe Experience Platform].
1. En [!UICONTROL Recopilación de datos], haga clic en **[!UICONTROL Editar en antes del código de devolución de llamada de envío de evento]** botón.
1. Coloque el código deseado en el editor.

## Realizar un seguimiento previo de las llamadas de retorno implementando manualmente el SDK web

El SDK web no tiene la capacidad de conectar una función después de compilar los datos pero antes de enviarlos al Adobe. Sin embargo, puede utilizar `onBeforeEventSend` para registrar una función que se ejecutará justo antes de enviar los datos, de forma similar a `doPlugins`. Consulte [Modificación de eventos globalmente](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) en la documentación del SDK web para obtener más información.

```js
// Set the trackingCode XDM field to "New value"
alloy("configure", {
  "onBeforeEventSend": function(content) {
    content.xdm.marketing.trackingCode = "New value";
  }
})
```

## Llamada de retorno previa al seguimiento con la extensión Adobe Analytics

No hay ningún campo dedicado en la extensión de Adobe Analytics para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.registerPreTrackCallback en el editor de código personalizado de la extensión de Analytics y AppMeasurement

`s.registerPreTrackCallback` es una función que toma una función como su único argumento. La función anidada se ejecuta justo antes de que se envíe una solicitud de imagen.

```js
s.registerPreTrackCallback(function(){/* Desired code */});
```

Si desea utilizar la URL de solicitud de imagen en el código, haga referencia al argumento de la cadena `requestUrl` dentro de la función anidada. Puede analizar la variable `requestUrl` para el uso deseado; el ajuste de esta variable no afecta a la recopilación de datos.

```js
s.registerPreTrackCallback(function(requestUrl){
  console.log(requestUrl); // Outputs the full image request URL
});
```

Puede incluir argumentos adicionales en la función `s.registerPreTrackCallback`, que se pueden usar en la función anidada:

```js
s.registerPreTrackCallback(function(requestUrl,a,b,c) {
    console.log(requestUrl); // Full image request URL
    console.log(a); // param1
    console.log(b); // param2
    console.log(c); // param3
}, "param1", "param2", "param3");
```

>[!NOTE]
>
>La configuración de variables de página o la modificación de la cadena `requestUrl` dentro de esta función **no** afectan a la solicitud de imagen enviada poco después de esta llamada de función. En su lugar, utilice la variable [`doPlugins()`](doplugins.md).

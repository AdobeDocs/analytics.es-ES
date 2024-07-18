---
title: registerPreTrackCallback
description: Cree funciones de devolución de llamada antes de enviar una visita a Adobe.
feature: Variables
exl-id: 11c960d7-ded4-441a-822f-463d3a137d2d
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 55%

---

# registerPreTrackCallback

La variable `registerPreTrackCallback` permite a la organización conectar una función de JavaScript después de compilar una dirección URL de solicitud de imagen pero antes de enviarla. Puede utilizar esta variable para enviar datos recopilados por AppMeasurement a un socio o a una infraestructura interna.

>[!WARNING]
>
>No realice llamadas de seguimiento como [`t()`](t-method.md) o [`tl()`](tl-method.md) dentro de la variable `registerPreTrackCallback`. La configuración de llamadas de seguimiento en esta variable provoca un bucle infinito de solicitudes de imagen.

Cada vez que llama a la variable `registerPreTrackCallback`, vincula esa función para que se ejecute cada vez que se compile una URL de solicitud de imagen. Evite registrar la misma función varias veces en la misma carga de página.

>[!NOTE]
>
>No se garantiza el tiempo y el orden de las funciones activadas entre `registerPreTrackCallback` y `registerPostTrackCallback`. Evite las dependencias entre estas dos funciones.

## Realizar un seguimiento previo de las llamadas de retorno mediante la extensión SDK web

El SDK web no puede conectar una función después de compilar los datos pero antes de enviarlos al Adobe. Sin embargo, puede usar `onBeforeEventSend` para registrar una función para que se ejecute justo antes de que se envíen los datos.

1. Inicie sesión en la interfaz de usuario de [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad de etiquetas deseada.
1. Vaya a la pestaña [!UICONTROL Extensions] y, a continuación, haga clic en el botón **[!UICONTROL Configure]** en [!UICONTROL Adobe Experience Platform Web SDK].
1. En [!UICONTROL Recopilación de datos], haga clic en el botón **[!UICONTROL Editar en antes del código de devolución de llamada de envío de evento]**.
1. Coloque el código deseado en el editor.

## Realizar un seguimiento previo de las llamadas de retorno implementando manualmente el SDK web

El SDK web no puede conectar una función después de compilar los datos pero antes de enviarlos al Adobe. Sin embargo, puede usar `onBeforeEventSend` para registrar una función que se va a ejecutar justo antes de enviar los datos, de forma similar a `doPlugins`. Consulte [Modificación de eventos globalmente](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) en la documentación del SDK web para obtener más información.

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

## s.registerPreTrackCallback en el AppMeasurement y el editor de código personalizado de la extensión de Analytics

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

---
title: abort
description: La variable abort es un booleano que evita que se envíe una visita a los servidores de recopilación de datos de Adobe.
feature: Variables
exl-id: e4e25a89-272b-4444-b52b-c7fe2478ff30
role: Admin, Developer
source-git-commit: 5ef8ba686a13f8b4ab592c0b48a9c074b0477fcf
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 39%

---

# abort

La variable `abort` es un booleano que puede evitar que la siguiente llamada de seguimiento se envíe al Adobe. Existe una funcionalidad similar en el SDK web que le permite devolver `false` antes de enviar un evento XDM.

## Cancelación del envío de un evento mediante la extensión del SDK web

Use el editor de código [!UICONTROL Activado antes de la devolución de llamada al evento] y devuelva `false`.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad de etiquetas deseada.
1. Vaya a la pestaña [!UICONTROL Extensions] y, a continuación, haga clic en el botón **[!UICONTROL Configure]** en [!UICONTROL Adobe Experience Platform Web SDK].
1. En [!UICONTROL Recopilación de datos], haga clic en el botón **[!UICONTROL Editar en antes del código de devolución de llamada de envío de evento]**.
1. En el editor de código, ponga el siguiente código en cualquier condición en la que desee cancelar el envío de datos a Edge:

```js
return false;
```

## Cancelación del envío de un evento manualmente mediante la implementación del SDK web

Use la llamada de retorno `onBeforeEventSend` y devuelva `false`. Consulte [Modificación de eventos globalmente](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=es#modifying-events-globally) en la documentación del SDK web para obtener más información.

```js
alloy("configure"), {
    "onBeforeEventSend": function(content) {
        return false;
    }
}
```

## Uso de la variable abort en la extensión de Adobe Analytics

No hay ningún campo dedicado en la extensión de Adobe Analytics para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.abort en el AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `s.abort` es booleana. Su valor predeterminado es `false`.

* Si se establece como `true`, la siguiente llamada de seguimiento ([`t()`](../functions/t-method.md) o [`tl()`](../functions/tl-method.md)) no envía ningún dato a Adobe.
* Si se establece el valor como `false` o no se establece ninguno, esta variable no hace nada.

```js
s.abort = true;
```

>[!NOTE]
>
>La variable `abort` se restablece como `false` después de cada llamada de seguimiento. Si desea cancelar llamadas de seguimiento subsiguientes en la misma página, vuelva a establecer `abort` en `true`.

La variable `abort` se puede establecer en la función [`doPlugins()`](../functions/doplugins.md), que es la última función que se ejecuta antes de que se envíe una solicitud de imagen al Adobe. Este ejemplo funciona de manera similar a la llamada de retorno `onBeforeEventSend` mediante el SDK web.

```js
s.doPlugins = function(s) {
    s.campaign = s.Util.getQueryParam("cid");
    if ((!s.campaign) && (!s.events)) {
        s.abort = true;
    }
};
```

Puede centralizar la lógica utilizada para identificar la actividad que no se quiere seguir, como algunos vínculos personalizados o vínculos externos para mostrar anuncios.

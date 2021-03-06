---
title: abort
description: La variable abort es un booleano que evita que se envíe una visita a los servidores de recopilación de datos de Adobe.
feature: Variables
exl-id: e4e25a89-272b-4444-b52b-c7fe2478ff30
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 40%

---

# abort

La variable `abort` es un booleano que puede evitar que la siguiente llamada de seguimiento se envíe a Adobe. Existe una funcionalidad similar en el SDK web que le permite devolver `false` antes de enviar un evento XDM.

## Cancelar el envío de un evento mediante la extensión del SDK web

Utilice la variable [!UICONTROL Activado antes de que el evento envíe una llamada de retorno] editor de código y devolución `false`.

1. Iniciar sesión en [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) uso de sus credenciales de Adobe ID.
1. Haga clic en la propiedad de etiquetas deseada.
1. Vaya a la [!UICONTROL Extensiones] y, a continuación, haga clic en la pestaña **[!UICONTROL Configurar]** botón debajo de [!UICONTROL SDK web de Adobe Experience Platform].
1. En [!UICONTROL Recopilación de datos], haga clic en **[!UICONTROL Editar antes del código de llamada de retorno de envío de evento]** botón.
1. En el editor de código, coloque el siguiente código bajo cualquier condición en la que desee anular el envío de datos a Edge:

```js
return false;
```

## Cancelar el envío de un evento implementando manualmente el SDK web

Utilice la variable `onBeforeEventSend` devolución de llamada y devolución `false`. Consulte [Modificación global de eventos](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) en la documentación del SDK web para obtener más información.

```js
alloy("configure"), {
    "onBeforeEventSend": function(content) {
        return false;
    }
}
```

## Uso de la variable abort en la extensión de Adobe Analytics

No hay un campo específico en la extensión de Adobe Analytics para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.abort en AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `s.abort` es booleana. Su valor predeterminado es `false`.

* Si se establece como `true`, la siguiente llamada de seguimiento ([`t()`](../functions/t-method.md) o [`tl()`](../functions/tl-method.md)) no envía ningún dato a Adobe.
* Si se establece el valor como `false` o no se establece ninguno, esta variable no hace nada.

```js
s.abort = true;
```

>[!NOTE]
>
>La variable `abort` se restablece como `false` después de cada llamada de seguimiento. Si necesita cancelar llamadas de seguimiento subsiguientes en la misma página, establezca `abort` nuevamente como `true`.

Por ejemplo, la variable `abort` se puede configurar en la variable [`doPlugins()`](../functions/doplugins.md) , que es la última función que se ejecuta antes de que se envíe una solicitud de imagen al Adobe. Este ejemplo funciona de forma similar a la variable `onBeforeEventSend` llamada de retorno mediante el SDK web.

```js
s.doPlugins = function(s) {
    s.campaign = s.Util.getQueryParam("cid");
    if ((!s.campaign) && (!s.events)) {
        s.abort = true;
    }
};
```

Puede centralizar la lógica utilizada para identificar la actividad que no se quiere seguir, como algunos vínculos personalizados o vínculos externos para mostrar anuncios.

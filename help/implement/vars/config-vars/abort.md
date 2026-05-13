---
title: abort
description: La variable abort es un booleano que evita que se envíe una visita a los servidores de recopilación de datos de Adobe.
feature: Appmeasurement Implementation
exl-id: e4e25a89-272b-4444-b52b-c7fe2478ff30
role: Admin, Developer
TQID: https://experienceleague.adobe.com/xVOUnGUxNcQqBGAoDxefFBT1Yg2mKzpXLPSVFqOcJSM
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 343
ht-degree: 39%

---

# abort

La variable `abort` es un booleano que puede evitar que la siguiente llamada de seguimiento se envíe a Adobe. Existe una funcionalidad similar en Web SDK que le permite devolver `false` antes de enviar un evento XDM.

## Cancelación del envío de un evento con la extensión Web SDK

Use el editor de código [!UICONTROL Activado antes de la devolución de llamada al evento] y devuelva `false`.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad de etiquetas deseada.
1. Vaya a la pestaña [!UICONTROL Extensions] y, a continuación, haga clic en el botón **[!UICONTROL Configure]** en [!UICONTROL Adobe Experience Platform Web SDK].
1. En [!UICONTROL Recopilación de datos], haga clic en el botón **[!UICONTROL Editar en antes del código de devolución de llamada de envío de evento]**.
1. En el editor de código, ponga el siguiente código en cualquier condición en la que desee cancelar el envío de datos a Edge:

```js
return false;
```

## Cancelar el envío de un evento manualmente al implementar Web SDK

Use la llamada de retorno `onBeforeEventSend` y devuelva `false`. Consulte [Modificación de eventos globalmente](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) en la documentación de Web SDK para obtener más información.

```js
alloy("configure"), {
    "onBeforeEventSend": function(content) {
        return false;
    }
}
```

## Uso de la variable abort en la extensión de Adobe Analytics

No hay ningún campo dedicado en la extensión de Adobe Analytics para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.abort en AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `s.abort` es booleana. Su valor predeterminado es `false`.

* Si se establece como `true`, la siguiente llamada de seguimiento ([`t()`](../functions/t-method.md) o [`tl()`](../functions/tl-method.md)) no envía ningún dato a Adobe.
* Si se establece el valor como `false` o no se establece ninguno, esta variable no hace nada.

```js
s.abort = true;
```

>[!NOTE]
>
>La variable `abort` se restablece como `false` después de cada llamada de seguimiento. Si desea cancelar llamadas de seguimiento subsiguientes en la misma página, vuelva a establecer `abort` en `true`.

La variable `abort` se puede establecer en la función [`doPlugins()`](../functions/doplugins.md), que es la última función que se ejecuta antes de que se envíe una solicitud de imagen a Adobe. Este ejemplo funciona de manera similar a la llamada de retorno `onBeforeEventSend` mediante Web SDK.

```js
s.doPlugins = function(s) {
    s.campaign = s.Util.getQueryParam("cid");
    if ((!s.campaign) && (!s.events)) {
        s.abort = true;
    }
};
```

Puede centralizar la lógica utilizada para identificar la actividad que no se quiere seguir, como algunos vínculos personalizados o vínculos externos para mostrar anuncios.

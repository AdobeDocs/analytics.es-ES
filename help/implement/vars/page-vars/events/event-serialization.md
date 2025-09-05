---
title: Serialización de eventos
description: Ayuda a deduplicar métricas en el sitio.
feature: Appmeasurement Implementation
exl-id: 54de0fd7-9056-44af-bd59-b8eb55fc816e
role: Admin, Developer
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 83%

---

# Serialización del ID de evento

La serialización de eventos es el proceso de implementación de medidas para evitar que los informes de Analytics incluyan eventos duplicados. La deduplicación de eventos es importante en los casos en que no desee que las métricas se inflen con los visitantes que actualizan la página.

>[!NOTE]
>
>Las fuentes de datos no son compatibles con la serialización de eventos ni la deduplicación.

## Configurar la serialización de eventos

En primer lugar, debe configurar la [!UICONTROL grabación de eventos únicos] de un evento para [!UICONTROL utilizar el ID de evento] en la configuración del grupo de informes. Consulte [Evento de éxito](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/c-success-events/success-event.md) en la guía de usuario de administración.

Al utilizar ID de evento, la deduplicación se produce en los siguientes niveles:

* Cada variable utiliza su propia tabla para la deduplicación. Por ejemplo, `event1:ABC` y `event2:ABC` se cuentan en los informes.
* La deduplicación se produce globalmente en todos los visitantes. Si el visitante A envía `event1:ABC` y el visitante B también envía `event1:ABC`, Adobe ignora la segunda instancia del visitante B.
* La deduplicación no caduca. Si un visitante envía `event1:ABC` y vuelve 2 años después y envía `event1:ABC` nuevamente, Adobe ignora la segunda instancia.

>[!TIP]
>
>Si desea deduplicar el evento [`purchase`](event-purchase.md), utilice la variable [`purchaseID`](../purchaseid.md) en su lugar.

## Uso de ID de eventos mediante el SDK web

Si se usa el [**objeto XDM**](/help/implement/aep-edge/xdm-var-mapping.md), la serialización de eventos usa el campo XDM `id` del evento deseado. La ruta completa de XDM depende del evento que se desea serializar.

Por ejemplo, si desea serializar la métrica Adiciones al carro de compras, establezca `xdm.commerce.productListAdds.id` en el valor de serialización deseado. Si desea serializar el evento personalizado 20, establezca `xdm._experience.analytics.event1to100.event20` en el valor de serialización deseado.

Si se usa el [**objeto de datos**](/help/implement/aep-edge/data-var-mapping.md), la serialización de eventos usa `data.__adobe.analytics.events`, siguiendo la sintaxis de cadena de AppMeasurement.

## Uso de ID de eventos con la extensión de Adobe Analytics

Puede establecer el campo de ID de evento al configurar la extensión de Analytics (variables globales) o como una acción en una regla.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad de etiquetas deseada.
3. Vaya a la pestaña [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en una acción existente de [!UICONTROL Adobe Analytics: Establecer variables] o haga clic en el icono “+”.
5. Establezca la lista desplegable [!UICONTROL Extension] en Adobe Analytics y [!UICONTROL Action Type] en [!UICONTROL Set Variables].
6. Busque la sección [!UICONTROL Eventos], donde cada evento contiene un campo [!UICONTROL ID de evento].

Los valores válidos son caracteres alfanuméricos de hasta 20 bytes de longitud. Si introduce un valor que supera los 20 bytes, el sistema lo truncará a los primeros 20 bytes.

## Utilice ID de eventos en AppMeasurement y el editor de código personalizado de la extensión de Analytics

La serialización de eventos es parte de la variable `s.events`. Asigne un ID a cada evento utilizando dos puntos en la cadena.

```js
// Assign custom ID serialization to a single value
s.events = "event1:ABC123";

// Assign custom ID serialization to multiple values
s.events = "event1:ABC123,event2:ABC123";
```

Si un evento tiene habilitada la serialización pero no contiene un ID de serialización, siempre se contará el evento.

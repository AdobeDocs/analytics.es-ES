---
title: Serialización de eventos
description: Ayuda a deduplicar métricas en el sitio.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Serialización del ID de evento

La serialización de eventos es el proceso de implementación de medidas para evitar que los informes de Analytics incluyan eventos duplicados. La deduplicación de eventos es importante en los casos en que no desee que las métricas se inflen con los visitantes que actualizan la página.

>[!NOTE] Las fuentes de datos no son compatibles con la serialización de eventos ni la deduplicación.

## Configurar la serialización de eventos

Primero debe establecer un evento [!UICONTROL Unique Event Recording] en la configuración [!UICONTROL Use Event ID] del grupo de informes. Consulte [Evento de éxito](/help/admin/admin/c-success-events/success-event.md) en la guía de usuario de administración.

Al utilizar ID de evento, la deduplicación se produce en los siguientes niveles:

* Cada variable utiliza su propia tabla para la deduplicación. Por ejemplo, `event1:ABC` y `event2:ABC` se cuentan en los informes.
* La deduplicación se produce globalmente en todos los visitantes. Si el visitante A envía `event1:ABC` y el visitante B también envía `event1:ABC`, Adobe ignora la segunda instancia del visitante B.
* La deduplicación no caduca. Si un visitante envía `event1:ABC` y vuelve 2 años después y envía `event1:ABC` nuevamente, Adobe ignora la segunda instancia.

>[!TIP] Si desea deduplicar el evento [`purchase`](event-purchase.md), utilice la variable [`purchaseID`](../purchaseid.md) en su lugar.

## Uso del ID de evento en Adobe Experience Platform Launch

Puede establecer el campo de ID de evento al configurar la extensión de Analytics (variables globales) o como una acción en una regla.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad deseada.
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. En [!UICONTROL Actions], haga clic en una [!UICONTROL Adobe Analytics - Set Variables] acción existente o en el icono &#39;+&#39;.
5. Establezca el [!UICONTROL Extension] menú desplegable en Adobe Analytics y el valor [!UICONTROL Action Type] en [!UICONTROL Set Variables].
6. Busque la [!UICONTROL Events] sección, donde cada evento contiene un [!UICONTROL Event ID] campo.

Los valores válidos son caracteres alfanuméricos de hasta 20 bytes de longitud.

## Uso del ID de eventos en el editor de código personalizado de AppMeasurement y Launch

La serialización de eventos es parte de la variable `s.events`. Asigne un ID a cada evento utilizando dos puntos en la cadena.

```js
// Assign custom ID serialization to a single value
s.events = "event1:ABC123";

// Assign custom ID serialization to multiple values
s.events = "event1:ABC123,event2:ABC123";
```

Si un evento tiene habilitada la serialización pero no contiene un ID de serialización, siempre se contará el evento.

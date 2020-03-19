---
title: Serialización de eventos
description: Ayuda a eliminar la duplicación de métricas en el sitio.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Serialización de ID de evento

La serialización de eventos es el proceso de implementación de medidas para evitar que los informes de Analytics incluyan eventos duplicados. La eliminación de duplicaciones de eventos es importante en los casos en que no desee que las métricas se inflen con los visitantes que actualizan la página.

> [!NOTE] Las fuentes de datos no son compatibles con la serialización de eventos ni la deduplicación.

## Configurar la serialización de eventos

Primero debe establecer los eventos [!UICONTROL Unique Event Recording] en la configuración del grupo [!UICONTROL Use Event ID] de informes. See [Success Events](/help/admin/admin/c-success-events/success-event.md) in the Admin user guide.

Al utilizar ID de evento, la anulación de duplicación se produce en los siguientes niveles:

* Cada variable utiliza su propia tabla para la eliminación de duplicaciones. Por ejemplo, `event1:ABC` y `event2:ABC` se cuentan en los informes.
* La desduplicación se produce globalmente en todos los visitantes. Si el visitante A envía `event1:ABC` entonces el visitante B también lo hace `event1:ABC`, Adobe ignora la segunda instancia del visitante B.
* La desduplicación no caduca. Si un visitante envía `event1:ABC` y vuelve 2 años después y lo envía `event1:ABC` nuevamente, Adobe ignora la segunda instancia.

> [!TIP] Si desea anular la duplicación del [`purchase`](event-purchase.md) evento, utilice la [`purchaseID`](../purchaseid.md) variable en su lugar.

## Uso de ID de evento en Adobe Experience Platform Launch

Puede establecer el campo de ID de evento al configurar la extensión de Analytics (variables globales) o como una acción en una regla.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Haga clic en la propiedad que desee.
3. Vaya a la [!UICONTROL Rules] ficha y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Actions], haga clic en una [!UICONTROL Adobe Analytics - Set Variables] acción existente o en el icono &#39;+&#39;.
5. Establezca el [!UICONTROL Extension] menú desplegable en Adobe Analytics y el valor [!UICONTROL Action Type] en [!UICONTROL Set Variables].
6. Localice la [!UICONTROL Events] sección, donde cada evento contiene un [!UICONTROL Event ID] campo.

Los valores válidos son caracteres alfanuméricos de hasta 20 bytes de longitud.

## Usar ID de eventos en AppMeasurement e Iniciar editor de código personalizado

La serialización de eventos es parte de la `s.events` variable. Asigne un ID a cada evento utilizando dos puntos en la cadena.

```js
// Assign custom ID serialization to a single value
s.events = "event1:ABC123";

// Assign custom ID serialization to multiple values
s.events = "event1:ABC123,event2:ABC123";
```

Si un evento tiene habilitada la serialización pero no contiene un ID de serialización, siempre se cuenta el evento.

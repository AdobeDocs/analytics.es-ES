---
title: Serialización de eventos
description: Ayuda a eliminar la duplicación de métricas en el sitio.
translation-type: tm+mt
source-git-commit: c5a60bc9756af2742740dbc6a26a081f55ee3235

---


# Serialización de ID de evento

La serialización de eventos es el proceso de implementación de medidas para evitar que los informes de Analytics incluyan eventos duplicados. La eliminación de duplicaciones de eventos es importante en los casos en que no desee que las métricas se inflen con los visitantes que actualizan la página.

> [!NOTE] Las fuentes de datos no son compatibles con la serialización de eventos ni la deduplicación.

## Configurar la serialización de eventos

En primer lugar, debe configurar la grabación [!UICONTROL de eventos] únicos de un evento para [!UICONTROL utilizar la ID] de evento en la configuración del grupo de informes. See [Success Events](../../../../admin/admin/c-success-events/success-event.md) in the Admin user guide.

Al utilizar ID de evento, la anulación de duplicación se produce en los siguientes niveles:

* Cada variable utiliza su propia tabla para la eliminación de duplicaciones. Por ejemplo, `event1:ABC` y `event2:ABC` se cuentan en los informes.
* La desduplicación se produce globalmente en todos los visitantes. Si el visitante A envía `event1:ABC` entonces el visitante B también lo hace `event1:ABC`, Adobe ignora la segunda instancia del visitante B.
* La desduplicación no caduca. Si un visitante envía `event1:ABC` y vuelve 2 años después y lo envía `event1:ABC` nuevamente, Adobe ignora la segunda instancia.

> [!TIP] Si desea anular la duplicación del `purchase` evento, utilice la `purchaseID` variable en su lugar.

## Uso de ID de evento en Adobe Experience Platform Launch

Puede establecer el campo de ID de evento al configurar la extensión de Analytics (variables globales) o como una acción en una regla.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Haga clic en la propiedad que desee.
3. Vaya a la ficha [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en una acción existente de [!UICONTROL Adobe Analytics - Establecer variables] o haga clic en el icono &#39;+&#39;.
5. Defina el menú desplegable [!UICONTROL Extensión] en Adobe Analytics y el tipo [!UICONTROL de] acción en [!UICONTROL Establecer variables].
6. Busque la sección [!UICONTROL Eventos] , donde cada evento contiene un campo ID [!UICONTROL de] evento.

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

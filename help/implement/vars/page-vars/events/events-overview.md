---
title: events
description: Configure la variable “events” (eventos), que gobierna la mayoría de las métricas del sitio.
translation-type: ht
source-git-commit: 2fd6e3b561d02bdbdd77b0be982614e765c870e2
workflow-type: ht
source-wordcount: '676'
ht-degree: 100%

---


# events

Las dimensiones y las métricas son componentes fundamentales para los informes. La variable `events` es responsable de la recopilación de datos de muchas métricas del sitio. Los eventos suelen incrementar las [métricas](/help/components/metrics/overview.md) en los informes.

Antes de implementar eventos, asegúrese de crearlos y configurarlos en [Eventos de éxito](/help/admin/admin/c-success-events/success-event.md) en la configuración del grupo de informes. Si planea utilizar eventos personalizados en las visitas de seguimiento de vínculos, asegúrese de que [`linkTrackVars`](../../config-vars/linktrackvars.md) y [`linkTrackEvents`](../../config-vars/linktrackevents.md) están correctamente configurados.

## Eventos en Adobe Experience Platform Launch

Puede establecer eventos al configurar la extensión de Analytics (variables globales) o en reglas.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad deseada.
3. Vaya a la pestaña [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en una acción existente de [!UICONTROL Adobe Analytics: Establecer variables] o haga clic en el icono “+”.
5. Establezca el menú desplegable [!UICONTROL Extensión] en Adobe Analytics y el [!UICONTROL tipo de acción] en [!UICONTROL Establecer variables].
6. Busque la sección [!UICONTROL Eventos].

Hay varias funciones disponibles:

* Un menú desplegable permite seleccionar el evento que se va a incluir.
* Un campo de texto opcional permite la serialización. Consulte [Serialización de eventos](event-serialization.md) para obtener más información.
* Campo de texto opcional para un valor de evento. Puede incluir moneda para eventos de moneda o un entero para eventos que no sean de moneda para incrementar la cifra varias veces. Por ejemplo, si selecciona `event1` en la lista desplegable e incluye `10` en este campo, los informes se incrementan `event1` en 10.
* Botón para agregar otro evento. No hay un límite razonable para el número de eventos que puede incluir en una visita.

## “s.events” en el editor de código personalizado de AppMeasurement y Launch

La variable `s.events` es una cadena que contiene una lista de eventos delimitada por comas que se pueden incluir en la visita. No hay límite de bytes para esta variable, por lo que no se trunca. Los valores válidos son los siguientes:

* `event1` - `event1000`: Eventos personalizados, establezca lo que desee. Registre cómo se utiliza cada evento en el [documento de diseño de soluciones](../../../prepare/solution-design.md) de su organización. El número de eventos disponibles depende del contrato de Analytics de su organización. La mayoría de las organizaciones con contratos no incluidos tienen disponibles 1000 eventos personalizados. Contacte con el administrador de cuentas de su organización si no está seguro de cuántos eventos personalizados tiene a su disposición.
* `purchase`: Aumenta la métrica [“Pedidos”](/help/components/metrics/orders.md) en 1, y toma los valores establecidos en la variable `products` para calcular [“Unidades”](/help/components/metrics/units.md) e [“Ingresos”](/help/components/metrics/revenue.md). Consulte [Evento de compra](event-purchase.md) para obtener más información.
* `prodView`: Aumenta la métrica [“Vistas del producto”](/help/components/metrics/product-views.md).
* `scOpen`: Aumenta la métrica [“Carros de compras”](/help/components/metrics/carts.md).
* `scAdd`: Aumenta la métrica [“Adiciones al carro de compras”](/help/components/metrics/cart-additions.md).
* `scRemove`: Aumenta la métrica [“Eliminaciones del carro de compras”](/help/components/metrics/cart-removals.md).
* `scView`: Aumenta la métrica [“Vistas del carro de compras”](/help/components/metrics/cart-views.md).
* `scCheckout`: Aumenta la métrica [“Compras finalizadas”](/help/components/metrics/checkouts.md).

>[!NOTE]
>
>: Esta variable distingue entre mayúsculas y minúsculas. Evite utilizar mayúsculas y minúsculas en los valores de eventos para garantizar una recopilación de datos precisa.

```js
// Set the events variable to a single value
s.events = "event1";

// Set the events variable to multiple values
s.events = "event1,event13,purchase";
```

### Incrementar eventos de contador varias veces

Si lo desea, puede contar eventos personalizados más de una vez. Asigne un número entero al evento deseado dentro de la cadena. Los eventos creados en la configuración del grupo de informes se catalogan como eventos de contador de forma predeterminada.

```js
// Count event1 ten times
s.events = "event1=10";

// Count event1 twice and event2 once
s.events = "event1=2,event2";
```

>[!NOTE]
>
>Los eventos de contador no admiten valores decimales o de moneda. Utilice eventos monetarios para moneda o eventos numéricos para valores decimales.

### Usar eventos de moneda

Puede cambiar un evento personalizado para utilizar moneda en lugar de enteros. Los eventos de moneda hacen la conversión automática a la moneda del grupo de informes si esta y la variable `currencyCode` no coinciden. Son útiles para calcular los costes de envío, los descuentos o los reembolsos. Puede configurar eventos de moneda en la variable `products` si desea atribuir el evento únicamente a ese producto.

Antes de implementar eventos de moneda, asegúrese de establecer el evento deseado en “Moneda” en [Eventos de éxito](/help/admin/admin/c-success-events/success-event.md) en la configuración del grupo de informes.

```js
// Send $9.99 USD in event1 using the events variable. Make sure the event type for event1 is Currency in Report suite settings
s.currencyCode = "USD";
s.events = "event1=9.99";

// Send $9.99 USD in event1 using the products variable. Make sure the event type for event1 is Currency in Report suite settings
s.currencyCode = "USD";
s.events = "event1";
s.products = "Example category;Example product;1;0;event1=9.99";
```

>[!NOTE]
>
>Si establece un valor de moneda tanto en la variable `events` como en la variable `products`, se utiliza el valor de moneda en `events`. Evite establecer valores monetarios en las variables `events` y `products`.

### Usar eventos numéricos

Puede cambiar un evento personalizado para aceptar valores decimales en lugar de enteros. Los eventos numéricos se comportan de manera similar a los eventos de moneda, excepto que no utilizan la conversión monetaria. Puede establecer eventos numéricos en la variable `products` si desea atribuir el evento únicamente a ese producto.

Antes de implementar eventos numéricos, asegúrese de establecer el evento deseado en “Numérico” en [Eventos de éxito](/help/admin/admin/c-success-events/success-event.md) en la configuración del grupo de informes.

```js
// Send 4.5 in event1 using the events variable. Make sure the event type for event1 is Numeric in Report suite settings
s.events = "event1=4.5";

// Send 4.5 in event1 using the products variable. Make sure the event type for event1 is Numeric in Report suite settings
s.events = "event1";
s.products = "Example category;Example product;1;0;event1=4.5";
```

>[!NOTE]
>
>Si establece un valor numérico tanto en la variable `events` como en la variable `products`, se utiliza el valor numérico en `events`. Evite establecer valores numéricos en las variables `events` y `products`.

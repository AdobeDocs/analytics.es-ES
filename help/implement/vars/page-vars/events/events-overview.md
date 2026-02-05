---
title: events
description: Configure la variable “events” (eventos), que gobierna la mayoría de las métricas del sitio.
feature: Appmeasurement Implementation
exl-id: 6ef99ee5-40c3-4ff2-a75d-c97f2e8ec1f8
role: Admin, Developer
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: ht
source-wordcount: '845'
ht-degree: 100%

---

# events

Las dimensiones y las métricas son componentes fundamentales para los informes. La variable `events` es responsable de la recopilación de datos de muchas métricas del sitio. Los eventos suelen incrementar las [métricas](/help/components/metrics/overview.md) en los informes.

Antes de implementar eventos, asegúrese de crearlos y configurarlos en [Eventos de éxito](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/c-success-events/success-event.md) en la configuración del grupo de informes. Si planea utilizar eventos personalizados en las visitas de seguimiento de vínculos, asegúrese de que [`linkTrackVars`](../../config-vars/linktrackvars.md) y [`linkTrackEvents`](../../config-vars/linktrackevents.md) están correctamente configurados.

## Eventos con el SDK web

Si se usa el [objeto XDM](/help/implement/aep-edge/xdm-var-mapping.md), los eventos personalizados utilizarán los siguientes campos XDM:

* Los eventos personalizados 1-100 se asignan a `xdm._experience.analytics.event1to100.event1` - `xdm._experience.analytics.event1to100.event100`.
* Los eventos personalizados 101-200 se asignan a `xdm._experience.analytics.event101to200.event100` - `xdm._experience.analytics.event101to200.event200`.
* Este patrón se repite cada 100 eventos en `xdm._experience.analytics.event901to1000.event901` - `xdm._experience.analytics.event901to1000.event1000`. `eventx.value` se utiliza para especificar la cantidad que se va a incrementar. `eventx.id` se usa para la [serialización](event-serialization.md).
* Los pedidos se asignan a `xdm.commerce.purchases.value`.
* Las unidades se asignan a la suma de todos los campos `productListItems[].quantity`.
* Los ingresos se asignan a la suma de todos los campos `productListItems[].priceTotal`.
* Las vistas del producto se asignan a `xdm.commerce.productViews.value`.
* Los carros de compras se asignan a `xdm.commerce.productListOpens.value`.
* Las adiciones al carro de compras se asignan a `xdm.commerce.productListAdds.value`.
* Las eliminaciones del carro de compras se asignan a `xdm.commerce.productListRemovals.value`.
* Las vistas del carro de compras se asignan a `xdm.commerce.productListViews.value`.
* Los cierres de compra se asignan a `xdm.commerce.checkouts.value`.

>[!NOTE]
>
>Si se establece un evento en `productListItems` (por ejemplo, `productListItems._experience.analytics.event1.value`) y aún no está en este campo, se agregará automáticamente a dicho campo.

Si se usa el [**objeto de datos**](/help/implement/aep-edge/data-var-mapping.md), todos los eventos utilizarán `data.__adobe.analytics.events`, siguiendo la sintaxis de cadena de AppMeasurement. Si establece este campo, los eventos establecidos en el objeto XDM se sobrescriben y no se envían a Adobe Analytics.

## Eventos con la extensión de Adobe Analytics

Puede establecer eventos al configurar la extensión de Analytics (variables globales) o en reglas.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad de etiquetas deseada.
3. Vaya a la pestaña [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en una acción existente de [!UICONTROL Adobe Analytics: Establecer variables] o haga clic en el icono “+”.
5. Establezca la lista desplegable [!UICONTROL Extensión] en Adobe Analytics y el [!UICONTROL tipo de acción] en [!UICONTROL Establecer variables].
6. Busque la sección [!UICONTROL Eventos].

Hay varias funciones disponibles:

* Una lista desplegable que le permite seleccionar el evento que se va a incluir
* Un campo de texto opcional permite la serialización. Consulte [Serialización de eventos](event-serialization.md) para obtener más información.
* Campo de texto opcional para un valor de evento. Puede incluir moneda para eventos de moneda o un entero para eventos que no sean de moneda para incrementar la cifra varias veces. Por ejemplo, seleccionando `event1` en la lista desplegable e incluyendo `10` en este campo, la creación de informes se incrementa `event1` en 10.
* Botón para añadir otro evento. Puede agregar tantos eventos como desee a una única regla dentro de lo razonable.

## s.events en AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `s.events` es una cadena que contiene una lista de eventos delimitada por comas que se pueden incluir en la visita. La variable permite hasta 64 kB, lo que efectivamente permite tantos eventos como necesite una visita. Los valores válidos son los siguientes:

* `event1` - `event1000`: Eventos personalizados, establezca lo que desee. Registre cómo se utiliza cada evento en el [documento de diseño de soluciones](../../../prepare/solution-design.md) de su organización. El número de eventos disponibles depende del contrato de Analytics de su organización. La mayoría de las organizaciones con contratos no incluidos tienen disponibles 1000 eventos personalizados. Contacte con el equipo de cuentas de Adobe si no está seguro de cuántos eventos personalizados tiene a su disposición.
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

Antes de implementar eventos de moneda, asegúrese de establecer el evento deseado en “Moneda” en [Eventos de éxito](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/c-success-events/success-event.md) en la configuración del grupo de informes.

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

Antes de implementar eventos numéricos, asegúrese de establecer el evento deseado en “Numérico” en [Eventos de éxito](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/c-success-events/success-event.md) en la configuración del grupo de informes.

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

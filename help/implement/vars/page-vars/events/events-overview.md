---
title: Events
description: Configure la variable events, que gobierna la mayoría de las métricas del sitio.
translation-type: tm+mt
source-git-commit: c7d596be4f70c820039725be6a5fddc8572156d9

---


# Events

Las dimensiones y las métricas son componentes vitales para los informes. La `events` variable es responsable de la recopilación de datos de muchas métricas del sitio.

## Eventos en el lanzamiento de Adobe Experience Platform

Puede establecer eventos al configurar la extensión de Analytics (variables globales) o en reglas.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Haga clic en la propiedad que desee.
3. Vaya a la ficha [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en una acción existente de [!UICONTROL Adobe Analytics - Establecer variables] o haga clic en el icono &#39;+&#39;.
5. Defina el menú desplegable [!UICONTROL Extensión] en Adobe Analytics y el tipo [!UICONTROL de] acción en [!UICONTROL Establecer variables].
6. Busque la sección [!UICONTROL Eventos] .

Hay varias funciones disponibles:

* Un menú desplegable permite seleccionar el evento que se va a incluir
* Campo de texto opcional para la serialización. See [event serialization](event-serialization.md) for more information.
* Campo de texto opcional para un valor de evento. Puede incluir moneda para eventos de moneda o un entero para eventos que no sean de moneda para incrementarla varias veces. Por ejemplo, si selecciona `event1` en la lista desplegable e incluye `10` en este campo, los informes se incrementan `event1` en 10.
* Botón para agregar otro evento. No hay un límite razonable para el número de eventos que puede incluir en una visita.

## s.events en el editor de código personalizado AppMeasurement e Launch

La `s.events` variable es una cadena que contiene una lista de eventos delimitada por comas para incluir en la visita. No hay límite de bytes para esta variable, por lo que no se trunca. Los valores válidos son los siguientes:

* `event1` - `event1000`: Eventos personalizados, establezca lo que desee. Registre cómo se utiliza cada evento en el documento [de diseño de](../../../prepare/solution-design.md)soluciones de su organización. El número de eventos disponibles depende del contrato de Analytics de su organización. La mayoría de las organizaciones con contratos no preexistentes tienen disponibles 1000 eventos personalizados. Póngase en contacto con el administrador de cuentas de su organización si no está seguro de cuántos eventos personalizados tiene a su disposición.
* `purchase`:: Aumenta la métrica &#39;Pedidos&#39; en 1 y toma los valores establecidos en la `products` variable para calcular &#39;Unidades&#39; e &#39;Ingresos&#39;. Consulte [Evento](event-purchase.md) de compra para obtener más información.
* `prodView`:: Aumenta la métrica &quot;Vistas del producto&quot;.
* `scOpen`:: Aumenta la métrica &#39;Carros de compras&#39;.
* `scAdd`:: Aumenta la métrica &#39;Adiciones al carro de compras&#39;.
* `scRemove`:: Aumenta la métrica &#39;Eliminaciones del carro de compras&#39;.
* `scView`:: Aumenta la métrica &quot;Vistas del carro de compras&quot;.
* `scCheckout`:: Incrementa la métrica &#39;Cierres de compras&#39;.

> [!TIP] Esta variable distingue entre mayúsculas y minúsculas. Evite utilizar mayúsculas y minúsculas en los valores de eventos para garantizar una recopilación de datos precisa.

```js
// Set the events variable to a single value
s.events = "event1";

// Set the events variable to multiple values
s.events = "event1,event13,purchase";
```

### Incrementar eventos de contador varias veces

Si lo desea, puede contar eventos personalizados más de una vez. Asigne un entero al evento deseado dentro de la cadena. Los eventos creados en la configuración del grupo de informes son eventos de contador de forma predeterminada.

```js
// Count event1 ten times
s.events = "event1=10";

// Count event1 twice and event2 once
s.events = "event1=2,event2";
```

> [!NOTE] Los eventos de contador no admiten valores decimales o de moneda. Utilice eventos monetarios para moneda o eventos numéricos para valores decimales.

### Usar eventos de moneda

Puede cambiar un evento personalizado para utilizar moneda en lugar de enteros. Los eventos de moneda se convierten automáticamente a la moneda del grupo de informes si la moneda del grupo de informes y la `currencyCode` variable no coinciden. Son útiles para calcular los costes de envío, los descuentos o los reembolsos. Puede configurar eventos de moneda en la `products` variable si desea atribuir el evento únicamente a ese producto.

```js
// Send $9.99 USD in event1 using the events variable. Make sure the event type for event1 is Currency in report suite settings
s.currencyCode = "USD";
s.events = "event1=9.99";

// Send $9.99 USD in event1 using the products variable. Make sure the event type for event1 is Currency in report suite settings
s.currencyCode = "USD";
s.events = "event1";
s.products = "Example category;Example product;1;0;event1=9.99";
```

> [!NOTE] Si establece un valor de moneda tanto en la `events` variable como en la `products` variable, se utiliza el valor de moneda en `events` . Evite establecer valores monetarios en las variables `events` y `products` .

### Usar eventos numéricos

Puede cambiar un evento personalizado para aceptar valores decimales en lugar de enteros. Los eventos numéricos se comportan de manera similar a los eventos monetarios, excepto que no utilizan la conversión de moneda. Puede establecer eventos numéricos en la `products` variable si desea atribuir el evento únicamente a ese producto.

```js
// Send 4.5 in event1 using the events variable. Make sure the event type for event1 is Numeric in report suite settings
s.events = "event1=4.5";

// Send 4.5 in event1 using the products variable. Make sure the event type for event1 is Numeric in report suite settings
s.events = "event1";
s.products = "Example category;Example product;1;0;event1=4.5";
```

> [!NOTE] Si establece un valor numérico tanto en la `events` variable como en la `products` variable, se utiliza el valor numérico en `events` . Evite establecer valores numéricos en las variables `events` y `products` .

---
title: Evento de compra
description: Utilice el evento purchase para recopilar datos de las métricas 'Pedidos', 'Unidades' e 'Ingresos'.
translation-type: tm+mt
source-git-commit: 7a1c3c7ed0e509969e281e865e8ff2c969a18bcb

---


# Evento de compra

El evento purchase es un valor en la `events` variable. Este valor es útil para las organizaciones que desean recopilar datos en torno a los ingresos que genera su sitio. Depende en gran medida de las `products` variables y `purchaseID` .

Al configurar un evento de compra, éste afecta a las siguientes métricas:

* La métrica &#39;Pedidos&#39; se incrementa en 1
* La métrica &#39;Unidades&#39; aumenta por el número de productos en la `products` variable
* La métrica &#39;Ingresos&#39; aumenta por la suma de los parámetros de precio en la `products` variable

## Configurar el evento de compra en Adobe Experience Platform Launch

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Haga clic en la propiedad que desee.
3. Vaya a la ficha [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en una acción existente de [!UICONTROL Adobe Analytics - Establecer variables] o haga clic en el icono &#39;+&#39;.
5. Defina el menú desplegable [!UICONTROL Extensión] en Adobe Analytics y el tipo [!UICONTROL de] acción en [!UICONTROL Establecer variables].
6. Busque la sección [!UICONTROL Eventos] y establezca el menú desplegable Eventos en [!UICONTROL compra].

Otras variables dependientes como `products` y `purchaseID` no tienen campos dedicados en Launch. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement para estas variables.

## Configure el evento purchase en el editor de código personalizado AppMeasurement e Launch

El evento purchase es una cadena que se establece como parte de la variable events.

```js
// Set the purchase event by itself
s.events = "purchase";

// Set the purchase event alongside other events
s.events = "purchase,event1,event2";
```

## Desduplicación de eventos de compra

Cuando se activa un evento de compra, Adobe comprueba lo siguiente:

* ¿Contiene la visita la `purchaseID` variable? Si no es así, Adobe utiliza la información de la visita para crear un &quot;ID de compra temporal&quot;. Este ID de compra temporal solo se aplica al visitante de la visita. Los 5 ID de compra temporales anteriores se almacenan para cada ID de visitante por grupo de informes.
* ¿Coincide el ID de compra temporal con alguno de los últimos cinco ID de compra temporal almacenados? En caso afirmativo, la solicitud de imagen se considera una compra duplicada. En el informe no aparece ninguna variable de conversión y tampoco el evento de compra.
* Si la `purchaseID` variable está definida, ¿coincide con algún valor ya recopilado en el grupo de informes en todos los visitantes? En caso afirmativo, la solicitud de imagen se considera una compra duplicada. En el informe no aparece ninguna variable de conversión y tampoco el evento de compra.

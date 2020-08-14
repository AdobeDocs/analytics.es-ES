---
title: Evento de compra
description: Utilice el evento de compra para recopilar datos de las métricas “Pedidos”, “Unidades” e “Ingresos”.
translation-type: ht
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: ht
source-wordcount: '387'
ht-degree: 100%

---


# Evento de compra

El evento de compra es un valor en la variable `events`. Este valor es útil para las organizaciones que desean recopilar datos en torno a los ingresos que genera su sitio. Depende en gran medida de las variables [`products`](../products.md) y [`purchaseID`](../purchaseid.md).

Al configurar un evento de compra, este afecta a las siguientes métricas:

* La métrica “Pedidos” se incrementa en 1
* La métrica “Unidades” aumenta por el número de productos en la variable `products`
* La métrica “Ingresos” aumenta por la suma de los parámetros de precio en la variable `products`

>[!NOTE]
>
>Los ingresos no se multiplican por el campo de cantidad. Por ejemplo, `s.products="Womens;Socks;5;4.50"` no pasa 22,50 $ a los ingresos, sino que pasa 4,50 $. Compruebe que la implementación pasa los ingresos totales en relación con la cantidad enumerada. Por ejemplo: `s.products="Womens;Socks;5;22.50"`.

## Configurar el evento de compra en Adobe Experience Platform Launch

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad deseada.
3. Vaya a la pestaña [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en una acción existente de [!UICONTROL Adobe Analytics: Establecer variables] o haga clic en el icono “+”.
5. Establezca el menú desplegable [!UICONTROL Extensión] en Adobe Analytics y el [!UICONTROL tipo de acción] en [!UICONTROL Establecer variables].
6. Busque la sección [!UICONTROL Eventos] y establezca el menú desplegable Eventos en [!UICONTROL compra].

Otras variables dependientes como `products` y `purchaseID` no tienen campos dedicados en Launch. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement para estas variables.

## Configure el evento de compra en el editor de código personalizado AppMeasurement y Launch

El evento de compra es una cadena que se establece como parte de la variable de eventos.

```js
// Set the purchase event by itself
s.events = "purchase";

// Set the purchase event alongside other events
s.events = "purchase,event1,event2";
```

## Deduplicación de eventos de compra

Cuando se activa un evento de compra, Adobe comprueba lo siguiente:

* ¿La visita contiene la variable `purchaseID`? Si no es así, Adobe utiliza la información de la visita para crear un “ID de compra temporal”. Este ID de compra temporal solo se aplica al visitante de la visita. Los 5 ID de compra temporales anteriores se almacenan para cada ID de visitante por grupo de informes.
* ¿Coincide el ID de compra temporal con cualquiera de los últimos cinco ID de compra temporal almacenados? En caso afirmativo, la solicitud de imagen se considera una compra duplicada. En el informe no aparece ninguna variable de conversión y tampoco el evento de compra.
* Si la variable `purchaseID` está definida, ¿coincide con algún valor ya recopilado en el grupo de informes en todos los visitantes? En caso afirmativo, la solicitud de imagen se considera una compra duplicada. En el informe no aparece ninguna variable de conversión y tampoco el evento de compra.

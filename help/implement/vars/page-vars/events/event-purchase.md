---
title: Evento de compra
description: Utilice el evento de compra para recopilar datos de las métricas “Pedidos”, “Unidades” e “Ingresos”.
feature: Appmeasurement Implementation
exl-id: 5ad148d6-cf45-4dea-846a-255004300bc2
role: Admin, Developer
TQID: https://experienceleague.adobe.com/r-L330P6HA5qWBmEW-2LwECo-d3dhVK1ovWsfraErXE
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 474
ht-degree: 75%

---

# Evento de compra

El evento de compra es un valor en la variable `events`. Este valor es útil para las organizaciones que desean recopilar datos en torno a los ingresos que genera su sitio. Depende en gran medida de las variables [`products`](../products.md) y [`purchaseID`](../purchaseid.md).

Al configurar un evento de compra, este afecta a las siguientes métricas:

* La métrica “Pedidos” se incrementa en 1
* La métrica “Unidades” aumenta por el número de productos en la variable `products`
* La métrica “Ingresos” aumenta por la suma de los parámetros de precio en la variable `products`

>[!NOTE]
>
>Los ingresos no se multiplican por el campo de cantidad. Por ejemplo, `s.products="Womens;Socks;5;4.50"` no pasa 22,50 $ a los ingresos, sino que pasa 4,50 $. Asegúrese de que la implementación pasa los ingresos totales en relación con la cantidad enumerada. Por ejemplo, `s.products="Womens;Socks;5;22.50"`.

## Configuración del evento de compra mediante Web SDK

Si se usa el [**objeto XDM**](/help/implement/aep-edge/xdm-var-mapping.md), el evento de compra utilizará los siguientes campos XDM:

* Los pedidos se asignan a `xdm.commerce.purchases.value`.
* Las unidades se asignan a la suma de todos los campos `xdm.productListItems[].quantity`. Consulte [`products`](../products.md) para obtener más información.
* Los ingresos se asignan a la suma de todos los campos `xdm.productListItems[].priceTotal`.

```json
{
  "xdm": {
    "commerce": {
      "purchases": {
        "value": 1
      }
    }
  }
}
```

Si se usa el [**objeto de datos**](/help/implement/aep-edge/data-var-mapping.md), el evento de compra usa `data.__adobe.analytics.events`, siguiendo la sintaxis de cadena de AppMeasurement.

```json
{
  "data": {
    "__adobe": {
      "analytics": {
        "events": "purchase"
      }
    }
  }
}
```

## Configure el evento de compra con la extensión Adobe Analytics

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad de etiquetas deseada.
3. Vaya a la pestaña [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en una acción existente de [!UICONTROL Adobe Analytics: Establecer variables] o haga clic en el icono “+”.
5. Establezca la lista desplegable [!UICONTROL Extensión] en Adobe Analytics y el [!UICONTROL tipo de acción] en [!UICONTROL Establecer variables].
6. Busque la sección [!UICONTROL Eventos] y establezca la lista desplegable [!UICONTROL Eventos] en [!UICONTROL compra].

Otras variables dependientes como `products` y `purchaseID` no tienen campos dedicados en la extensión de Analytics en la recopilación de datos de Adobe Experience Platform. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement para estas variables.

## Configure el evento de compra en AppMeasurement y el editor de código personalizado de la extensión de Analytics

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

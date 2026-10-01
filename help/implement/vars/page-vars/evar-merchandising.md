---
title: eVar (variable de comercialización)
description: Variables personalizadas que se relacionan con productos individuales.
feature: Appmeasurement Implementation
exl-id: 26e0c4cd-3831-4572-afe2-6cda46704ff3
mini-toc-levels: 3
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/BdChWcR9AJqLZ0KjOxSvFAjB8-58JmmGahrpvTyFeFI'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
    internal-label: Appmeasurement implementation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: ca917b867cd84b09b899ce7b72586f0b15003106
workflow-type: tm+mt
source-wordcount: '787'
ht-degree: 29%
---
# eVar (comercialización)

>[!BEGINSHADEBOX]

*Esta página de ayuda describe cómo implementar eVars de comercialización. Para obtener información sobre cómo funcionan las eVars de comercialización como dimensiones, consulte [eVar (dimensión de comercialización)](/help/components/dimensions/evar-merchandising.md) en la guía de usuario sobre componentes.*

>[!ENDSHADEBOX]

Las eVars de comercialización enlazan un valor a productos individuales, de modo que los eventos de éxito que involucran a cada producto se acreditan al valor enlazado a ese producto. Puede establecer el valor de una de las dos maneras siguientes:

* **[!UICONTROL Sintaxis del producto]**: establezca el valor de cada producto en la variable [`products`](products.md).
* **[!UICONTROL Sintaxis de la variable de conversión]**: establezca el valor en el propio eVar. El valor se enlaza a los productos en una visita que contiene un evento de enlace.

Para ver cómo funcionan el enlace, la asignación y la caducidad, consulte [eVar (dimensión de comercialización)](/help/components/dimensions/evar-merchandising.md).

## Configurar eVars en la configuración del grupo de informes

Antes de usar eVars en la implementación, asegúrese de configurar la eVar con la sintaxis deseada en la configuración del grupo de informes. Consulte [Variables de conversión](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md) en la guía de administración.

>[!WARNING]
>
>Si no se configuran correctamente las eVars de comercialización, se pueden producir valores inesperados o incluso perder datos para la variable. Asegúrese de que esté correctamente configurado para su implementación.

## Elija una sintaxis.

Use [!UICONTROL Sintaxis del producto] cuando el valor de comercialización esté disponible en el momento de establecer la variable `products` o cuando los productos de la misma visita necesiten valores diferentes. Use [!UICONTROL Sintaxis de la variable de conversión] cuando el valor se conozca antes del producto, como el término de búsqueda o la campaña interna que condujo al visitante al producto. Consulte [Funcionamiento del enlace y la asignación](/help/components/dimensions/evar-merchandising.md#how-binding-and-allocation-work) para ver una comparación completa.

## Implementar mediante sintaxis de producto

Cuando se habilita [!UICONTROL Sintaxis del producto], el valor de comercialización se establece directamente en la variable `products`, por lo que no se utilizan eventos de enlace. Las eVars de comercialización van en el último segmento de cada producto:

```js
s.products = "[category];[name];[quantity];[revenue];[events];[eVars]";
```

Delimite varias eVars de comercialización en el mismo producto con una barra vertical (`|`). Los marcadores de posición vacíos para cantidad, ingresos y eventos son necesarios aunque no los utilice. Sin ellos, se ignora el valor eVar.

El valor está enlazado al producto en esa visita. El que un valor posterior reemplace un enlace existente depende de la configuración de [!UICONTROL Asignación]. Ver [Cómo funcionan el enlace y la asignación](/help/components/dimensions/evar-merchandising.md#how-binding-and-allocation-work).

```js
// The bare minimum to set a merchandising eVar with product syntax
s.products = ";Example product;;;;eVar1=Example merchandising value";

// An example single product with product syntax
s.products = "Example category;Example product;1;5.99;event1=1;eVar1=Turtles";

// Tie a merchandising eVar to different values on two different products
s.products = "Birds;Scarlet Macaw;1;4200;;eVar1=talking bird,Birds;Turtle dove;2;550;;eVar1=love birds";
```

### Sintaxis del producto mediante el SDK web

Si se usa el [**objeto XDM**](/help/implement/aep-edge/xdm-var-mapping.md), las variables de comercialización de sintaxis de producto usan los siguientes campos XDM:

* Las eVars de comercialización de sintaxis de producto están asignados en `xdm.productListItems[]._experience.analytics.customDimensions.eVars.eVar1` a `xdm.productListItems[]._experience.analytics.customDimensions.eVars.eVar250`.
* Los eventos de comercialización de sintaxis de producto están asignados en `xdm.productListItems[]._experience.analytics.event1to100.event1.value` a `xdm.productListItems[]._experience.analytics.event901to1000.event1000.value`. Los campos XDM de [serialización de eventos](events/event-serialization.md) están asignados en `xdm.productListItems[]._experience.analytics.event1to100.event1.id` a `xdm.productListItems[]._experience.analytics.event901to1000.event1000.id`.

>[!NOTE]
>
>Cuando establece eventos en `productListItems`, no es necesario establecerlos en la cadena de evento. Si se establecen en ambos lugares, el valor de la cadena de evento tiene prioridad.

El siguiente ejemplo muestra un único [producto](products.md) que usa varias eVars y eventos de comercialización:

```json
"productListItems": [
  {
    "name": "Bahama Shirt",
    "priceTotal": "12.99",
    "quantity": 3,
    "_experience": {
      "analytics": {
        "customDimensions" : {
          "eVars" : {
            "eVar10" : "green",
            "eVar33" : "large"
          }
        },
        "event1to100" : {
          "event4" : {
            "value" : 1
          },
          "event10" : {
            "value" : 2,
            "id" : "abcd"
          }
        }
      }
    }
  }
]
```

El objeto del ejemplo anterior se enviaría a Adobe Analytics como `";Bahama Shirt;3;12.99;event4|event10=2:abcd;eVar10=green|eVar33=large"`.

Si se usa el [**objeto de datos**](/help/implement/aep-edge/data-var-mapping.md), las eVars de comercialización de sintaxis de producto se establecen en `data.__adobe.analytics.products`, con la misma sintaxis que la variable de AppMeasurement `products`. El equivalente del objeto de datos del ejemplo de XDM anterior:

```json
"data": {
  "__adobe": {
    "analytics": {
      "products": ";Bahama Shirt;3;12.99;event4|event10=2:abcd;eVar10=green|eVar33=large"
    }
  }
}
```

## Implementación y uso de la sintaxis de la variable de conversión

Use [!UICONTROL Sintaxis de la variable de conversión] cuando el valor de eVar no esté disponible para establecerse en la variable `products`. Esto suele significar que la página de producto no tiene contexto para el método de búsqueda o el canal de comercialización. En estos casos, configure eVar de comercialización en la página donde se produce el evento de enlace o antes de ella. El valor persiste hasta que caduca o se sobrescribe con un nuevo valor.

Cuando una visita contiene la variable `products` y un [!UICONTROL evento de enlace de comercialización] seleccionado, el valor actual de eVar se enlaza a todos los productos de esa visita. Configurar eVar junto a un producto sin un evento de enlace no enlaza el valor. El que un enlace posterior reemplace a uno existente depende de la configuración de [!UICONTROL Asignación]. Ver [Cómo funcionan el enlace y la asignación](/help/components/dimensions/evar-merchandising.md#how-binding-and-allocation-work).

Para ver un ejemplo que establece varias eVars de método de localización de productos a la vez, consulte [Práctica recomendada: métodos de localización de productos](/help/components/dimensions/evar-merchandising.md#best-practice-product-finding-methods).

El siguiente ejemplo establece un eVar de comercialización antes del evento de enlace:

```js
// Place on the same or previous page before the binding event:
s.eVar1 = "Aviary";

// Place on the page where the binding event occurs:
s.events = "prodView";
s.products = ";Canary";
```

Si [!UICONTROL Evento de vista de producto] es un evento de enlace, el valor `"Aviary"` de `eVar1` está enlazado al producto `"Canary"`. Los eventos de éxito posteriores que involucran este producto se acreditan a `"Aviary"`. El valor `"Aviary"` también se enlaza a productos en visitas posteriores que contengan un evento de enlace, hasta que se cumpla una de las siguientes condiciones:

* La eVar caduca (según la configuración [!UICONTROL Caduca después de]).
* Que la eVar de comercialización se sobrescriba con un nuevo valor.

### Sintaxis de variables de conversión mediante el SDK web

Si se usa el objeto [**XDM**](/help/implement/aep-edge/xdm-var-mapping.md), la sintaxis funciona de manera similar a la implementación de otras [eVars](evar.md) y [eventos](events/events-overview.md). Si se usa el [**objeto de datos**](/help/implement/aep-edge/data-var-mapping.md), la sintaxis sigue a AppMeasurement.

La duplicación XDM del ejemplo de AppMeasurement anterior tendría el siguiente aspecto.

Establezca la eVar en la misma llamada de evento o en la anterior:

```json
"_experience": {
  "analytics": {
    "customDimensions": {
      "eVars": {
        "eVar1" : "Aviary"
      }
    }
  }
}
```

Establezca el evento de enlace y los valores para la cadena de productos:

```json
"commerce": {
  "productViews" : {
    "value" : 1
  }
},
"productListItems": [
  {
    "name": "Canary"
  }
]
```

Los objetos de datos que reflejan el ejemplo de AppMeasurement anterior tendrían el siguiente aspecto.

Establezca la eVar en la misma llamada de evento o en la anterior:

```json
"data": {
  "__adobe": {
    "analytics": {
      "eVar1": "Aviary"
    }
  }
}
```

Establezca el evento de enlace y los valores para la cadena de productos:

```json
"data": {
  "__adobe": {
    "analytics": {
      "events": "prodView",
      "products": ";Canary"
    }
  }
}
```


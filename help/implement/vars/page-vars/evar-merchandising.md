---
title: eVar (variable de comercialización)
description: Variables personalizadas que se relacionan con productos individuales.
feature: Variables
exl-id: 26e0c4cd-3831-4572-afe2-6cda46704ff3
mini-toc-levels: 3
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 100%

---

# eVar (comercialización)

*Esta página de ayuda describe cómo implementar eVars de comercialización. Para obtener información sobre cómo funcionan las eVars de comercialización como dimensiones, consulte [eVars (dimensión de comercialización)](/help/components/dimensions/evar-merchandising.md) en la guía del usuario de Componentes.*

Para obtener información detallada sobre cómo funcionan las eVars de comercialización, consulte [eVars de comercialización y métodos de búsqueda de productos](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/merchandising-evars.html?lang=es).

## Configurar eVars en la configuración del grupo de informes

Antes de usar eVars en la implementación, asegúrese de configurar la eVar con la sintaxis deseada en la configuración del grupo de informes. Consulte [Variables de conversión](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md) en la guía de administración.

>[!WARNING]
>
>Si no se configuran correctamente las eVars de comercialización, se pueden producir valores inesperados o incluso perder datos para la variable. Asegúrese de que esté correctamente configurado para su implementación.

## Implementar mediante sintaxis de producto

Si se habilita Sintaxis del producto, la categoría de comercialización se rellena directamente en la variable `products` de los productos y, por ello, no resulta necesario seleccionar y establecer un evento de enlace. Este es el método recomendado y debe usarse a menos que no se encuentre disponible el valor que debe establecerse en `products` cuando el evento de éxito tiene lugar.

```js
// The bare minimum to set a merchandising eVar with product syntax
s.products = ";Example product;;;;eVar1=Example merchandising value";

// An example single product with product syntax
s.products = "Example category;Example product;1;5.99;event1=1;eVar1=Turtles";

// Tie a merchandising eVar to a different values on two different products
s.products = "Birds;Scarlet Macaw;1;4200;;eVar1=talking bird,Birds;Turtle dove;2;550;;eVar1=love birds";
```

El valor de `eVar1` se asigna al producto. Todos los eventos de éxito subsiguientes que involucran este producto se acreditan al valor de la eVar.

### Sintaxis del producto mediante el SDK web

Las variables de comercialización de sintaxis de producto se [asignan para Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=es) en varios campos XDM diferentes.

* Las eVars de comercialización de sintaxis de producto están asignados en `productListItems[]._experience.analytics.customDimensions.eVars.eVar1` a `productListItems[]._experience.analytics.customDimensions.eVars.eVar250`.
* Los eventos de comercialización de sintaxis de producto están asignados en `productListItems[]._experience.analytics.event1to100.event1.value` a `productListItems[]._experience.analytics.event901to1000.event1000.value`. Los campos XDM de [serialización de eventos](events/event-serialization.md) están asignados en `productListItems[]._experience.analytics.event1to100.event1.id` a `productListItems[]._experience.analytics.event901to1000.event1000.id`.

>[!NOTE]
>
>Cuando establece eventos en `productListItems`, no es necesario establecerlos en la cadena de evento. Si se establecen en ambos lugares, el valor de la cadena de evento tiene prioridad.

El siguiente ejemplo muestra un único [producto](products.md) que usa varias eVars y eventos de comercialización:

```js
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

## Implementación y uso de la sintaxis de la variable de conversión

La sintaxis de la variable de conversión debe usarse cuando no se encuentre disponible el valor de la eVar que debe establecerse en la variable `products`. Por lo general, esto significa que la página no dispone de contexto para el método de búsqueda o el canal de comercialización. En estos casos, se establece la variable de comercialización antes de llegar a la página del producto. El valor persistirá hasta que se produzca el evento de enlace.

Cuando el evento de enlace seleccionado durante la configuración tenga lugar, el valor de la eVar que se ha mantenido se asociará con el producto. Por ejemplo, si `prodView` se especifica como evento de enlace, la categoría de comercialización solo se enlazará con la lista de productos actual cuando se produzca el evento. Solo los eventos de enlace subsiguientes podrán actualizar una eVar de comercialización que ya se haya asignado a un producto.

```js
// Place on the same or previous page before the binding event:
s.eVar1 = "Aviary";

// Place on the page where the binding event occurs:
s.events = "prodView";
s.products = ";Canary";
```

El valor `"Aviary"` de `eVar1` se asigna al producto `"Canary"`. Todos los eventos de éxito subsiguientes que involucran este producto se acreditan a `"Canary"`. Asimismo, el valor actual de la variable de comercialización estará enlazado con todos los productos subsiguientes hasta que se cumpla una de estas condiciones:

* Que caduque la eVar (en función de la opción “Caduca después”).
* Que la eVar de comercialización se sobrescriba con un nuevo valor.

### Sintaxis de variables de conversión mediante el SDK web

La sintaxis de variables de conversión mediante el SDK web funciona de forma similar a la implementación de otras [eVars](evar.md) y [eventos](events/events-overview.md). La duplicación XDM del ejemplo anterior tendría el siguiente aspecto:

Establezca la eVar en la misma llamada de evento o en la anterior:

```js
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

```js
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

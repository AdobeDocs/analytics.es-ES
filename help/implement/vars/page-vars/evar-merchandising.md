---
title: eVar (comercialización)
description: Variables personalizadas que se relacionan con productos individuales.
translation-type: tm+mt
source-git-commit: 52e00470df0f0c6bff84b26c1548e64ff5114fb8
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 29%

---


# eVar (comercialización)

*Esta página de ayuda describe cómo implementar las eVars de comercialización. Para obtener información sobre cómo funcionan las eVars de comercialización como una dimensión, consulte[eVars (Comercialización)](/help/components/dimensions/evar-merchandising.md)en la guía del usuario Componentes.*

## Configurar eVars en la configuración del grupo de informes

Antes de usar eVars en la implementación, asegúrese de configurar la eVar según la sintaxis deseada en la configuración del grupo de informes. Consulte [Variables de conversión](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) en la guía de administración.

>[!IMPORTANT] Si no se configuran correctamente las eVars de comercialización, se producen valores inesperados o pérdida de datos para la variable. Asegúrese de que esté correctamente configurado para su implementación.

## Implementar mediante sintaxis de producto

When &#39;Product Syntax&#39; is enabled, the merchandising category is populated directly within the `products` variable, so selecting and setting a binding event is not required. Este es el método recomendado y debe usarse a menos que no se encuentre disponible el valor que debe establecerse en `products` cuando el evento de éxito tiene lugar.

```js
// The bare minimum to set a merchandising eVar with product syntax
s.products = ";Example product;;;;eVar1=Example merchandising value";

// An example single product with product syntax
s.products = "Example category;Example product;1;5.99;event1=1;eVar1=Turtles";

// Tie a merchandising eVar to a different values on two different products
s.products = "Birds;Scarlet Macaw;1;4200;;eVar1=talking bird,Birds;Turtle dove;2;550;;eVar1=love birds";
```

El valor de `eVar1` se asigna al producto. Todos los eventos de éxito subsiguientes que involucran este producto se acreditan al valor de la eVar.

## Implementar mediante sintaxis de variable de conversión

Conversion Variable Syntax is used when the eVar value is not available to set in the `products` variable. Este escenario generalmente significa que la página no tiene contexto del canal de comercialización o del método de búsqueda. En estos casos, se establece la variable de comercialización antes de llegar a la página del producto y el valor persiste hasta que se produce el evento de enlace.

Cuando el evento de enlace seleccionado durante la configuración tenga lugar, el valor de la eVar que se ha mantenido se asociará con el producto. For example, if `prodView` is specified as the binding event, the merchandising category is tied to the current product list only at the time the event occurs. Solo los eventos de enlace subsiguientes podrán actualizar una eVar de comercialización que ya se haya asignado a un producto.

```js
// Place on the same or previous page before the binding event:
s.eVar1 = "Aviary";

// Place on the page where the binding event occurs:
s.events = "prodView";
s.products = "Birds;Canary";
```

El valor `"Aviary"` de `eVar1` se asigna al producto `"Canary"`. Todos los eventos de éxito subsiguientes que involucran este producto reciben crédito `"Canary"`. Asimismo, el valor actual de la variable de comercialización estará enlazado con todos los productos subsiguientes hasta que se cumpla una de estas condiciones:

* La eVar caduca (según la configuración &#39;Caduca después de&#39;)
* Que la eVar de comercialización se sobrescriba con un nuevo valor.

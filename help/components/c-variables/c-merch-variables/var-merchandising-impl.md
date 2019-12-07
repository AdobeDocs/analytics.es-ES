---
description: Describe cómo habilitar e implementar una variable de comercialización.
keywords: Analytics Implementation;merchandising;variable;product syntax;Conversion Variable Syntax;s.products
title: Implementación de una variable de comercialización
topic: Developer and implementation
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Implementación de una variable de comercialización

Describe cómo habilitar e implementar una variable de comercialización.

## Activación de una variable de comercialización

La comercializacón se puede habilitar para cualquier eVar personalizada en **[!UICONTROL Herramientas de administración]** &gt; **[!UICONTROL Grupos de informes]** &gt; **[!UICONTROL Conversión de variables]**.

![](assets/merch-enable.png)

| Configuración | Descripción |
|--- |--- |
| Caduca después | Determina el tiempo que deben persistir los valores de comercialización. |
| Comercialización | **Sintaxis del producto:** El valor que se establece en `s.products`.<br>**Sintaxis de la variable de conversión:** El valor que se establece en la variable de comercialización designada. |
| Evento de enlace de comercialización (solo para Sintaxis de la variable de conversión) | Indica si un producto debe enlazarse con la categoría de comercialización actual. Para seleccionar varios eventos, mantenga presionada la tecla Ctrl y haga clic en los distintos elementos de la lista. Solo puede seleccionar eventos si también se selecciona la opción "Sintaxis de la variable de conversión". |

## Implementación y uso de Sintaxis del producto

Si se habilita Sintaxis del producto, la categoría de comercialización se rellena directamente en las variables de los productos y por ello no resulta necesario seleccionar y establecer un evento de enlace. Este es el método recomendado y debe usarse a menos que no se encuentre disponible el valor que debe establecerse en `s.products` cuando el evento de éxito tiene lugar.

### Sintaxis

```js
s.products="category;product;quantity;price;event_incrementer;eVarN=merch_category|eVarM=merch_category2";
```

### Ejemplo

```js
s.events="prodView";
s.products=";Snow Goggles;;;;eVar1=goggles";
```

El valor “gafas protectoras” para eVar1 se encuentra asignado al producto “Gafas protectoras para la nieve Todos los eventos de éxito subsiguientes (adiciones de productos, cierres de compra, compras, etc.) relacionados con este producto se abonarán a "gafas protectoras".

## Implementación y uso de Sintaxis de la variable de conversión

Sintaxis de la variable de conversión debe usarse cuando no se encuentre disponible el valor de la eVar que debe establecerse en `s.products`. Por lo general, esto significa que la página no dispone de contexto para el método de búsqueda o el canal de comercialización. En estos casos, debe establecer la variable de comercialización antes de llegar a la página del producto. El valor persistirá hasta que se produzca el evento de enlace.

Cuando el evento de enlace seleccionado durante la configuración tenga lugar, el valor de la eVar que se ha mantenido se asociará con el producto. Por ejemplo, si se especifica prodView como evento de enlace, la categoría de comercialización solo se enlazará con la lista de productos actual cuando se produzca el evento. Solo los eventos de enlace subsiguientes podrán actualizar una eVar de comercialización que ya se haya asignado a un producto.

### Sintaxis

En la página del evento de enlace o en la página anterior:

```js
s.eVar1="merchandising_category";
```

En la página donde se produce el evento de enlace:

```js
s.events="prodView";
s.products="category;product";
```

### Ejemplo

En la página 1 de la visita:

```js
s.eVar1="Outdoors"
```

En la página 2 de la visita:

```js
s.events="prodView";
s.products=";Snow Goggles";
```

El valor “Naturaleza” para eVar1 se encuentra asignado al producto “Gafas protectoras para la nieve Todos los eventos de éxito subsiguientes (adiciones de productos, cierres de compra, compras, etc.) relacionados con este producto se abonarán a “gafas protectoras”. Asimismo, el valor actual de la variable de comercialización estará enlazado con todos los productos subsiguientes hasta que se cumpla una de estas condiciones:

* Que caduque la eVar (en función de la opción "Caduca después").
* Que la eVar de comercialización se sobrescriba con un nuevo valor.

## Información adicional externa

[Comercialización de sintaxis de conversión avanzada](https://analyticsdemystified.com/adobe-analytics/advanced-conversion-syntax-merchandising/) en [!DNL analyticsdemystified.com]

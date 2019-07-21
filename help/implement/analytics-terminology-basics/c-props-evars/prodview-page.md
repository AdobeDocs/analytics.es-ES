---
description: La variable products se usa para realizar el seguimiento de productos y categorías de productos (así como la cantidad de compra y el precio de compra).
keywords: Implementación de Analytics; product variable; product view; evento de éxito
seo-description: La variable products se usa para realizar el seguimiento de productos y categorías de productos (así como la cantidad de compra y el precio de compra).
seo-title: Página detallada de vista del producto
solution: Analytics
title: Página detallada de vista del producto
topic: Desarrollador e implementación
uuid: 464 c 9 daf-b 042-4 fb 8-8 ca 6-e 104 c 0 bcef 45
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Página detallada de vista del producto

La variable products se usa para realizar el seguimiento de productos y categorías de productos (así como la cantidad de compra y el precio de compra).

A success event should always be set in conjunction with the *`products`* variable.

```js
s.events="prodView"
```

>[!NOTE]
>
>While *`prodView`* is treated in implementation like an event, it does not have the same flexibility in the interface. The *`prodView`*event is an instance of the product and is only available in the *`products`* report. Adobe recomienda usar un evento *`custom`* además del evento *`prodView`.* De esta manera puede ver las métricas de la vista del producto además de otras métricas de otros informes de conversión.

```js
s.products=";diamond earrings (54321)"
```

>[!NOTE]
>
>La sintaxis de la cadena de productos debe comenzar con un punto y coma. Este es un requisito de la sintaxis heredada. Anteriormente se usaba para delimitar la categoría y el producto, pero provoca una limitación en la interfaz en caso de que quisiera cambiar la manera en que se clasifican los productos. Para disponer de la máxima flexibilidad en sus informes, es mejor dejarla en blanco y usar Clasificaciones para configurar las categorías.

## Página Carro de compras (scOpen, scAdd, scRemove ) {#section_469B64F4150149DFB6B2C731279C0BC7}

```js
s.events="scOpen,scAdd" 
s.products=";SKU" 
```

## Primera página de cierre de compra {#section_E15607A9AECB44F79631926C853CF64E}

```js
s.events="scCheckout" 
s.products=”;SKU" 
```

## Página de confirmación {#section_E006943CD5FD42358086581CA44B9660}

```js
s.events="purchase" 
s.products=";SKU" 
```

>[!NOTE]
>
>While using the SKU in the product string may make the *`products`* report less readable, it provides the maximum flexibility later when you want to classify your products. Puede crear categorías a partir de la SKU que indica acabado, fabricante, categoría y subcategoría.

Si la variable *`products`* se configura junto con el evento *`purchase`, la cantidad de compra y el precio de compra total se incluyen en el valor de products tal y como se muestra arriba.*

---
description: La variable products se usa para realizar el seguimiento de productos y categorías de productos (así como la cantidad de compra y el precio de compra).
keywords: Analytics Implementation;products variable;product view;success event
title: Página de vista detallada del producto
topic: Developer and implementation
uuid: 464c9daf-b042-4fb8-8ca6-e104c0bcef45
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Página de vista detallada del producto

La variable products se usa para realizar el seguimiento de productos y categorías de productos (así como la cantidad de compra y el precio de compra).

Siempre debe configurarse un evento de éxito junto con la variable *`products`*.

```js
s.events="prodView"
```

> [!NOTE] Aunque *`prodView`* se trata en la implementación como un evento, no tiene la misma flexibilidad en la interfaz. El evento *`prodView`* es una instancia del producto y solo está disponible en el informe *`products`*. Adobe recomienda usar un evento *`custom`* además del evento *`prodView`*. De esta manera puede ver las métricas de la vista del producto además de otras métricas de otros informes de conversión.

```js
s.products=";diamond earrings (54321)"
```

> [!NOTE] La sintaxis de la cadena de products debe comenzar por punto y coma. Este es un requisito de la sintaxis heredada. Anteriormente se usaba para delimitar la categoría y el producto, pero provoca una limitación en la interfaz en caso de que quisiera cambiar la manera en que se clasifican los productos. Para disponer de la máxima flexibilidad en sus informes, es mejor dejarla en blanco y usar Clasificaciones para configurar las categorías.

## Página Carro de compras (scOpen, scAdd, scRemove ) {#section_469B64F4150149DFB6B2C731279C0BC7}

```js
s.events="scOpen,scAdd"
s.products=";SKU"
```

## Primera página de cierre de compra {#section_E15607A9AECB44F79631926C853CF64E}

```js
s.events="scCheckout"
s.products=";SKU"
```

## Página de confirmación {#section_E006943CD5FD42358086581CA44B9660}

```js
s.events="purchase"
s.products=";SKU"
```

> [!NOTE] Aunque el uso del SKU en la cadena de productos puede hacer que el informe *`products`* sea menos legible, proporciona la máxima flexibilidad a la hora de clasificar los productos. Puede crear categorías a partir de la SKU que indica acabado, fabricante, categoría y subcategoría.

Si la variable *`products`* se configura junto con el evento *`purchase`, la cantidad de compra y el precio de compra total se incluyen en el valor de products tal y como se muestra arriba.*

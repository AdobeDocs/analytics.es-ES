---
title: products
description: Enviar datos sobre qué productos se muestran o están en el carro de compras.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 95%

---


# products

La variable `products` rastrea productos y propiedades vinculados a ellos. Esta variable se configura generalmente en páginas de productos individuales, páginas del carro de compras y páginas de confirmación de compra. Es una variable de varios valores, lo que significa que puede enviar varios productos en la misma visita y el Adobe analiza el valor en elementos de dimensión independientes.

>[!NOTE]
>
>Si esta variable se configura en una visita individual sin un evento de carro de compras en la variable [`events`](events/events-overview.md), la métrica [“Vistas del producto”](/help/components/metrics/product-views.md) se incrementa en 1. Asegúrese de establecer el evento del carro de compras correspondiente en cada visita individual con la variable `products`.

## Productos en Adobe Experience Platform Launch

No hay un campo específico en Launch para configurar esta variable; sin embargo, existen varias extensiones de terceros que pueden ayudar.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad deseada.
3. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en [!UICONTROL Catálogo] para ver todas las extensiones disponibles.
4. Busque el término “product”, que revela varias extensiones disponibles para ayudarle a configurar esta variable.

Puede utilizar una de estas extensiones o puede utilizar el editor de código personalizado siguiendo la sintaxis de AppMeasurement a continuación.

## “s.products” en el editor de código personalizado de AppMeasurement y Launch

La variable `s.products` es una cadena que contiene varios campos delimitados por producto. Cada producto individual puede contener hasta 100 bytes en todos los campos. Delimite cada campo con un punto y coma (`;`) en la cadena.

* **Categoría** (opcional): La categoría de producto global. Su organización decide cómo agrupar los productos en categorías.
* **Nombre** del producto (obligatorio): El nombre del producto.
* **Cantidad** (opcional): Cuántos de estos productos están en el carro de compras. Este campo solo se aplica a las visitas con el evento de compra.
* **Precio** (opcional): El precio total del producto como decimal. Si la cantidad es mayor que 1, establezca el precio en el total y no en el precio del producto individual. Alinee la moneda de este valor para que coincida con la variable [`currencyCode`](../config-vars/currencycode.md). No incluya el símbolo de moneda en este campo. Este campo solo se aplica a las visitas con el evento de compra.
* **Eventos** (opcional): Eventos asociados al producto. Delimite varios eventos con una barra vertical (`|`). Consulte [events](events/events-overview.md) (eventos) para obtener más información.
* **eVars** (opcional): eVars de comercialización vinculadas al producto. Delimite varias eVars de comercialización con una barra vertical (`|`). Consulte [eVars de comercialización](evar-merchandising.md) para obtener más información.

```js
// Set a single product using all available fields
s.products = "Example category;Example product;1;3.50;event1=4.99|event2=5.99;eVar1=Example merchandising value 1|eVar2=Example merchandising value 2";
```

Esta variable admite varios productos en la misma visita. Es útil para un carro de compras y pedidos que incluyen múltiples productos. Aunque hay un límite de 100 bytes por producto, la longitud total de la variable `products` es de 64 000. Separe cada producto con una coma (`,`) en la cadena.

```js
// Set multiple products - useful for when a visitor views their shopping cart
s.products = "Example category 1;Example product 1;1;3.50,Example category 2;Example product 2,1,5.99";
```

>[!IMPORTANT]
>
>Elimine todos los puntos y comas, las barras de los nombres de productos y las categorías, y los valores de eVar de comercialización. Si el nombre de un producto incluye una coma, AppMeasurement la analiza como el inicio de un nuevo producto. Este error en el análisis elimina el resto de la cadena de producto, lo que provoca datos incorrectos en dimensiones e informes.

## Ejemplos

La variable `products` es flexible cuando se omiten campos e incluyen varios productos. Esta flexibilidad puede facilitar la omisión de un delimitador, lo que hace que la implementación envíe datos incorrectos a Adobe.

```js
// Include only product and category. Common on individual product pages
s.products = "Example category;Example product";

// Include only product name if you do not want to use product category
s.products = ";Example product";

// One product has a category, the other does not. Note the comma and adjacent semicolon to omit category
s.products = "Example category;Example product 1,;Example product 2";

// A visitor purchases a single product; record quantity and price
s.events = "purchase";
s.products = "Example category;Example product;1;6.99";

// A visitor purchases multiple products with different quantities
s.events = "purchase";
s.products = "Example category;Example product 1;9;26.91,Example category;Example product 2;4;9.96";

// Attribute currency event1 only to product 2 and not product 1
s.events = "event1";
s.products = "Example category 1;Example product 1;1;1.99,Example category 2;Example product 2;1;2.69;event1=1.29";

// Use multiple numeric events in the product string
s.events = "event1,event2";
s.products = "Example category;Example product;1;4.20;event1=2.3|event2=5";

// Use merchandising eVars without any events. Note the adjacent semicolons to skip events
s.products = "Example category;Example product;1;6.69;;eVar1=Merchandising value";

// Use merchandising eVars without category, quantity, price, or events
s.products = ";Example product;;;;eVar1=Merchandising value";

// Multiple products using multiple different events and multiple different merchandising eVars
s.events = "event1,event2,event3,event4,purchase";
s.products = "Example category 1;Example product 1;3;12.60;event1=1.4|event2=9;eVar1=Merchandising value|eVar2=Another merchandising value,Example category 2;Example product 2;1;59.99;event3=6.99|event4=1;eVar3=Merchandising value 3|eVar4=Example value four";
```

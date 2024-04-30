---
title: productos
description: Enviar datos sobre qué productos se muestran o están en el carro de compras.
feature: Variables
exl-id: f26e7c93-f0f1-470e-a7e5-0e310ec666c7
role: Admin, Developer
source-git-commit: 7c8ffe8f4ccf0577136e4d7ee96340224897d2a4
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 67%

---

# productos

La variable `products` rastrea productos y propiedades vinculados a ellos. Esta variable se configura generalmente en páginas de productos individuales, páginas del carro de compras y páginas de confirmación de compra. Es una variable de varios valores, lo que significa que puede enviar varios productos en la misma visita y Adobe analiza el valor en elementos de dimensión independientes.

>[!NOTE]
>
>Si esta variable se configura en una visita individual sin la variable [`events`](events/events-overview.md), la métrica [Vistas del producto](/help/components/metrics/product-views.md) se incrementa en 1. Asegúrese de establecer los eventos correspondientes en cada visita con la variable `products`.

## Productos que utilizan el SDK web

Si se usa la variable [**Objeto XDM**](/help/implement/aep-edge/xdm-var-mapping.md), los productos se asignan a las siguientes variables:

* Categoría asignada a `xdm.productListItems[].productCategories[].categoryID`. Utiliza el primer elemento de la `productCategories[]` matriz. `lineItemId` también se asigna correctamente, pero el Adobe recomienda `categoryID` ya que es XDM estándar. Si ambos campos XDM están presentes, `lineItemId` tiene prioridad.
* El producto está asignado a `xdm.productListItems[].SKU` o `xdm.productListItems[].name`. Si ambos campos XDM están presentes, `xdm.productListItems[].SKU` se utiliza.
* La cantidad se ha asignado a `xdm.productListItems[].quantity`.
* El precio está asignado a `xdm.productListItems[].priceTotal`.
* Las eVars de comercialización se asignan a `xdm.productListItems._experience.analytics.customDimensions.eVars.eVar1` hasta `xdm.productListItems._experience.analytics.customDimensions.eVars.eVar250`, dependiendo del eVar al que desee enlazar un producto.
* Los eventos de comercialización se asignan a `xdm.productListItems[]._experience.analytics.event1to100.event1.value` hasta `xdm.productListItems._experience.analytics.event901to1000.event1000.value`, en función del evento que desee enlazar a un producto. Si establece un evento en uno de estos campos, se incluye automáticamente en la variable [evento](events/events-overview.md) cadena enviada a Adobe Analytics.

```json
{
  "xdm": {
    "productListItems": [{
      "productCategories": [{
        "categoryID": "Men's"
      }],
      "name": "Hiking boot",
      "quantity": 1,
      "priceTotal": 49.99
    },
    {
      "productCategories": [{
        "categoryID": "Camping"
      }],
      "name": "Hunting blind",
      "quantity": 3,
      "priceTotal": 699.69
    }]
  }
}
```

Si se usa la variable [**objeto de datos**](/help/implement/aep-edge/data-var-mapping.md), la variable products utiliza `data.__adobe.analytics.products` siguiente sintaxis de AppMeasurement. Si define este campo, todos los productos definidos en el objeto XDM se sobrescriben y no se envían a Adobe Analytics.

```json
{
  "data": {
    "__adobe": {
      "analytics": {
        "products": "Archery;Fletched arrow;12;159.99"
      }
    }
  }
}
```

## Productos con la extensión Adobe Analytics

No hay un campo específico en la recopilación de datos de Adobe Experience Platform para configurar esta variable; sin embargo, existen varias extensiones de terceros que pueden ayudar.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad de etiquetas deseada.
3. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en [!UICONTROL Catálogo] para ver todas las extensiones disponibles.
4. Busque el término “product”, que revela varias extensiones disponibles para ayudarle a configurar esta variable.

Puede utilizar una de estas extensiones o puede utilizar el editor de código personalizado siguiendo la sintaxis de AppMeasurement a continuación.

## s.products en AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `s.products` es una cadena que contiene varios campos delimitados por producto. Delimite cada campo con un punto y coma (`;`) en la cadena.

* **Categoría** (opcional): La categoría del producto. La longitud máxima de este campo es de 100 bytes.
* **Nombre** del producto (obligatorio): El nombre del producto. La longitud máxima de este campo es de 100 bytes.
* **Cantidad** (opcional): Cuántos de estos productos están en el carro de compras. Este campo solo se aplica a las visitas con el evento de compra.
* **Precio** (opcional): El precio total del producto como decimal. Si la cantidad es mayor que 1, establezca el precio en el total y no en el precio del producto individual. Alinee la moneda de este valor para que coincida con la variable [`currencyCode`](../config-vars/currencycode.md). No incluya el símbolo de moneda en este campo. Este campo solo se aplica a las visitas con el evento de compra.
* **Eventos** (opcional): Eventos asociados al producto. Delimite varios eventos con una barra vertical (`|`). Consulte [events](events/events-overview.md) (eventos) para obtener más información.
* **eVars** (opcional): eVars de comercialización vinculadas al producto. Delimite varias eVars de comercialización con una barra vertical (`|`). Consulte [eVars de comercialización](evar-merchandising.md) para obtener más información.

```js
// Set a single product using all available fields
s.products = "Example category;Example product;1;3.50;event1=4.99|event2=5.99;eVar1=Example merchandising value 1|eVar2=Example merchandising value 2";
```

Esta variable admite varios productos en la misma visita. Es útil para un carro de compras y pedidos que incluyen múltiples productos. La longitud máxima de todo el `products` la cadena tiene 64 k bytes. Separe cada producto con una coma (`,`) en la cadena.

```js
// Set multiple products - useful for when a visitor views their shopping cart
s.products = "Example category 1;Example product 1;1;3.50,Example category 2;Example product 2;1;5.99";
```

>[!WARNING]
>
>Elimine todos los puntos y comas, las barras de los nombres de productos y las categorías, y los valores de eVar de comercialización. Si el nombre de un producto incluye una coma, AppMeasurement la analiza como el inicio de un nuevo producto. Este error en el análisis elimina el resto de la cadena de producto, lo que provoca datos incorrectos en dimensiones e informes.

## Ejemplos

La variable `products` es flexible cuando se omiten campos e incluyen varios productos. Esta flexibilidad puede facilitar la omisión de un delimitador, lo que hace que la implementación envíe datos incorrectos a Adobe.

```js
// Include only product and category. Common on individual product pages
s.products = "Example category;Example product";

// Include only product name
s.products = ";Example product";

// One product has a category, the other does not. Note the comma and adjacent semicolon to omit category
s.products = "Example category;Example product 1,;Example product 2";

// A visitor purchases a single product; record quantity and price
s.events = "purchase";
s.products = ";Example product;1;6.99";

// A visitor purchases multiple products with different quantities
s.events = "purchase";
s.products = ";Example product 1;9;26.91,Example category;Example product 2;4;9.96";

// Attribute currency event1 only to product 2 and not product 1
s.events = "event1";
s.products = ";Example product 1;1;1.99,Example category 2;Example product 2;1;2.69;event1=1.29";

// Use multiple numeric events in the product string
s.events = "event1,event2";
s.products = ";Example product;1;4.20;event1=2.3|event2=5";

// Use merchandising eVars without any events. Note the adjacent semicolons to skip events
s.products = ";Example product;1;6.69;;eVar1=Merchandising value";

// Use merchandising eVars without category, quantity, price, or events
s.products = ";Example product;;;;eVar1=Merchandising value";

// Multiple products using multiple different events and multiple different merchandising eVars
s.events = "event1,event2,event3,event4,purchase";
s.products = "Example category 1;Example product 1;3;12.60;event1=1.4|event2=9;eVar1=Merchandising value|eVar2=Another merchandising value,Example category 2;Example product 2;1;59.99;event3=6.99|event4=1;eVar3=Merchandising value 3|eVar4=Example value four";
```

Si utiliza la `digitalData` [capa de datos](../../prepare/data-layer.md), puede iterar a través de la matriz de objetos `digitalData.product`:

```js
for(var i = 0; i < digitalData.product.length; i++) {
    // Add individual product info to the product string
    s.products += digitalData.product[i].category.primaryCategory + ";" + digitalData.product[i].productInfo.productName;
    // If there are more products, add a comma
    if(i != digitalData.product.length - 1) {
        s.products += ",";
    }
}
```

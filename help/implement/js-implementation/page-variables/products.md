---
description: Las variables de página rellenan directamente un informe, como pageName, Props de lista, Variables de lista, etc.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Variables de página
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: e9820869d16b8656ebebe11e397a3d7d8123fbcf

---


# Productos

La variable se usa para rastrear productos y categorías de productos, así como precios y cantidades de compra. Los productos se suelen configurar junto con un evento de carro o un evento

<!-- 

products.xml

 -->

>[!IMPORTANT]
>
>En enero de 2016, se actualizó la lógica que establece el evento *`prodView`* automáticamente, lo que sucede cuando hay un *`product`* pero ningún *`event`*. Esta actualización puede provocar un aumento en los eventos *`prodView`*. *`prodViews`* aumentarán solo cuando:
>
>1. La variable de eventos contiene únicamente un evento no reconocido, como *`shoppingCart`* o *`cart`*, que no son eventos válidos.
   >
   >
1. La variable *`products`* no está vacía.
>
>
Un posible efecto secundario es que las eVars de comercialización activadas por los eventos *`prodView`* podrían asociarse con un *`product`* vacío, pero solo si la *`product list`* contiene únicamente un producto no válido (como un punto y coma sin producto enumerado).

La variable *`products`* realiza el seguimiento de la manera en que los usuarios interaccionan con los productos del sitio. Por ejemplo, la variable products puede realizar el seguimiento de cuántas veces se ha visto un producto, se ha agregado al carro de compras, se ha cerrado su compra y se ha comprado. También puede realizar el seguimiento de la eficacia relativa de las categorías de comercialización del sitio. Los siguientes son escenarios habituales para usar la variable products.

La variable *`products`* siempre debe configurarse junto con un evento de éxito.

<table id="table_D5A11AFDDD364D0993D387906343DDF3"> 
 <thead> 
  <tr> 
   <th class="entry"> Tamaño máximo </th> 
   <th class="entry"> Parámetro depurador </th> 
   <th class="entry"> Informes rellenados </th> 
   <th class="entry"> Valor predeterminado </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>La cadena de productos <span class="wintitle"></span> tiene un tamaño máximo de 64 k. </p> </td> 
   <td> Productos </td> 
   <td> Productos <p>Categorías (opcional) </p> <p>Ingresos (opcional) </p> <p>Unidades (opcional) </p> <p>Eventos personalizados (opcional) </p> <p>eVars (opcional) </p> </td> 
   <td> " " </td> 
  </tr> 
 </tbody> 
</table>

**Sintaxis**

```js
"Category;Product;Quantity;Price;eventN=X[|eventN2=X2];eVarN=merch_category[|eVarN2=merch_category2]"
```

| Campo | Definición |
|---|---|
| Categoría | Contiene la categoría de producto asociada. En la versión 15, los productos se pueden asociar a varias categorías, lo que pone fin a la limitación existente en la versión 14. Si anteriormente no registraba una categoría de producto, ahora le recomendamos que empiece a rellenar este campo para los grupos de informes presentes en la versión 15. |
| Producto | (Requerido) Identificador usado para realizar el seguimiento de un producto. Este identificador se utiliza para rellenar el informe Productos. Asegúrese de usar el mismo identificador en todo el proceso de cierre de la compra. |
| Cantidad | Número de unidades compradas. Este campo se debe configurar con un evento purchase para que se registre. |
| Precio | Hace referencia al coste combinado de la cantidad total comprada (unidades x precio unitario individual), no al precio individual. Este campo se debe configurar con un evento purchase para que se registre. |
| Eventos | Eventos monetarios asociados al producto especificado. Consulte [Eventos monetarios específicos de productos](https://helpx.adobe.com/analytics/kb/comparing-event-types.html) y [Eventos monetarios de todo el pedido](https://helpx.adobe.com/analytics/kb/comparing-event-types.html). |
| eVars | Valores eVar de comercialización asociados a un producto específico. Consulte [Variables de comercialización](/help/components/c-variables/c-merch-variables/var-merchandising.md). |

Los valores incluidos en la variable *`products`* se basan en el tipo de evento que esté registrando. El delimitador de categoría/producto (;) es necesario como marcador de posición cuando se omite la categoría. Solo se requieren otros delimitadores en caso de que sea necesario distinguir el parámetro que se está incluyendo, como se muestra en los ejemplos de esta página.

**Configurar products con eventos que no son purchase**

La variable *`products`* debe configurarse junto con un evento de éxito.

**Configurar products con un evento purchase**

El evento *`purchase`* debe configurarse en la página de confirmación final (“Gracias”) del proceso de pedido. El nombre del producto, categoría, cantidad y precio se capturan todos en la variable *`products`* campaign. Aunque la variable *`purchaseID`* no es obligatoria, es muy recomendable para evitar pedidos duplicados.

**Eventos monetarios específicos de productos**

Si un evento de moneda recibe un valor en la variable *`products`* en lugar de en la variable de eventos, solo se aplica a ese valor. Esto es útil para realizar un seguimiento de descuentos específicos del producto, envíos de productos y valores similares. Por ejemplo, si ha configurado el evento 1 para realizar un seguimiento del envío de productos, un producto con un cargo de envío de "4,50" podría parecerse a lo siguiente:

```js
s.events="event1" 
s.products="Footwear;Running Shoes;1;99.99;event1=4.50"
```

En este ejemplo, el valor de 4,50 está asociado directamente al producto "Running Shoes". Si agrega event1 al informe de productos, verá cómo aparece "4,50" en el elemento de línea "Running Shoes". Al igual que ocurre con Price, este valor debe reflejar el total de la cantidad mostrada. Si tiene 2 artículos con un cargo de envío de 4,50 cada uno, el valor de event1 debe ser "9,00".

**Eventos monetarios de todo el pedido**

Si un evento de moneda recibe un valor en la lista de eventos en lugar de la variable *`products`*, se aplica a todos los productos de la variable *`products`*. Esto es útil para rastrear descuentos, envíos y valores similares en los pedidos sin modificar el precio del producto o rastreándolo en la lista de productos por separado.

Por ejemplo, si ha configurado event10 para que contenga descuentos en los pedidos, puede que aparezca una compra con un 10 % de descuento similar a la siguiente:

```js
s.events="purchase,event10=9.95" 
s.products="Footwear;Running Shoes;1;69.95,Running Essentials;Running Socks;10;29.50" 
s.purchaseID="1234567890"
```

En los informes de eventos monetarios, el total del informe representa el total del evento sin duplicados (en este ejemplo, la cantidad total de descuentos durante el período de informe) y no la suma de valores de evento para cada producto. Por ejemplo, aparecería "9,95" tanto para "Running Shoes" como para "Running Socks" y el total también sería "9,95".

> [!NOTE]si se especifica un valor para el mismo evento numérico/monetario en la variable *`products`* y en la variable *`events`*, se utiliza el valor de *`events`*.

**Problemas, preguntas y consejos**

* La variable *`products`* siempre debe configurarse junto con un evento de éxito (events). Si no se especifica un evento de éxito, el evento predeterminado es prodView.

* Elimine todas las comas y punto y comas de los nombres de producto y categoría antes de rellenar los productos.
* Elimine todos los caracteres HTML (símbolos de marca registrada, marca comercial, etc.).
* Elimine los símbolos de moneda ($) del precio.

**Ejemplos**

<table id="table_6F1334E73CE048A5AC0CC28B561C1B2D"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <code> s.products="Category;ABC123" </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.products="Category2;ABC123,;ABC456" </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.products="Category3;ABC123;1;10" </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.products="Category;ABC123;1;10,;ABC456;2;19.98" </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1" </code> <p> <code> s.products="Category;ABC123;;;event1=1.99" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99,;ABC123;2;19.98;event1=1.99" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping|evar2=3 Stars" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping, ;ABC456;2;19.98;event1=1.99|event2=100;evar1=Ground Shipping" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2,event3" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping,;ABC456;2;19.98;event1=1.99|event2=100;evar1=Ground Shipping,;;;;event3=2.9;evar3=20% off" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2,event3=9.95" </code> <p> <code> s.products="Category;ABC123;,;ABC456;2;19.98;event1=1.99|event2=100;evar1=Ground Shipping,;;;;event3=2.9;evar3=20% off" </code> </p> </td> 
  </tr> 
 </tbody> 
</table>


---
title: Unidades
description: Número total de productos comprados dentro de todos los pedidos.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 1%

---


# Unidades

La métrica &#39;Unidades&#39; muestra la cantidad total de productos comprados dentro de todos los pedidos. Esta métrica es vital para los sitios de comercio electrónico a la hora de medir la conversión. Puede combinar esta métrica con cualquier dimensión para ver qué elementos de dimensión contribuyeron a la cantidad de productos comprados. Por ejemplo: puede ver las campañas principales (usando la dimensión de código [de](../dimensions/tracking-code.md) seguimiento) o los términos de búsqueda interna principales (usando una [eVar](../dimensions/evar.md)) que contribuyeron a los productos comprados.

## Cómo se calcula esta métrica

Para cada visita individual donde `purchase` exista en la [`events`](/help/implement/vars/page-vars/events/events-overview.md) variable, sume el campo &#39;Cantidad&#39; dentro de la [`products`](/help/implement/vars/page-vars/products.md) variable.

## Comparar pedidos y unidades

La métrica [Pedidos](orders.md) sólo registra el número de eventos de compra. La métrica &#39;Unidades&#39; suele ser mayor que &#39;Pedidos&#39; porque los clientes pueden comprar más de un producto. En estos casos, existe un único pedido con varias unidades.

Si tiene pedidos superiores a las unidades, Adobe recomienda comprobar la integridad de la implementación. Es probable que la `products` variable no esté configurada correctamente en las compras, lo que generalmente no es un comportamiento deseado.

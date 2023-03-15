---
title: Unidades
description: Número total de productos comprados dentro de todos los pedidos.
feature: Metrics
exl-id: c7293445-0760-4237-83ae-812224ca6f4b
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 100%

---

# Unidades

La métrica “Unidades” muestra la cantidad total de productos comprados dentro de todos los pedidos. Esta métrica es vital para los sitios de comercio electrónico a la hora de medir la conversión. Puede combinar esta métrica con cualquier dimensión para ver qué elementos de dimensión contribuyeron a la cantidad de productos comprados. Por ejemplo, puede ver las campañas principales (usando la dimensión de [código de seguimiento](../dimensions/tracking-code.md)) o los términos de búsqueda interna principales (usando una [eVar](../dimensions/evar.md)) que contribuyeron en los productos comprados.

## Cálculo de esta métrica

Para cada visita individual donde `purchase` se incluya en la variable [`events`](/help/implement/vars/page-vars/events/events-overview.md), sume el campo “Cantidad” dentro de la variable [`products`](/help/implement/vars/page-vars/products.md).

## Comparar pedidos y unidades

La métrica [Pedidos](orders.md) solo registra el número de eventos de compra. La métrica “Unidades” suele ser mayor que “Pedidos” porque los clientes pueden comprar más de un producto. En estos casos, existe un único pedido con varias unidades.

Si tiene pedidos superiores a las unidades, Adobe recomienda comprobar la integridad de la implementación. Es probable que la variable `products` no esté configurada correctamente en las compras, lo que generalmente no es un comportamiento deseado.

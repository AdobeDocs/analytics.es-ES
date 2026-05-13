---
title: Unidades
description: Número total de productos comprados dentro de todos los pedidos.
feature: Metrics
exl-id: c7293445-0760-4237-83ae-812224ca6f4b
TQID: https://experienceleague.adobe.com/0v4pF0Iv0IzU9K4CQiTy1-IIYgMCaO37E6QTmAAEPXc
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f1f1a2d4-0976-4881-b091-c2bb8de7ffacid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 173
ht-degree: 80%

---

# Unidades

La métrica [Unidades](overview.md) muestra la cantidad total de productos comprados dentro de todos los pedidos. Esta métrica es vital para los sitios de comercio electrónico a la hora de medir la conversión. Puede combinar esta métrica con cualquier dimensión para ver qué elementos de dimensión contribuyeron a la cantidad de productos comprados. Por ejemplo, puede ver las campañas principales (usando la dimensión de [código de seguimiento](../dimensions/tracking-code.md)) o los términos de búsqueda interna principales (usando una [eVar](../dimensions/evar.md)) que contribuyeron en los productos comprados.

## Cálculo de esta métrica

Para cada visita individual donde `purchase` se incluya en la variable [`events`](/help/implement/vars/page-vars/events/events-overview.md), sume el campo “Cantidad” dentro de la variable [`products`](/help/implement/vars/page-vars/products.md).

## Comparar pedidos y unidades

La métrica [Pedidos](orders.md) solo registra el número de eventos de compra. La métrica “Unidades” suele ser mayor que “Pedidos” porque los clientes pueden comprar más de un producto. En estos casos, existe un único pedido con varias unidades.

Si tiene pedidos superiores a las unidades, Adobe recomienda comprobar la integridad de la implementación. Es probable que la variable `products` no esté configurada correctamente en las compras, lo que generalmente no es un comportamiento deseado.

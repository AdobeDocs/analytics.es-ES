---
title: Ingresos
description: El importe monetario de los productos comprados dentro de todos los pedidos.
feature: Metrics
exl-id: a70e4d93-704b-46ac-9cec-31ea20d3dcb5
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: ht
source-wordcount: '113'
ht-degree: 100%

---

# Ingresos

La métrica “Ingresos” muestra la cantidad monetaria de productos comprados dentro de todos los pedidos. Esta métrica es vital para los sitios de comercio electrónico a la hora de medir la conversión. Puede combinar esta métrica con cualquier dimensión para ver qué elementos de dimensión contribuyeron a los ingresos. Por ejemplo: puede ver las campañas principales (usando la dimensión [Código de seguimiento](../dimensions/tracking-code.md)) o los términos de búsqueda interna principales (usando una [eVar](../dimensions/evar.md)).

## Cálculo de esta métrica

Para cada visita individual donde `purchase` exista en la variable [`events`](/help/implement/vars/page-vars/events/event-purchase.md), sume el campo “Precio” dentro de la variable [`products`](/help/implement/vars/page-vars/products.md).

Esta métrica se basa en la variable [currencyCode](/help/implement/vars/config-vars/currencycode.md) si la moneda de la página es diferente a la moneda original del grupo de informes.

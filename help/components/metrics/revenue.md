---
title: Ingresos
description: El importe monetario de los productos comprados dentro de todos los pedidos.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 1%

---


# Ingresos

La métrica &#39;Ingresos&#39; muestra la cantidad monetaria de productos comprados dentro de todos los pedidos. Esta métrica es vital para los sitios de comercio electrónico a la hora de medir la conversión. Puede combinar esta métrica con cualquier dimensión para ver qué elementos de dimensión contribuyeron a los ingresos. Por ejemplo: puede ver las campañas principales (usando la dimensión Código [de](../dimensions/tracking-code.md) seguimiento) o los términos de búsqueda interna principales (usando una [eVar](../dimensions/evar.md)).

## Cómo se calcula esta métrica

Para cada visita individual donde `purchase` exista en la [`events`](/help/implement/vars/page-vars/events/event-purchase.md) variable, sume el campo &#39;Precio&#39; dentro de la [`products`](/help/implement/vars/page-vars/products.md) variable.

Esta métrica se basa en la variable [currencyCode](/help/implement/vars/config-vars/currencycode.md) si la moneda de la página es diferente a la moneda nativa del grupo de informes.

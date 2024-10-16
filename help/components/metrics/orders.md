---
title: Pedidos
description: Número de compras realizadas.
feature: Metrics
exl-id: b05abb6d-983f-43fe-80ad-a0ddf90de466
source-git-commit: a1fbd3f483d3a236fe5dc3246f5e90c1b3f51ba9
workflow-type: tm+mt
source-wordcount: '90'
ht-degree: 65%

---

# Pedidos

La [métrica](overview.md) &quot;Pedidos&quot; muestra la cantidad total de eventos de compra realizados en el sitio. Esta métrica es vital para los sitios de comercio electrónico a la hora de medir la conversión. Puede combinar esta métrica con cualquier dimensión para ver qué elementos de dimensión contribuyeron a un pedido. Por ejemplo, puede ver las campañas principales (usando la dimensión [Código de seguimiento](../dimensions/tracking-code.md)) o los términos de búsqueda interna principales (usando una [eVar](../dimensions/evar.md)) que contribuyeron a las compras.

## Cálculo de esta métrica

Esta métrica cuenta el número de visitas donde `purchase` existe en la variable [`events`](/help/implement/vars/page-vars/events/events-overview.md).

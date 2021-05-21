---
title: Pedidos
description: Número de compras realizadas.
exl-id: b05abb6d-983f-43fe-80ad-a0ddf90de466
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '91'
ht-degree: 100%

---

# Pedidos

La métrica “Pedidos” muestra la cantidad total de eventos de compra realizados en el sitio. Esta métrica es vital para los sitios de comercio electrónico a la hora de medir la conversión. Puede combinar esta métrica con cualquier dimensión para ver qué elementos de dimensión contribuyeron a un pedido. Por ejemplo, puede ver las campañas principales (usando la dimensión [Código de seguimiento](../dimensions/tracking-code.md)) o los términos de búsqueda interna principales (usando una [eVar](../dimensions/evar.md)) que contribuyeron a las compras.

## Cálculo de esta métrica

Esta métrica cuenta el número de visitas donde `purchase` existe en la variable [`events`](/help/implement/vars/page-vars/events/events-overview.md).

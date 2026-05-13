---
title: Ingresos
description: El importe monetario de los productos comprados dentro de todos los pedidos.
feature: Metrics
exl-id: a70e4d93-704b-46ac-9cec-31ea20d3dcb5
TQID: https://experienceleague.adobe.com/GJsQWf7h-TihzyNUN6e3VGzOUNyxYD1esuvXet5LM1c
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 112
ht-degree: 74%

---

# Ingresos

La métrica [Ingresos](overview.md) muestra la cantidad monetaria de productos comprados dentro de todos los pedidos. Esta métrica es vital para los sitios de comercio electrónico a la hora de medir la conversión. Puede combinar esta métrica con cualquier dimensión para ver qué elementos de dimensión contribuyeron a los ingresos. Por ejemplo: puede ver las campañas principales (usando la dimensión [Código de seguimiento](../dimensions/tracking-code.md)) o los términos de búsqueda interna principales (usando una [eVar](../dimensions/evar.md)).

## Cálculo de esta métrica

Para cada visita individual donde `purchase` exista en la variable [`events`](/help/implement/vars/page-vars/events/event-purchase.md), sume el campo “Precio” dentro de la variable [`products`](/help/implement/vars/page-vars/products.md).

Esta métrica se basa en la variable [currencyCode](/help/implement/vars/config-vars/currencycode.md) si la moneda de la página es diferente a la moneda original del grupo de informes.

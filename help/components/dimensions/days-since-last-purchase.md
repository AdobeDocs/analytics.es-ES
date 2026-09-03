---
title: Días desde la última compra
description: Número de días entre la visita actual y la última compra que realizaron.
feature: Dimensions
exl-id: 6f0d9d79-cf40-4de3-9d9f-9b1bc57f97b6
TQID: https://experienceleague.adobe.com/q86bc1bMRctUBe7dFEJaALsq0GjALFQQtKU9cRpRkoU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 173
ht-degree: 84%

---

# Días desde la última compra

La dimensión [Días transcurridos desde la última compra](overview.md) mide la cantidad de tiempo transcurrido entre la visita actual del visitante y su compra más reciente en ese momento. Esta dimensión ayuda a comprender el comportamiento de los visitantes tras comprar algo en el sitio.

Los visitantes que nunca han comprado algo no se incluyen en esta dimensión. Además, tampoco se incluyen las visitas activadas antes de la primera compra de un visitante. Solo se incluyen las visitas después de la primera compra del visitante.

## Rellene esta dimensión con datos

Adobe rellena automáticamente esta dimensión en función del evento [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) de la implementación. Si implementa el evento `purchase` en el sitio, esta dimensión siempre funciona.

## Elementos de dimensión

Los elementos de dimensión incluyen el número de días entre la compra más reciente de un visitante y la visita actual. Cada número de días es un elemento de dimensión independiente: “Mismo día” se produce cuando la compra más reciente de un visitante y la visita actual se produjeron el mismo día.

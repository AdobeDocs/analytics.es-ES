---
title: Días desde la última compra
description: Número de días entre la visita actual y la última compra que realizaron.
feature: Dimensions
exl-id: 6f0d9d79-cf40-4de3-9d9f-9b1bc57f97b6
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 84%

---

# Días desde la última compra

La dimensión [Días transcurridos desde la última compra](overview.md) mide la cantidad de tiempo transcurrido entre la visita actual del visitante y su compra más reciente en ese momento. Esta dimensión ayuda a comprender el comportamiento de los visitantes tras comprar algo en el sitio.

Los visitantes que nunca han comprado algo no se incluyen en esta dimensión. Además, tampoco se incluyen las visitas activadas antes de la primera compra de un visitante. Solo se incluyen las visitas después de la primera compra del visitante.

## Rellene esta dimensión con datos

Adobe rellena automáticamente esta dimensión en función del evento [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) de la implementación. Si implementa el evento `purchase` en el sitio, esta dimensión siempre funciona.

## Elementos de dimensión

Los elementos de dimensión incluyen el número de días entre la compra más reciente de un visitante y la visita actual. Cada número de días es un elemento de dimensión independiente: “Mismo día” se produce cuando la compra más reciente de un visitante y la visita actual se produjeron el mismo día.

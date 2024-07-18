---
title: Días antes de la primera compra
description: Número de días entre la primera visita de un visitante y la primera compra.
feature: Dimensions
exl-id: 651f9d55-49b9-402a-b7c7-ba4fba62c695
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 83%

---

# Días antes de la primera compra

La [dimensión](overview.md) &quot;Días antes de la primera compra&quot; indica la cantidad de días que transcurren entre la primera vez que un visitante llega al sitio y el momento en el que realiza una compra. Por ejemplo, si un visitante realiza una compra un día después de la primera visita, cualquier visita o evento posterior pertenece al elemento de dimensión “1 día”.

Una vez que un visitante realiza su primera compra, pertenece al mismo elemento de dimensión durante el resto de la duración de la cookie del visitante.

## Rellene esta dimensión con datos

Adobe rellena automáticamente esta dimensión en función del evento [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) de la implementación. Si implementa el evento `purchase` en el sitio, esta dimensión siempre funciona.

## Elementos de dimensión

Los elementos de dimensión incluyen la cantidad de días entre la primera visita de un visitante a su sitio y la primera compra. Cada número de días es un elemento de dimensión independiente, con “Mismo día” en el que se produce la primera visita de un visitante y su primera compra se produjeron el mismo día.

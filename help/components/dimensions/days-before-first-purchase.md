---
title: Días antes de la primera compra
description: Número de días entre la primera visita de un visitante y la primera compra.
feature: Dimensions
exl-id: 651f9d55-49b9-402a-b7c7-ba4fba62c695
TQID: https://experienceleague.adobe.com/fA8CgahXKwJfiynK-I8yuD-byaIyFPkaii3FzkrrPoI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
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
source-wordcount: 174
ht-degree: 83%

---

# Días antes de la primera compra

La [dimensión](overview.md) &quot;Días antes de la primera compra&quot; indica la cantidad de días que transcurren entre la primera vez que un visitante llega al sitio y el momento en el que realiza una compra. Por ejemplo, si un visitante realiza una compra un día después de la primera visita, cualquier visita o evento posterior pertenece al elemento de dimensión “1 día”.

Una vez que un visitante realiza su primera compra, pertenece al mismo elemento de dimensión durante el resto de la duración de la cookie del visitante.

## Rellene esta dimensión con datos

Adobe rellena automáticamente esta dimensión en función del evento [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) de la implementación. Si implementa el evento `purchase` en el sitio, esta dimensión siempre funciona.

## Elementos de dimensión

Los elementos de dimensión incluyen la cantidad de días entre la primera visita de un visitante a su sitio y la primera compra. Cada número de días es un elemento de dimensión independiente, con “Mismo día” en el que se produce la primera visita de un visitante y su primera compra se produjeron el mismo día.

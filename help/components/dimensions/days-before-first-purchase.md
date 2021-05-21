---
title: Días antes de la primera compra
description: Número de días entre la primera visita de un visitante y la primera compra.
exl-id: 651f9d55-49b9-402a-b7c7-ba4fba62c695
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '173'
ht-degree: 100%

---

# Días antes de la primera compra

La dimensión “Días antes de la primera compra” informa de la cantidad de días que transcurren entre la primera vez que los visitantes llegan al sitio y el momento en el que realizan la primera compra. Por ejemplo, si un visitante realiza una compra un día después de la primera visita, cualquier visita o evento posterior pertenece al elemento de dimensión “1 día”.

Una vez que un visitante realiza su primera compra, pertenece al mismo elemento de dimensión durante el resto de la duración de la cookie del visitante.

## Rellene esta dimensión con datos

Adobe rellena automáticamente esta dimensión en función del evento [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) de la implementación. Si implementa el evento `purchase` en el sitio, esta dimensión siempre funciona.

## Elementos de dimensión

Los elementos de dimensión incluyen la cantidad de días entre la primera visita de un visitante a su sitio y la primera compra. Cada número de días es un elemento de dimensión independiente, con “Mismo día” en el que se produce la primera visita de un visitante y su primera compra se produjeron el mismo día.

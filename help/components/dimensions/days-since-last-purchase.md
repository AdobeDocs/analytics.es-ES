---
title: Días transcurridos desde la última compra
description: Número de días entre la visita actual y la última compra que realizó.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 0%

---


# Días transcurridos desde la última compra

La dimensión &#39;Días transcurridos desde la última compra&#39; mide la cantidad de tiempo transcurrido entre la visita actual del visitante y la compra más reciente en ese momento. Esta dimensión ayuda a comprender los visitantes de comportamiento que se producen tras comprar algo en el sitio.

Los Visitantes que nunca han comprado algo no se incluyen en esta dimensión. Además, tampoco se incluyen las visitas activadas antes de la primera compra de un visitante. Solo se incluyen las visitas después de la primera compra del visitante.

## Rellenar esta dimensión con datos

Adobe rellena automáticamente esta dimensión en función del [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) evento de la implementación. Si implementa el `purchase` evento en el sitio, esta dimensión siempre funciona.

## Elementos de dimensión

Los elementos de dimensión incluyen el número de días entre la compra más reciente de un visitante y la visita individual actual. Cada número de días es un elemento de dimensión independiente, con &quot;Mismo día&quot; en el que se produce la compra más reciente de un visitante y la visita actual se produce el mismo día.

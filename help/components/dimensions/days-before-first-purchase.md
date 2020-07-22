---
title: Días antes de la primera compra
description: Número de días entre la primera visita de un visitante y la primera compra.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 0%

---


# Días antes de la primera compra

La dimensión &#39;Días antes de la primera compra&#39; informa la cantidad de días que transcurren entre la primera vez que un visitante llega al sitio y el momento en que realiza una compra. Por ejemplo, si un visitante realiza una compra un día después de la primera visita, cualquier visita o evento posterior pertenece al elemento de dimensión &quot;1 día&quot;.

Una vez que un visitante realiza su primera compra, pertenece al mismo elemento de dimensión durante el resto de la duración de la cookie del visitante.

## Rellenar esta dimensión con datos

Adobe rellena automáticamente esta dimensión en función del [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) evento de la implementación. Si implementa el `purchase` evento en el sitio, esta dimensión siempre funciona.

## Elementos de dimensión

Los elementos de dimensión incluyen el número de días entre la primera visita de un visitante al sitio y la primera compra. Cada número de días es un elemento de dimensión independiente, con &quot;Mismo día&quot; en el que se produce la primera visita de un visitante y su primera compra se realizó el mismo día.

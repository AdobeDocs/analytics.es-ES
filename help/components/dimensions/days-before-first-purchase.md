---
title: Días antes de la primera compra
description: Número de días entre la primera visita de un visitante y la primera compra.
translation-type: tm+mt
source-git-commit: a8dc233e962a49674a30ff3c9f0b5d0d45b09f24
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 0%

---


# Días antes de la primera compra

La dimensión &#39;Días antes de la primera compra&#39; informa la cantidad de días que transcurren entre la primera vez que un visitante llega al sitio y el momento en que realiza una compra. Por ejemplo, si un visitante realiza una compra un día después de la primera visita, cualquier visita o evento posterior pertenece al valor de dimensión &quot;1 día&quot;.

Una vez que un visitante realiza su primera compra, pertenece al mismo valor de dimensión durante el resto de la duración de la cookie del visitante.

## Rellenar esta dimensión con datos

Adobe rellena automáticamente esta dimensión en función del [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) evento de la implementación. Si implementa el `purchase` evento en el sitio, esta dimensión siempre funciona.

## Valores de dimensión

Los valores de dimensión incluyen el número de días entre la primera visita de un visitante al sitio y la primera compra. Cada número de días es un valor de dimensión independiente, con &quot;Mismo día&quot; en el que se produce la primera visita de un visitante y su primera compra en el mismo día.

---
title: Lealtad del cliente
description: Categorías basadas en el número de compras anteriores realizadas por un visitante.
feature: Dimensions
exl-id: 48ac1fdf-9a32-4bcc-8b23-bf58358a3470
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 88%

---

# Lealtad del cliente

La [dimensión](overview.md) &quot;Lealtad del cliente&quot; indica la cantidad de visitantes al sitio que han realizado 0 compras anteriores, 1 compra anterior, 2 compras anteriores o más de 3 compras anteriores. Esta dimensión es valiosa para comprender cómo el sitio afecta en el comportamiento de compra. También puede usar esta dimensión en un segmento para centrarse en visitantes que vuelven para realizar una compra, de modo que pueda estimular un comportamiento similar para nuevos visitantes.

## Rellene esta dimensión con datos

Adobe rellena automáticamente esta dimensión en función del evento [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) de la implementación. Si implementa el evento `purchase` en el sitio, esta dimensión siempre funciona.

## Elementos de dimensión

Los elementos de dimensión incluyen lo siguiente:

* **No es cliente**: En el momento de la visita, el visitante nunca había realizado una compra antes.
* **Clientes nuevos**: En el momento de la visita, el visitante realizó una sola compra antes.
* **Clientes que vuelven**: En el momento de la visita, el visitante realizó dos compras antes.
* **Clientes fieles**: En el momento de la visita, el visitante realizó tres o más compras antes.

Cuando un visitante realiza una compra (activa el evento `purchase`), esa visita y todas las visitas posteriores pasan al siguiente “bloque”. Por ejemplo, si un visitante compra un producto de su sitio por primera vez, pasa de “No es cliente” a “Clientes nuevos”, con el pedido atribuido a “Clientes nuevos”. El elemento de dimensión “No es cliente” no puede tener pedidos atribuidos a él.

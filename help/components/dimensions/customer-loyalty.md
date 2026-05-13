---
title: Lealtad del cliente
description: Categorías basadas en el número de compras anteriores realizadas por un visitante.
feature: Dimensions
exl-id: 48ac1fdf-9a32-4bcc-8b23-bf58358a3470
TQID: https://experienceleague.adobe.com/Essa0dflFlsqwtTQ4JdaSEOkX6T-zEYrQGhgXBWhfcI
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 246
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

---
title: Lealtad del cliente
description: Categorías basadas en el número de compras anteriores realizadas por un visitante.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 0%

---


# Lealtad del cliente

La dimensión &quot;Lealtad del cliente&quot; informa la cantidad de visitantes al sitio que han realizado 0 compras previas, 1 compra anterior, 2 compras anteriores o más de 3 compras previas. Esta dimensión es valiosa para comprender cómo el sitio afecta el comportamiento de compra. También puede usar esta dimensión en un segmento para centrarse en visitantes que regresan para realizar una compra, de modo que pueda estimular un comportamiento similar para nuevos visitantes.

## Rellenar esta dimensión con datos

Adobe rellena automáticamente esta dimensión en función del [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) evento de la implementación. Si implementa el `purchase` evento en el sitio, esta dimensión siempre funciona.

## Elementos de dimensión

Los elementos de dimensión incluyen lo siguiente:

* **No es cliente**: En el momento de la visita, el visitante nunca había realizado una compra antes.
* **Clientes** nuevos: En el momento de la visita, el visitante realizó una sola compra antes.
* **Clientes** de retorno: En el momento de la visita, el visitante realizó dos compras antes.
* **Clientes** fieles: En el momento de la visita, el visitante realizó tres o más compras antes.

Cuando un visitante realiza una compra (activa el `purchase` evento), esa visita y todas las visitas posteriores pasan al siguiente &quot;bloque&quot;. Por ejemplo: si un visitante compra un producto de su sitio por primera vez, pasa de &quot;No es cliente&quot; a &quot;Nuevos clientes&quot;, con el pedido atribuido a &quot;Nuevos clientes&quot;. El elemento de dimensión &quot;No es cliente&quot; no puede tener pedidos atribuidos a él.

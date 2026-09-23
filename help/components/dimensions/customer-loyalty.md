---
title: Lealtad del cliente
description: Categorías basadas en el número de compras anteriores realizadas por un visitante.
feature: Dimensions
exl-id: 48ac1fdf-9a32-4bcc-8b23-bf58358a3470
TQID: https://experienceleague.adobe.com/Essa0dflFlsqwtTQ4JdaSEOkX6T-zEYrQGhgXBWhfcI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 73%
---
# Lealtad del cliente

La [dimensión](overview.md) &quot;Lealtad del cliente&quot; indica la cantidad de visitantes al sitio que han realizado 0 compras anteriores, 1 compra anterior, 2 compras anteriores o más de 3 compras anteriores. Esta dimensión es valiosa para comprender cómo el sitio afecta en el comportamiento de compra. También puede usar esta dimensión en un segmento para centrarse en visitantes que vuelven para realizar una compra, de modo que pueda estimular un comportamiento similar para nuevos visitantes.

## Rellene esta dimensión con datos

Adobe calcula esta dimensión del lado del servidor a partir del historial de compras del visitante. No hay ninguna variable que establecer; depende del evento [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) que se esté implementando en el sitio.

| Propiedad | Valor |
| --- | --- |
| **variable de AppMeasurement** | Ninguno (calculado por Adobe) |
| **Campo Web SDK / XDM** | Ninguno (calculado por Adobe) |
| **Parámetro de consulta** | n/a |
| **etiqueta XML** | n/a |
| **Límite de bytes** | n/a |
| **Persistencia** | N/A |

## Elementos de dimensión

Los elementos de dimensión incluyen lo siguiente:

* **No es cliente**: En el momento del hit, el visitante nunca había realizado una compra antes.
* **Clientes nuevos**: En el momento del hit, el visitante realizó una sola compra antes.
* **Clientes que vuelven**: En el momento del hit, el visitante realizó dos compras antes.
* **Clientes fieles**: En el momento del hit, el visitante realizó tres o más compras antes.

Cuando un visitante realiza una compra (activa el evento `purchase`), ese hit y todos los hits posteriores pasan al siguiente “bloque”. Por ejemplo, si un visitante compra un producto de su sitio por primera vez, pasa de “No es cliente” a “Clientes nuevos”, con el pedido atribuido a “Clientes nuevos”. El elemento de dimensión “No es cliente” no puede tener pedidos atribuidos a él.

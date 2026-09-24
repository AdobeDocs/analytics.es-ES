---
title: Días desde la última compra
description: Número de días entre el hit actual y la última compra que realizaron.
feature: Dimensions
exl-id: 6f0d9d79-cf40-4de3-9d9f-9b1bc57f97b6
TQID: https://experienceleague.adobe.com/q86bc1bMRctUBe7dFEJaALsq0GjALFQQtKU9cRpRkoU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
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
source-wordcount: '207'
ht-degree: 64%
---
# Días desde la última compra

La dimensión [Días transcurridos desde la última compra](overview.md) mide la cantidad de tiempo transcurrido entre la visita actual del visitante y su compra más reciente en ese momento. Esta dimensión ayuda a comprender el comportamiento de los visitantes tras comprar algo en el sitio.

Los visitantes que nunca han comprado algo no se incluyen en esta dimensión. Además, tampoco se incluyen los hits activados antes de la primera compra de un visitante. Solo se incluyen los hits después de la primera compra del visitante.

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

Los elementos de dimensión incluyen el número de días entre la compra más reciente de un visitante y el hit actual. Cada número de días es un elemento de dimensión independiente: “Mismo día” se produce cuando la compra más reciente de un visitante y el hit actual se produjeron el mismo día.

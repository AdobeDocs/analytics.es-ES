---
title: Ocurrencias de productos Bot
description: La métrica "Ocurrencias de productos de bots" muestra el número de subvisitas de cadenas de producto que coincidieron con las reglas de bots y se excluyeron de los informes de Analytics.
feature: Metrics
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
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: 3ba8d2cce29a1965c85789c3fd0543c23533e3a8
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 5%
---
# Ocurrencias de productos Bot

La [métrica](overview.md) &quot;Ocurrencias de productos de bots&quot; muestra el número de visitas secundarias que coinciden con [reglas de bots](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md).

Dado que los informes de bots están separados del resto de los datos del grupo de informes, esta métrica solo funciona con las siguientes dimensiones:

* [Nombre de bot](../dimensions/bot-name.md)
* [Producto](../dimensions/product.md)
* Dimensiones basadas en el tiempo (por ejemplo, [Día](../dimensions/day.md), [Semana](../dimensions/week.md) o [Mes](../dimensions/month.md))

El uso de cualquier otra dimensión con esta métrica no devuelve datos.

## Cómo se calcula esta métrica

Adobe comprueba cada subvisita con la [cadena de producto](/help/implement/vars/page-vars/products.md) para ver si coincide con las reglas de bots que ha configurado su organización. Si una subvisita determinada coincide con una regla de bots, la subvisita se excluye de los informes y esta métrica aumenta en uno.

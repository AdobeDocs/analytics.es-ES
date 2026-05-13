---
title: Ocurrencias de bots
description: El número de visitas que coincidieron con las reglas de bots.
feature: Metrics
exl-id: 94cbbee4-8455-48b1-b804-534ed8fccdc9
TQID: https://experienceleague.adobe.com/LH7eQC-Z6Y3nku1QzI9Yn0N3MRwGA--5R-93lfadT1c
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 130
ht-degree: 9%

---

# Ocurrencias de bots

La [métrica](overview.md) &quot;Ocurrencias de bots&quot; muestra el número de visitas que coincidieron con [reglas de bots](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md).

Dado que los informes de bots están separados del resto de los datos del grupo de informes, esta métrica solo funciona con las siguientes dimensiones:

* [Nombre de bot](../dimensions/bot-name.md)
* [Página](../dimensions/page.md)
* Dimensiones basadas en el tiempo (por ejemplo, [Día](../dimensions/day.md), [Semana](../dimensions/week.md) o [Mes](../dimensions/month.md))

El uso de cualquier otra dimensión con esta métrica no devuelve datos.

## Cómo se calcula esta métrica

Adobe comprueba cada visita para ver si coincide con las reglas de bots que ha configurado su organización. Si una visita determinada coincide con una regla de bots, se excluye de la creación de informes y esta métrica aumenta en uno. Esta métrica incluye vistas de página ([`t()`](/help/implement/vars/functions/t-method.md)) y visitas de seguimiento de vínculos ([`tl()`](/help/implement/vars/functions/tl-method.md)), mientras que [Vistas de páginas de bots](bot-page-views.md) no incluyen visitas de seguimiento de vínculos.

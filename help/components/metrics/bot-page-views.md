---
title: Vistas de páginas de bots
description: Número de vistas de página que coinciden con las reglas de bots.
feature: Metrics
exl-id: d6699880-3faa-4df9-ad49-c7998f6ce45b
TQID: https://experienceleague.adobe.com/Y0r2fzF87dep4NsrbJGCC9OnqBHrZozCh2DovNc90KQ
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 125
ht-degree: 11%

---

# Vistas de páginas de bots

La [métrica](overview.md) &quot;Vistas de página de bots&quot; muestra el número de visitas de página que coinciden con [reglas de bots](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md).

Dado que los informes de bots están separados del resto de los datos del grupo de informes, esta métrica solo funciona con las siguientes dimensiones:

* [Nombre de bot](../dimensions/bot-name.md)
* [Página](../dimensions/page.md)
* Dimensiones basadas en el tiempo (por ejemplo, [Día](../dimensions/day.md), [Semana](../dimensions/week.md) o [Mes](../dimensions/month.md))

El uso de cualquier otra dimensión con esta métrica no devuelve datos.

## Cómo se calcula esta métrica

Adobe comprueba todas las visitas individuales de las páginas para ver si coinciden con las reglas de bots que ha configurado su organización. Si una visita determinada coincide con una regla de bots, la visita a la página se excluye de los informes y esta métrica aumenta en uno. Esta métrica no incluye las visitas de seguimiento de vínculos ([`tl()`](/help/implement/vars/functions/tl-method.md)).

---
title: Vistas de páginas de bots
description: Número de vistas de página que coinciden con las reglas de bots.
feature: Metrics
exl-id: d6699880-3faa-4df9-ad49-c7998f6ce45b
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '124'
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

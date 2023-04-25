---
title: Vistas de páginas de bots
description: Número de vistas de página que coinciden con las reglas de bots.
source-git-commit: 61a0292bf2f8ff22b414c2e91da476c1da69d163
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 4%

---

# Vistas de páginas de bots

La métrica &quot;Vistas de página de bots&quot; muestra el número de visitas individuales de página que coincidieron con [Reglas de bots](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md).

Dado que los informes de bots están separados del resto de los datos del grupo de informes, esta métrica solo funciona con las siguientes dimensiones:

* [Nombre de bots](../dimensions/bot-name.md)
* [Página](../dimensions/page.md)
* Dimensiones basadas en el tiempo (por ejemplo, [Día](../dimensions/day.md), [Semana](../dimensions/week.md)o [Mes](../dimensions/month.md))

El uso de cualquier otra dimensión con esta métrica no devuelve datos.

## Cálculo de esta métrica

Adobe comprueba cada visita a una página para ver si coincide con las reglas de bots configuradas por su organización. Si una visita determinada coincide con una regla de bots, la visita a la página se excluye de los informes y esta métrica aumenta en uno. Esta métrica no incluye las visitas de seguimiento de vínculos ([`tl()`](/help/implement/vars/functions/tl-method.md)).

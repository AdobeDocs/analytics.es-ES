---
title: Ocurrencias de bots
description: Número de visitas que coinciden con las reglas de bots.
exl-id: 3b6cbe94-98db-4ba4-aab2-ce59cdbc420a
hide: true
hidefromtoc: true
source-git-commit: 017559d2b909deb4bf87fb5fe41db8250f2ca2ac
workflow-type: tm+mt
source-wordcount: '129'
ht-degree: 4%

---

# Ocurrencias de bots

La métrica &quot;Ocurrencias de bots&quot; muestra el número de visitas coincidentes [Reglas de bots](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md).

Dado que los informes de bots están separados del resto de los datos del grupo de informes, esta métrica solo funciona con las siguientes dimensiones:

* [Nombre de bots](../dimensions/bot-name.md)
* [Página](../dimensions/page.md)
* Dimensiones basadas en el tiempo (por ejemplo, [Día](../dimensions/day.md), [Semana](../dimensions/week.md)o [Mes](../dimensions/month.md))

El uso de cualquier otra dimensión con esta métrica no devuelve datos.

## Cálculo de esta métrica

Adobe comprueba cada visita para ver si coincide con las reglas de bots configuradas por su organización. Si una visita determinada coincide con una regla de bots, la visita se excluye de los informes y esta métrica aumenta en uno. Esta métrica incluye ambas vistas de página ([`t()`](/help/implement/vars/functions/t-method.md)) y las visitas de seguimiento de vínculos ([`tl()`](/help/implement/vars/functions/tl-method.md)), que [Vistas de páginas de bots](bot-page-views.md) no incluya las visitas de seguimiento de vínculos.

---
title: Ocurrencias de bots
description: El número de visitas que coincidieron con las reglas de bots.
feature: Metrics
exl-id: 94cbbee4-8455-48b1-b804-534ed8fccdc9
source-git-commit: 9f70dbeb9dfe54897915213480f05cbdfaf920ef
workflow-type: tm+mt
source-wordcount: '129'
ht-degree: 9%

---

# Ocurrencias de bots

La [métrica](overview.md) &quot;Ocurrencias de bots&quot; muestra el número de visitas que coincidieron con [reglas de bots](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md).

Dado que los informes de bots están separados del resto de los datos del grupo de informes, esta métrica solo funciona con las siguientes dimensiones:

* [Nombre de bot](../dimensions/bot-name.md)
* [Página](../dimensions/page.md)
* Dimensiones basadas en el tiempo (por ejemplo, [Día](../dimensions/day.md), [Semana](../dimensions/week.md) o [Mes](../dimensions/month.md))

El uso de cualquier otra dimensión con esta métrica no devuelve datos.

## Cómo se calcula esta métrica

El Adobe comprueba cada visita para ver si coincide con las reglas de bots que ha configurado su organización. Si una visita determinada coincide con una regla de bots, se excluye de la creación de informes y esta métrica aumenta en uno. Esta métrica incluye vistas de página ([`t()`](/help/implement/vars/functions/t-method.md)) y visitas de seguimiento de vínculos ([`tl()`](/help/implement/vars/functions/tl-method.md)), mientras que [Vistas de páginas de bots](bot-page-views.md) no incluyen visitas de seguimiento de vínculos.

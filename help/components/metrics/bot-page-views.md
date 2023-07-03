---
title: Vistas de página de bots
description: Número de vistas de página que coinciden con las reglas de bots.
feature: Metrics
exl-id: 9b1efcb1-10ca-40fb-8f20-e6da105366d9
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Vistas de página de bots

La métrica &quot;Vistas de página de bots&quot; muestra el número de visitas individuales de página que coincidieron [Reglas de bots](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md).

Dado que los informes de bots están separados del resto de los datos del grupo de informes, esta métrica solo funciona con las siguientes dimensiones:

* [Nombre de bot](../dimensions/bot-name.md)
* [Página](../dimensions/page.md)
* Dimensiones basadas en el tiempo (por ejemplo, [Día](../dimensions/day.md), [Semana](../dimensions/week.md), o [Mes](../dimensions/month.md))

El uso de cualquier otra dimensión con esta métrica no devuelve datos.

## Cálculo de esta métrica

El Adobe comprueba cada visita individual a la página para ver si coincide con las reglas de bots que ha configurado su organización. Si una visita determinada coincide con una regla de bots, la visita a la página se excluye de los informes y esta métrica aumenta en uno. Esta métrica no incluye las visitas de seguimiento de vínculos ([`tl()`](/help/implement/vars/functions/tl-method.md)).

---
title: Ocurrencias de bots
description: El número de visitas que coincidieron con las reglas de bots.
feature: Metrics
exl-id: 3b6cbe94-98db-4ba4-aab2-ce59cdbc420a
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Ocurrencias de bots

La métrica &quot;Ocurrencias de bots&quot; muestra el número de visitas que coincidieron [Reglas de bots](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md).

Dado que los informes de bots están separados del resto de los datos del grupo de informes, esta métrica solo funciona con las siguientes dimensiones:

* [Nombre de bot](../dimensions/bot-name.md)
* [Página](../dimensions/page.md)
* Dimensiones basadas en el tiempo (por ejemplo, [Día](../dimensions/day.md), [Semana](../dimensions/week.md), o [Mes](../dimensions/month.md))

El uso de cualquier otra dimensión con esta métrica no devuelve datos.

## Cálculo de esta métrica

El Adobe comprueba cada visita para ver si coincide con las reglas de bots que ha configurado su organización. Si una visita determinada coincide con una regla de bots, se excluye de la creación de informes y esta métrica aumenta en uno. Esta métrica incluye ambas vistas de página ([`t()`](/help/implement/vars/functions/t-method.md)) y visitas de seguimiento de vínculos ([`tl()`](/help/implement/vars/functions/tl-method.md)), mientras que [Vistas de página de bots](bot-page-views.md) no incluya las visitas de seguimiento de vínculos.

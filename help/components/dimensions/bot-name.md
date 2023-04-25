---
title: Nombre de bots
description: Nombre del bot que coincide con las reglas de Bot.
source-git-commit: d7d9bbf9bf43509eb756408f772be870c3854aa5
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 3%

---

# Nombre de bots

La dimensión &quot;Nombre de bots&quot; muestra los nombres de los bots detectados mediante [Reglas de bots](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md). Estas reglas pueden ser reglas IAB predeterminadas o reglas de bots personalizadas que su organización configure. Resulta útil cuando desea obtener más información sobre qué bots están visitando el sitio o qué bots generan la mayor cantidad de tráfico.

Visitas que coinciden [!UICONTROL Reglas de bots] se filtran automáticamente fuera de todos los informes de Analytics, con excepción de esta dimensión, [Ocurrencias de bots](../metrics/bot-occurrences.md)y [Vistas de páginas de bots](../metrics/bot-page-views.md). Puede utilizar esta dimensión y estas dos métricas para ver qué datos de bots se excluyen del resto de los informes.

Dado que los informes de bots están separados del resto de los datos del grupo de informes, esta dimensión solo admite las siguientes dimensiones y métricas:

* [Página](page.md)
* Dimensiones basadas en el tiempo (por ejemplo, [Día](day.md), [Semana](week.md)o [Mes](month.md))
* [Ocurrencias de bots](../metrics/bot-occurrences.md)
* [Vistas de páginas de bots](../metrics/bot-page-views.md)

El uso de cualquier otra dimensión o métrica con esta dimensión no devuelve datos.

## Rellene esta dimensión con datos

Si ha activado [Reglas de bots](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md), esta dimensión recopila datos automáticamente. Si aún no está habilitado [!UICONTROL Reglas de bots], esta dimensión no aparece en Analysis Workspace.

## Elementos de dimensión

Cada elemento de dimensión enumera el nombre del bot que coincide con los criterios de reglas de bots personalizados o IAB.

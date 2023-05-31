---
title: Nombre de bot
description: El nombre del bot que coincidió con las reglas del bot.
exl-id: 668c1dce-c603-477a-9df7-dacb649bbf63
source-git-commit: 5ba12c243a8013c52b487d048c54461ebdf7bd85
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 3%

---

# Nombre de bot

La dimensión &quot;Nombre de bot&quot; muestra los nombres de bots detectados mediante [Reglas de bots](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md). Estas reglas pueden ser reglas IAB predeterminadas o reglas de bots personalizadas que configure su organización. Resulta útil en los casos en los que desea obtener más información sobre los bots que visitan el sitio o sobre los bots que generan la mayor cantidad de tráfico.

Visitas que coinciden [!UICONTROL Reglas de bots] se filtran automáticamente de todos los informes de Analytics, con excepción de esta dimensión, [Ocurrencias de bots](../metrics/bot-occurrences.md), y [Vistas de página de bots](../metrics/bot-page-views.md). Puede utilizar esta dimensión y estas dos métricas para ver qué datos de bots se excluyen del resto de los informes.

Dado que los informes de bots están separados del resto de los datos del grupo de informes, solo se admiten las siguientes dimensiones y métricas con esta dimensión:

* [Página](page.md)
* Dimensiones basadas en el tiempo (por ejemplo, [Día](day.md), [Semana](week.md), o [Mes](month.md))
* [Ocurrencias de bots](../metrics/bot-occurrences.md)
* [Vistas de página de bots](../metrics/bot-page-views.md)

El uso de cualquier otra dimensión o métrica con esta dimensión no devuelve datos.

## Rellene esta dimensión con datos

Si ha activado [Reglas de bots](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md), esta dimensión recopila datos automáticamente. Si aún no lo ha activado [!UICONTROL Reglas de bots]Sin embargo, esta dimensión no aparece en Analysis Workspace.

## Elementos de dimensión

Cada elemento de dimensión enumera el nombre del bot que coincidió con los criterios de la regla de bots IAB o personalizada.

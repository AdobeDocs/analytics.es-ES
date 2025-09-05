---
title: Nombre de bot
description: El nombre del bot que coincidió con las reglas del bot.
exl-id: 034dce46-e83c-4053-a062-3998231f8d6b
feature: Dimensions
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 7%

---

# Nombre de bot

El &quot;nombre de bot&quot; [dimension](overview.md) muestra los nombres de bots detectados mediante [reglas de bots](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md). Estas reglas pueden ser reglas IAB predeterminadas o reglas de bots personalizadas que configure su organización. Resulta útil en los casos en los que desea obtener más información sobre los bots que visitan el sitio o sobre los bots que generan la mayor cantidad de tráfico.

Las visitas que coinciden con [!UICONTROL reglas de bots] se filtran automáticamente de todos los informes de Analytics, con excepción de esta dimensión, [ocurrencias de bots](../metrics/bot-occurrences.md) y [vistas de páginas de bots](../metrics/bot-page-views.md). Puede utilizar esta dimensión y estas dos métricas para ver qué datos de bots se excluyen del resto de los informes.

Dado que los informes de bots están separados del resto de los datos del grupo de informes, solo se admiten las siguientes dimensiones y métricas con esta dimensión:

* [Página](page.md)
* Dimensiones basadas en el tiempo (por ejemplo, [Día](day.md), [Semana](week.md) o [Mes](month.md))
* [Ocurrencias de bots](../metrics/bot-occurrences.md)
* [Vistas de páginas de bots](../metrics/bot-page-views.md)

El uso de cualquier otra dimensión o métrica con esta dimensión no devuelve datos.

## Rellene esta dimensión con datos

Si ha habilitado [reglas de bots](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md), esta dimensión recopila datos automáticamente. Si aún no ha habilitado [!UICONTROL reglas de bots], esta dimensión no aparecerá en Analysis Workspace.

## Elementos de dimensión

Cada elemento de dimensión enumera el nombre del bot que coincidió con los criterios de la regla de bots IAB o personalizada.

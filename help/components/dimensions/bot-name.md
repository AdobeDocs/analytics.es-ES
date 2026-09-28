---
title: Nombre de bot
description: El nombre del bot que coincidió con las reglas del bot.
exl-id: 034dce46-e83c-4053-a062-3998231f8d6b
feature: Dimensions
TQID: 'https://experienceleague.adobe.com/lJn65s1JtcJf7WobPEeouvwlk7G5qd8XtgxvGLY-zu8'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 11%
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

| Propiedad | Valor |
| --- | --- |
| **variable de AppMeasurement** | Ninguno (derivado por reglas de detección de bots) |
| **Campo Web SDK / XDM** | Ninguno (derivado por reglas de detección de bots) |
| **Parámetro de consulta** | n/a |
| **etiqueta XML** | n/a |
| **Límite de bytes** | n/a |
| **Persistencia** | N/A |

## Elementos de dimensión

Cada elemento de dimensión enumera el nombre del bot que coincidió con los criterios de la regla de bots IAB o personalizada.

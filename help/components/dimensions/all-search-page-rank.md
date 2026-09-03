---
title: Clasificación de todas las páginas de búsqueda
description: Determinar en qué página de un motor de búsqueda hizo clic un visitante en el sitio.
feature: Dimensions
exl-id: 58ce54c3-cc45-4e84-a14d-5fec0b70f50f
TQID: https://experienceleague.adobe.com/U7WgtQDXInyD1gXeBntncC9Fao1Rdc9W4AHFgx07T4A
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 146
ht-degree: 85%

---

# Clasificación de todas las páginas de búsqueda

La &quot;Clasificación de todas las páginas de búsqueda&quot; [dimension](overview.md) proporciona a insight en qué página de resultados de búsqueda hizo clic un visitante en su sitio. Por ejemplo, si su sitio aparece en la segunda página de los resultados de búsqueda de un motor de búsqueda, el elemento de dimensión para esta variable es “Página de búsqueda 2”.

## Rellene esta dimensión con datos

Para que esta dimensión funcione solo es necesario que el grupo de informes tenga correctamente configurados los [Filtros URL internos](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md). AppMeasurement rellena automáticamente esta dimensión sin ningún cambio en el código de implementación.

## Elementos de dimensión

Si un visitante hace clic en su sitio desde un motor de búsqueda, el valor de esta dimensión es “Página de búsqueda” seguida del número de página en el que hizo clic. Si una visita no se origina desde un motor de búsqueda, el valor de esta dimensión es “No especificado”.

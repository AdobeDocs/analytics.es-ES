---
title: Clasificación de todas las páginas de búsqueda
description: Determinar en qué página de un motor de búsqueda hizo clic un visitante en el sitio.
feature: Dimensions
exl-id: 58ce54c3-cc45-4e84-a14d-5fec0b70f50f
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 85%

---

# Clasificación de todas las páginas de búsqueda

La &quot;Clasificación de todas las páginas de búsqueda&quot; [dimension](overview.md) proporciona a insight en qué página de resultados de búsqueda hizo clic un visitante en su sitio. Por ejemplo, si su sitio aparece en la segunda página de los resultados de búsqueda de un motor de búsqueda, el elemento de dimensión para esta variable es “Página de búsqueda 2”.

## Rellene esta dimensión con datos

Para que esta dimensión funcione solo es necesario que el grupo de informes tenga correctamente configurados los [Filtros URL internos](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md). AppMeasurement rellena automáticamente esta dimensión sin ningún cambio en el código de implementación.

## Elementos de dimensión

Si un visitante hace clic en su sitio desde un motor de búsqueda, el valor de esta dimensión es “Página de búsqueda” seguida del número de página en el que hizo clic. Si una visita no se origina desde un motor de búsqueda, el valor de esta dimensión es “No especificado”.

---
title: Clasificación de todas las páginas de búsqueda
description: Determinar en qué página de un motor de búsqueda hizo clic un visitante en el sitio.
exl-id: 58ce54c3-cc45-4e84-a14d-5fec0b70f50f
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '145'
ht-degree: 100%

---

# Clasificación de todas las páginas de búsqueda

La dimensión “Clasificación de todas las páginas de búsqueda” proporciona una perspectiva sobre la página de resultados de búsqueda en la que un visitante hizo clic en el sitio. Por ejemplo, si su sitio aparece en la segunda página de los resultados de búsqueda de un motor de búsqueda, el elemento de dimensión para esta variable es “Página de búsqueda 2”.

## Rellene esta dimensión con datos

Para que esta dimensión funcione solo es necesario que el grupo de informes tenga correctamente configurados los [Filtros URL internos](/help/admin/admin/internal-url-filter-admin.md). AppMeasurement rellena automáticamente esta dimensión sin ningún cambio en el código de implementación.

## Elementos de dimensión

Si un visitante hace clic en su sitio desde un motor de búsqueda, el valor de esta dimensión es “Página de búsqueda” seguida del número de página en el que hizo clic. Si una visita no se origina desde un motor de búsqueda, el valor de esta dimensión es “No especificado”.

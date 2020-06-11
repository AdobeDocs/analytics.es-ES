---
title: Clasificación de todas las páginas de búsqueda
description: Determinar en qué página de un motor de búsqueda hizo clic un visitante en el sitio.
translation-type: tm+mt
source-git-commit: 4a7b3a00bdbf557c219de530e3e692c2b2db4a84
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 0%

---


# Clasificación de todas las páginas de búsqueda

La dimensión &#39;Clasificación de todas las páginas de búsqueda&#39; proporciona una perspectiva sobre la página de resultados de búsqueda en la que se hizo clic un visitante en el sitio. Por ejemplo: si su sitio aparece en la segunda página de los resultados de búsqueda de un motor de búsqueda, el valor de dimensión de esta variable es &quot;Página de búsqueda 2&quot;.

## Rellenar esta dimensión con datos

Para que esta dimensión funcione solo es necesario que el grupo de informes tenga correctamente configurados los filtros [de URL](/help/admin/admin/internal-url-filter-admin.md) internos. AppMeasurement rellena automáticamente esta dimensión sin ningún cambio en el código de implementación.

## Valores de dimensión

Si un visitante hace clic en su sitio desde un motor de búsqueda, el valor de esta dimensión es &quot;Página de búsqueda&quot; seguida del número de página en el que hizo clic. Si una visita no se origina desde un motor de búsqueda, el valor de esta dimensión es &quot;No especificado&quot;.

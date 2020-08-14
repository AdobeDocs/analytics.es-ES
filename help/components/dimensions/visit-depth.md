---
title: Profundidad de la visita
description: Dimensión basada en visitas que indica la profundidad de la visita.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 57%

---


# Profundidad de la visita

La dimensión “Profundidad de la visita” indica la cantidad de vistas de página que vio el visitante en toda la visita. Visit depth increases only if the hit is a page view, and the [Page](page.md) dimension is not the same as the last page view&#39;s dimension item. Es una dimensión basada en visitas, lo que significa que contiene el mismo valor para toda la visita. Esta variable se establece para todas las visitas de una visita después de que la visita finalice.

## Rellene esta dimensión con datos

Esta dimensión funciona de forma predeterminada para todas las implementaciones. Si un grupo de informes contiene datos, esta dimensión funciona.

## Elementos de Dimension

Dimension items include the string `"Pages per visit"` followed by a number representing the number of pages in the visit. The dimension item of `"Pages per visit: 1"` represents a single-page visit, while the dimension item `"Pages per visit: 8"` represents a visit with 8 page views (and any number of link tracking calls).

## Comparación con la profundidad de la visita

Consulte [Profundidad de la visita](hit-depth.md) para ver una comparación entre dimensiones.
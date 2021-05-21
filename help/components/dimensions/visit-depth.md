---
title: Profundidad de la visita
description: Dimensión basada en visitas que indica la profundidad de la visita.
exl-id: 3e9aca08-2255-46ca-9949-77334ee7120e
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '166'
ht-degree: 100%

---

# Profundidad de la visita

La dimensión “Profundidad de la visita” indica la cantidad de vistas de página que vio el visitante en toda la visita. La profundidad de la visita solo aumenta si la visita es una vista de página y la dimensión [Página](page.md) no es la misma que el elemento de dimensión de la última vista de página. Es una dimensión basada en visitas, lo que significa que contiene el mismo valor para toda la visita. Esta variable se establece para todas las visitas de una visita después de que la visita finalice.

## Rellene esta dimensión con datos

Esta dimensión funciona de forma predeterminada para todas las implementaciones. Si un grupo de informes contiene datos, esta dimensión funciona.

## Elementos de dimensión

Los elementos de dimensión incluyen la cadena `"Pages per visit"` seguida de un número que representa el número de páginas en la visita. El elemento de dimensión de `"Pages per visit: 1"` representa una visita de una sola página, mientras que el elemento de dimensión `"Pages per visit: 8"` representa una visita con 8 vistas de página (y cualquier número de llamadas de seguimiento de vínculos).

## Comparación con la profundidad de la visita

Consulte [Profundidad de la visita](hit-depth.md) para ver una comparación entre dimensiones.

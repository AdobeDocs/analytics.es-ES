---
title: Profundidad de la visita
description: Dimensión basada en visitas que indica la profundidad de la visita.
feature: Dimensions
exl-id: 3e9aca08-2255-46ca-9949-77334ee7120e
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '167'
ht-degree: 89%

---

# Profundidad de la visita

La &quot;Profundidad de la visita&quot; [dimension](overview.md) indica la cantidad de vistas de página que vio el visitante en toda la visita. La profundidad de la visita solo aumenta si la visita es una vista de página y la dimensión [Página](page.md) no es la misma que el elemento de dimensión de la última vista de página. Es una dimensión basada en visitas, lo que significa que contiene el mismo valor para toda la visita. Esta variable se establece para todas las visitas de una visita después de que la visita finalice.

## Rellene esta dimensión con datos

Esta dimensión funciona de forma predeterminada para todas las implementaciones. Si un grupo de informes contiene datos, esta dimensión funciona.

## Elementos de dimensión

Los elementos de dimensión incluyen la cadena `"Pages per visit"` seguida de un número que representa el número de páginas en la visita. El elemento de dimensión de `"Pages per visit: 1"` representa una visita de una sola página, mientras que el elemento de dimensión `"Pages per visit: 8"` representa una visita con 8 vistas de página (y cualquier número de llamadas de seguimiento de vínculos).

## Comparación con la profundidad de la visita

Consulte [Profundidad de la visita](hit-depth.md) para ver una comparación entre dimensiones.

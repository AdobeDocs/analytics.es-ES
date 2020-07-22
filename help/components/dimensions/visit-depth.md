---
title: Profundidad de la visita
description: Dimensión basada en visitas que informa la profundidad de la visita.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 0%

---


# Profundidad de la visita

La dimensión &#39;Profundidad de la visita&#39; informa la cantidad de vistas de página que vio el visitante en toda la visita. La profundidad de la visita solo aumenta si la visita es una vista de página y la dimensión [Página](page.md) no es la misma que el elemento de dimensión de la última vista de página. Es una dimensión basada en visitas, lo que significa que contiene el mismo valor para toda la visita. Esta variable se establece para todas las visitas de una visita después de que la visita finalice.

## Rellenar esta dimensión con datos

Esta dimensión funciona de forma predeterminada para todas las implementaciones. Si un grupo de informes contiene datos, esta dimensión funciona.

## Elementos de dimensión

Los elementos de dimensión incluyen la cadena `"Pages per visit"` seguida de un número que representa el número de páginas en la visita. El elemento de dimensión de `"Pages per visit: 1"` representa una visita de una sola página, mientras que el elemento de dimensión `"Pages per visit: 8"` representa una visita con 8 vistas de página (y cualquier número de llamadas de seguimiento de vínculos).

## Comparación con la profundidad de la visita

Consulte [Profundidad](hit-depth.md) de acierto para ver una comparación entre dimensiones.
---
title: Tiempo empleado por visitante (segundos)
description: null
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 6%

---


# Tiempo empleado por visitante (segundos)

La métrica &#39;Tiempo empleado por visitante (segundos)&#39; muestra la cantidad promedio de tiempo que los visitantes interactúan con un elemento de dimensión determinado durante toda la vida del visitante.

Esta métrica no está disponible en la Data warehouse debido a que su arquitectura de procesamiento es diferente.

## Cómo se calcula esta métrica

Esta métrica utiliza la fórmula [`Total seconds spent`](total-seconds-spent.md)`divided by` [`Unique visitors`](unique-visitors.md).

## Porcentajes superiores al 100%

Esta métrica contiene con frecuencia porcentajes superiores al 100 %. El denominador es el tiempo empleado por visitante de toda la dimensión y el numerador es el tiempo empleado por cada visitante en el elemento de dimensión. Si el tiempo empleado por visitante de toda la dimensión es inferior al tiempo empleado por cada elemento de dimensión determinado por visitante, verá porcentajes superiores al 100 %. Al ordenar los informes de clasificación por esta métrica, se muestra el tiempo de anomalía empleado por los valores de visitante, lo que generalmente no es valioso. Adobe recomienda ordenar según otra métrica, como [Visitas](visits.md), en los informes de clasificación.

Consulte [Información general](time-spent.md) sobre el tiempo empleado para obtener información más general sobre el tiempo empleado.

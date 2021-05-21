---
title: Tiempo empleado por visitante (segundos)
description: La métrica Tiempo empleado por visitante (segundos) muestra la cantidad de tiempo promedio que los visitantes interactúan con un valor de dimensión determinado durante toda la vida útil del visitante.
exl-id: 80f38bab-2ee1-4d0d-ba53-9b2c7c85e481
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '179'
ht-degree: 100%

---

# Tiempo empleado por visitante (segundos)

La métrica [!UICONTROL Tiempo empleado por visitante (segundos)] muestra la cantidad de tiempo promedio que los visitantes interactúan con un valor de dimensión determinado durante toda la vida útil del visitante.

Esta métrica no está disponible en Data Warehouse debido a que su arquitectura de procesamiento es diferente.

## Cálculo de esta métrica

Esta métrica utiliza la fórmula [`Total seconds spent`](total-seconds-spent.md) `divided by` [`Unique visitors`](unique-visitors.md).

## Porcentajes superiores al 100%

Esta métrica contiene con frecuencia porcentajes superiores al 100%. El denominador es el tiempo empleado por visitante de toda la dimensión y el numerador es el tiempo empleado por visitante en el valor de la dimensión. Si el tiempo empleado por visitante de toda la dimensión es menor que el tiempo empleado por visitante de un valor de dimensión determinado, verá porcentajes superiores al 100 %. Al ordenar los informes de clasificación por esta métrica, se muestra el tiempo de anomalía empleado por los valores de visitante, lo que generalmente no es muy útil. Adobe recomienda ordenar según otra métrica, como [Visitas](visits.md), en los informes de clasificación.

Consulte [Información general sobre el tiempo empleado](time-spent.md) para saber más detalles sobre el tiempo invertido.

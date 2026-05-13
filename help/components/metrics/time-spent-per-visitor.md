---
title: Tiempo empleado por visitante (segundos)
description: La métrica Tiempo empleado por visitante (segundos) muestra la cantidad de tiempo promedio que los visitantes interactúan con un valor de dimensión determinado durante toda la vida útil del visitante.
feature: Metrics
exl-id: 80f38bab-2ee1-4d0d-ba53-9b2c7c85e481
TQID: https://experienceleague.adobe.com/NFmA2Q80h2WOTRwoJ882aFMG60y2HKngR0Ew0qnxb8o
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 182
ht-degree: 85%

---

# Tiempo empleado por visitante (segundos)

La [!UICONTROL métrica de tiempo empleado por visitante (segundos)] [muestra la cantidad de tiempo promedio que los visitantes interactúan con un elemento de dimensión determinado durante toda la vida útil del visitante.](overview.md)

Esta métrica no está disponible en Data Warehouse debido a que su arquitectura de procesamiento es diferente.

## Cálculo de esta métrica

Esta métrica utiliza la fórmula [`Total seconds spent`](total-seconds-spent.md) `divided by` [`Unique visitors`](unique-visitors.md).

## Porcentajes superiores al 100%

Esta métrica contiene con frecuencia porcentajes superiores al 100%. El denominador es el tiempo empleado por visitante de toda la dimensión y el numerador es el tiempo empleado por visitante en el valor de la dimensión. Si el tiempo empleado por visitante de toda la dimensión es menor que el tiempo empleado por visitante de un valor de dimensión determinado, verá porcentajes superiores al 100 %. Al ordenar los informes de clasificación por esta métrica, se muestra el tiempo de anomalía empleado por los valores de visitante, lo que generalmente no es muy útil. Adobe recomienda ordenar según otra métrica, como [Visitas](visits.md), en los informes de clasificación.

Consulte [Información general sobre el tiempo empleado](time-spent.md) para saber más detalles sobre el tiempo invertido.

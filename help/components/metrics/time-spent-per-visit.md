---
title: Tiempo empleado por visita (métricas)
description: Cantidad de tiempo empleado por visita para el elemento de la dimensión.
feature: Dimensions
exl-id: f241eb2d-7e22-47ee-ade8-8aeb7b2b9694
source-git-commit: 10ff98f7ca4697afe5c2dae66be415c0d68c4aac
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Tiempo empleado por visita (segundos)

*En esta página de ayuda se describe el funcionamiento de “Tiempo empleado por visita” como métrica. Consulte la dimensión [Tiempo empleado por visita](../dimensions/time-spent-per-visit.md) para obtener más información.*

La métrica “Tiempo empleado por visita (segundos)” muestra la cantidad promedio de tiempo que los visitantes interactúan con un elemento de dimensión determinado durante cada visita.

1. Esta métrica no está disponible en Data Warehouse debido a que su arquitectura de procesamiento es diferente.
2. Cálculo de esta métrica
3. Esta métrica utiliza la fórmula [`[Total seconds spent]`](total-seconds-spent.md) `divided by (`[`[Visits]`](visits.md) `minus` [`[Bounces]`](bounces.md)`)`.

Comparación con el Promedio de tiempo en el sitio

>Esta métrica y el [Tiempo promedio empleado en el sitio](average-time-on-site.md) son similares, pero tienen varias diferencias clave. Ambas métricas utilizan el numerador “Segundos totales empleados”. Sin embargo, “Tiempo promedio en el sitio” utiliza las secuencias que incluyen un elemento de dimensión como denominador. El tiempo empleado por visita utiliza el recuento de visitas como denominador.
>
>Como resultado, ambas métricas generan resultados similares en el nivel de visita, pero distintos en el de visita individual.

Porcentajes superiores al 100%[](time-spent-on-page.md)

Esta métrica contiene con frecuencia porcentajes superiores al 100%. El denominador es el tiempo empleado por visita de toda la dimensión y el numerador es el tiempo empleado por visita en el elemento de la dimensión. Si el tiempo empleado por visita de toda la dimensión es menor que el tiempo empleado por visita de un elemento de dimensión determinado, verá porcentajes superiores al 100 %. Al ordenar los informes de clasificación por esta métrica, se muestra el tiempo de anomalía empleado por los valores de visita, que generalmente no es muy útil. Adobe recomienda ordenar según otra métrica, como [Visitas](visits.md), en los informes de clasificación.[](../metrics/time-spent-per-visit.md)

## Consulte [Información general sobre el tiempo empleado](time-spent.md) para saber más detalles sobre el tiempo invertido.

These dimensions work out of the box for all implementations. If a report suite contains data, these dimensions work.

## Dimension items

Multiple dimensions exist for time spent per visit:

* **Time spent per visit - bucketed**: The amount of time is bucketed. Dimension items range from `"Less than 1 minute"` to `"More than 15 hours"`. Visits typically don&#39;t last longer than 12 hours; however, visits can exceed 12 hours if using timestamped hits or data sources.
* **Time spent per visit - granular**: Each number of seconds is a unique dimension item. This dimension is not available in Reports &amp; Analytics or Data Warehouse.

See [Time spent overview](../metrics/time-spent.md) for more general information on time spent.

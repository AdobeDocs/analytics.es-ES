---
title: Tiempo empleado por visita
description: Cantidad de tiempo empleado por visita para el elemento de la dimensión.
translation-type: ht
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: ht
source-wordcount: '259'
ht-degree: 100%

---


# Tiempo empleado por visita (segundos)

*En esta página de ayuda se describe el funcionamiento de “Tiempo empleado por visita” como métrica. Consulte la dimensión [Tiempo empleado por visita](../dimensions/time-spent-per-visit.md) para obtener más información.*

La métrica “Tiempo empleado por visita (segundos)” muestra la cantidad promedio de tiempo que los visitantes interactúan con un elemento de dimensión determinado durante cada visita.

Esta métrica no está disponible en Data Warehouse debido a que su arquitectura de procesamiento es diferente.

## Cálculo de esta métrica

Esta métrica utiliza la fórmula [`Total seconds spent`](total-seconds-spent.md) `divided by` ([`Visits`](visits.md) `minus` [`Bounces`](bounces.md)).

## Comparación con el Promedio de tiempo en el sitio

Esta métrica y el [Tiempo promedio empleado en el sitio](average-time-on-site.md) son similares, pero tienen varias diferencias clave. Ambas métricas utilizan el numerador “Segundos totales empleados”. Sin embargo, “Tiempo promedio en el sitio” utiliza las secuencias que incluyen un elemento de dimensión como denominador. El tiempo empleado por visita utiliza el recuento de visitas como denominador.

Como resultado, ambas métricas generan resultados similares en el nivel de visita, pero distintos en el de visita individual.

## Porcentajes superiores al 100%

Esta métrica contiene con frecuencia porcentajes superiores al 100%. El denominador es el tiempo empleado por visita de toda la dimensión y el numerador es el tiempo empleado por visita en el elemento de la dimensión. Si el tiempo empleado por visita de toda la dimensión es menor que el tiempo empleado por visita de un elemento de dimensión determinado, verá porcentajes superiores al 100 %. Al ordenar los informes de clasificación por esta métrica, se muestra el tiempo de anomalía empleado por los valores de visita, que generalmente no es muy útil. Adobe recomienda ordenar según otra métrica, como [Visitas](visits.md), en los informes de clasificación.

Consulte [Información general sobre el tiempo empleado](time-spent.md) para saber más detalles sobre el tiempo invertido.

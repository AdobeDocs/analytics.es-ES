---
title: Tiempo empleado por visita
description: Cantidad de tiempo empleado por visita para el elemento de dimensión.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 3%

---


# Tiempo empleado por visita (segundos)

*En esta página de ayuda se describe el funcionamiento de &quot;Tiempo empleado por visita&quot; como métrica. Consulte la dimensión[Tiempo empleado por visita](../dimensions/time-spent-per-visit.md)para obtener más información.*

La métrica &#39;Tiempo empleado por visita (segundos)&#39; muestra la cantidad promedio de tiempo que los visitantes interactúan con un elemento de dimensión determinado durante cada visita.

Esta métrica no está disponible en la Data warehouse debido a que su arquitectura de procesamiento es diferente.

## Cómo se calcula esta métrica

Esta métrica utiliza la fórmula [`Total seconds spent`](total-seconds-spent.md) ( `divided by`[`Visits`](visits.md) `minus` [`Bounces`](bounces.md)).

## Comparación con el tiempo promedio en el sitio

Esta métrica y el tiempo [promedio invertido en el sitio](average-time-on-site.md) son similares, pero tienen varias diferencias clave. Ambas métricas utilizan el numerador &#39;Segundos totales empleados&#39;. Sin embargo, &#39;Tiempo promedio en el sitio&#39; utiliza las secuencias que incluyen un elemento de dimensión como denominador. El tiempo empleado por visita utiliza el recuento de visitas como denominador.

Como resultado, estas métricas producen resultados similares a nivel de visita, pero son diferentes a nivel de visita.

## Porcentajes superiores al 100%

Esta métrica contiene con frecuencia porcentajes superiores al 100 %. El denominador es el tiempo empleado por visita de toda la dimensión y el numerador es el tiempo empleado por elemento de dimensión por visita. Si el tiempo empleado por visita de toda la dimensión es menor que el tiempo empleado por visita de un elemento de dimensión determinado, verá porcentajes superiores al 100 %. Al ordenar los informes de clasificación por esta métrica, se muestra el tiempo de anomalía empleado por los valores de visita, lo cual generalmente no es valioso. Adobe recomienda ordenar según otra métrica, como [Visitas](visits.md), en los informes de clasificación.

Consulte [Información general](time-spent.md) sobre el tiempo empleado para obtener información más general sobre el tiempo empleado.

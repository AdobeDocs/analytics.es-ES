---
title: Tiempo promedio en el sitio
description: Cantidad promedio de tiempo que un elemento de dimensión dado existió entre visitas individuales.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 1%

---


# Tiempo promedio en el sitio

La métrica &#39;Tiempo promedio en el sitio&#39; muestra la cantidad de tiempo que transcurrió entre las visitas para un elemento de dimensión determinado. Esta métrica es útil cuando desea ver el tiempo promedio empleado para elementos de dimensión específicos. También puede analizar la tendencia de esta métrica con el paso del tiempo para ver cómo cambia el tiempo empleado en general. Esta métrica se muestra en `HH:MM:SS` formato.

Esta métrica está relacionada con la dimensión [Tiempo empleado por visita](../dimensions/time-spent-per-visit.md) .

## Cómo se calcula esta métrica

Para un elemento de dimensión determinado, tome la marca de tiempo de cada visita individual donde exista ese elemento de dimensión. Compárela con la marca de tiempo de la siguiente visita en la visita. Si la visita no tiene una visita posterior, no la incluya en esta métrica. De todo el tiempo empleado para el elemento de dimensión, divida todos por el número de &quot;secuencias&quot; para ese elemento de dimensión. Una &quot;secuencia&quot; es donde un elemento de dimensión es el mismo para una o varias visitas individuales consecutivas. Este número resultante es la métrica que se muestra en los informes.

Por ejemplo: considere la siguiente visita:

| `Timestamp` | `Page` |
| --- | --- |
| `12:03:00` | `Home page` |
| `12:04:20` | `Product page A` |
| `12:05:30` | `Product page A` |
| `12:07:00` | `Product page B` |
| `12:07:40` | `Product page A` |
| `12:08:10` | `Checkout` |
| `12:10:00` | `Purchase` |
| `12:25:00` | `Home page` |
| `12:25:40` | `Product page A` |


Si desea un tiempo promedio en el sitio para el elemento de dimensión `Product page A`, primero tome la cantidad de tiempo transcurrido entre las visitas individuales para esa dimensión:

* **12:04:20 - 12:05:30** - 1 minuto 10 segundos
* **12:05:30 - 12:07:00** - 1 minuto 30 segundos
* **12:07:40 - 12:08:10** - 30 segundos
* **12:25:40 - ?** - No se incluye

La cantidad total de tiempo empleado `Product page A` es `00:03:10`. Esta visita tuvo dos secuencias; la primera secuencia para los dos valores consecutivos y la segunda antes del cierre de compra. La última visita individual de la visita no es una secuencia, ya que no hay una marca de hora de finalización.

El tiempo promedio en el sitio `Product page A` es `00:01:35`.

## Tiempo promedio empleado en el sitio (segundos)

La métrica &#39;Tiempo promedio invertido en el sitio (segundos)&#39; muestra los mismos datos presentados como un número entero en lugar de en `HH:MM:SS` formato. Esta métrica es más valiosa como componente dentro de las métricas calculadas.

## Los totales de desglose no coinciden con el elemento de línea principal

La métrica &#39;Tiempo promedio en el sitio&#39; utiliza secuencias no interrumpidas de una dimensión determinada. La dimensión de desglose no depende de la dimensión principal al calcular estas secuencias. Por ejemplo: considere la siguiente visita:

| `Timestamp` | `Page name` | `Site section` |
| --- | --- | --- |
| `12:00:00` | `Home` | `Foxes` |
| `12:00:30` | `Product` | `Foxes` |
| `12:02:10` | `Home` | `Foxes` |
| `12:02:20` | `(None; exit link click)` | `(None; exit link click)` |

Para calcular el tiempo promedio en el sitio para el elemento de dimensión `Home` se utilizaría el siguiente cálculo:

```text
(30 + 10) / 2 = 20 seconds average time on site
```

Si aplicara un desglose utilizando la dimensión de secciones [del](../dimensions/site-section.md) sitio, utilizaría el siguiente cálculo:

```text
(30 + 10) / 1 = 40 seconds average time on site
```

Dado que había una única secuencia en la dimensión de desglose, utiliza un denominador diferente a su dimensión principal. Estas métricas generalmente proporcionan resultados similares a nivel de visita, pero pueden ser diferentes a nivel de visita individual.

## Porcentajes superiores al 100%

Esta métrica contiene con frecuencia porcentajes superiores al 100 %. El denominador es el tiempo promedio de toda la dimensión en el sitio y el numerador es el tiempo promedio del elemento de dimensión en el sitio. Si el tiempo promedio en el sitio de toda la dimensión es menor que el tiempo promedio en el sitio de un elemento de dimensión determinado, verá porcentajes superiores al 100%. Al ordenar los informes de clasificación por esta métrica, se muestra el tiempo promedio de anomalías en los valores del sitio, lo cual generalmente no es valioso. Adobe recomienda ordenar según otra métrica, como [Visitas](visits.md), en los informes de clasificación.

Consulte [Información general](time-spent.md) sobre el tiempo empleado para obtener información más general sobre el tiempo empleado.

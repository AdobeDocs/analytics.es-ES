---
title: Promedio de tiempo en el sitio
description: Cantidad promedio de tiempo que un elemento de dimensión en concreto existió entre visitas.
feature: Metrics
exl-id: bf9056e2-4f6d-4c4f-b641-d3146ce269ff
source-git-commit: 9e140a6be5ab151d7a4e88e317c59eafea4d6e1d
workflow-type: tm+mt
source-wordcount: '558'
ht-degree: 92%

---

# Promedio de tiempo en el sitio

El &quot;Promedio de tiempo en el sitio&quot; [métrica](overview.md) muestra la cantidad de tiempo que transcurrió entre visitas individuales para un elemento de dimensión determinado. Esta métrica es útil cuando desea ver el tiempo promedio empleado para elementos de dimensión específicos. También puede analizar la tendencia de esta métrica con el paso del tiempo para ver cómo cambia el tiempo empleado en general. Esta métrica se muestra con el formato `HH:MM:SS`.

Esta métrica está relacionada con la dimensión [Tiempo empleado por visita](../dimensions/time-spent-per-visit.md).

## Cálculo de esta métrica

Para un elemento de dimensión determinado, tome la marca de tiempo de cada visita individual donde exista ese elemento de dimensión. Compare esta visita individual con la marca de tiempo de la siguiente en la visita general. Si la visita individual no tiene una visita posterior, no la incluya en esta métrica. De todo el tiempo empleado para el elemento de dimensión, divida todos por el número de “secuencias” para ese elemento de dimensión. Una secuencia es la coincidencia de un elemento de dimensión para una o varias visitas individuales consecutivas. Este número resultante es la métrica que se muestra en los informes.

Por ejemplo:

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


Si desea ver el tiempo promedio en el sitio para el elemento de dimensión `Product page A`, primero debe usar la cantidad de tiempo transcurrido entre las visitas individuales para esa dimensión:

* **12:04:20 - 12:05:30** = 1 minuto y 10 segundos
* **12:05:30 - 12:07:00** = 1 minuto y 30 segundos
* **12:07:40 - 12:08:10** = 30 segundos
* **12:25:40 = ?** = No se incluye

La cantidad total de tiempo empleado de `Product page A` es `00:03:10`. Esta visita tuvo dos secuencias; la primera secuencia para los dos valores consecutivos y la segunda antes del cierre de compra. La última visita individual de la visita no es una secuencia, ya que no hay una marca de hora de finalización.

El tiempo promedio de `Product page A` en el sitio es `00:01:35`.

>[!NOTE]
>
>Esta métrica muestra un valor de `"Invalid"` si el elemento de dimensión contiene solo las visitas que fueron las últimas de una visita. Esta métrica requiere una visita posterior para rastrear el tiempo empleado.

## Tiempo promedio empleado en el sitio (segundos)

La métrica “Tiempo promedio empleado en el sitio (segundos)” muestra los mismos datos presentados como un número entero en lugar de en formato `HH:MM:SS`. Esta métrica es más valiosa como componente dentro de las métricas calculadas.

## Los totales de desglose no coinciden con el elemento de línea principal

La métrica “Promedio de tiempo en el sitio” utiliza secuencias no interrumpidas de una dimensión determinada. La dimensión de desglose no depende de la dimensión principal al calcular estas secuencias. Por ejemplo:

| `Timestamp` | `Page name` | `Site section` |
| --- | --- | --- |
| `12:00:00` | `Home` | `Foxes` |
| `12:00:30` | `Product` | `Foxes` |
| `12:02:10` | `Home` | `Foxes` |
| `12:02:20` | `(None; exit link click)` | `(None; exit link click)` |

Para calcular el tiempo promedio en el sitio para el elemento de la dimensión `Home` se utilizaría el siguiente cálculo:

```text
(30 + 10) / 2 = 20 seconds average time on site
```

Si aplica un desglose utilizando la dimensión de [secciones del sitio](../dimensions/site-section.md), se utilizaría el siguiente cálculo:

```text
(30 + 100 + 10) / 1 = 140 seconds (2 minutes 20 seconds) average time on site
```

Dado que había una única secuencia en la dimensión de desglose, se utiliza un denominador diferente a su dimensión principal. Estas métricas generalmente proporcionan resultados similares a nivel de visita, pero pueden ser diferentes a nivel de visita individual.

## Porcentajes superiores al 100%

Esta métrica contiene con frecuencia porcentajes superiores al 100%. El denominador es el tiempo promedio de toda la dimensión en el sitio y el numerador es el tiempo promedio del elemento de la dimensión en el sitio. Si el tiempo promedio en el sitio de toda la dimensión es menor que el tiempo promedio en el sitio de un elemento de dimensión determinado, verá porcentajes superiores al 100%. Al ordenar los informes de clasificación por esta métrica, se muestra el tiempo promedio de anomalías en los valores del sitio, lo cual generalmente no es muy útil. Adobe recomienda ordenar según otra métrica, como [Visitas](visits.md), en los informes de clasificación.

Consulte [Información general sobre el tiempo empleado](time-spent.md) para saber más detalles sobre el tiempo invertido.

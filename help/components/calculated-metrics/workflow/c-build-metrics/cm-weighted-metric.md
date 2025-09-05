---
description: Obtenga información acerca de ejemplos de métricas filtradas y ponderadas.
title: Métricas Filtradas Y Ponderadas
feature: Calculated Metrics
exl-id: bea46e03-7d05-44c8-b654-c61b1e32becc
source-git-commit: 665319bdfc4c1599292c2e7aea45622d77a291a7
workflow-type: tm+mt
source-wordcount: '158'
ht-degree: 63%

---

# Métricas filtradas y ponderadas

Este artículo muestra ejemplos de métricas filtradas y ponderadas.

## Tasa de devoluciones filtradas

Esta sencilla métrica filtrada muestra la frecuencia de rebotes únicamente para aquellas páginas con más de 100 visitas:

![Tasa de salida hacia otro sitio filtrada](assets/filtered-bounce-rate.png){zoomable="yes"}

Tenga en cuenta que esta fórmula depende de un plazo de tiempo constante. Si ejecuta un informe para un solo día, vale la pena observar cualquier página con más de 20 visitas. Si la ejecuta para un mes, es posible que desee el filtro para incluir más visitas.

## Tasa de salida hacia otro sitio filtrada con percentil

Este filtro muestra la tasa de salida hacia otro sitio del principal 30 por ciento de las páginas, cuando se ordena por visitas.

![Tasa de salida hacia otro sitio filtrada con percentil](assets/filtered-bounce-rate-with-percentile.png){zoomable="yes"}

## Tasa de salida hacia otro sitio ponderada

Suponga que desea clasificar por la tasa de devoluciones en general, pero las páginas con un mayor número de visitas deben estar en una posición superior de la lista. Puede crear una frecuencia de rebotes ponderada similar a esta:

![](assets/weighted-bounce-rate.png)

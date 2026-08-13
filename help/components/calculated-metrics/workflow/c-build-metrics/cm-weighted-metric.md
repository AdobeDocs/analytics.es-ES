---
description: Obtenga información acerca de ejemplos de métricas filtradas y ponderadas.
title: Métricas Filtradas Y Ponderadas
feature: Calculated Metrics
exl-id: bea46e03-7d05-44c8-b654-c61b1e32becc
TQID: https://experienceleague.adobe.com/Euk3sI0-AYtfmpEbL-8gfWU4HcFE6kGO6QGgctZbvig
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 158
ht-degree: 9%

---

# Métricas filtradas y ponderadas

Este artículo muestra ejemplos de métricas filtradas y ponderadas.

## Tasa de devoluciones filtradas

Esta métrica filtrada simple muestra la tasa de salida hacia otro sitio solo para las páginas con más de 100 visitas:

![Tasa de salida hacia otro sitio filtrada](assets/filtered-bounce-rate.png){zoomable="yes"}

Tenga en cuenta que esta fórmula depende de un intervalo de tiempo coherente. Si ejecuta un informe para un solo día, vale la pena mirar cualquier página con más de 20 visitas. Si lo ejecuta durante un mes, es posible que desee que el filtro incluya más visitas.

## Tasa de salida hacia otro sitio filtrada con percentil

Este filtro muestra la tasa de salida hacia otro sitio del principal 30 por ciento de las páginas, cuando se ordena por visitas.

![Tasa de salida hacia otro sitio filtrada con percentil](assets/filtered-bounce-rate-with-percentile.png){zoomable="yes"}

## Tasa de salida hacia otro sitio ponderada

Supongamos que desea ordenar por tasa de salida hacia otro sitio en general, pero las páginas con visitas más altas deben estar más arriba en la lista. Puede crear una frecuencia de rebotes ponderada similar a esta:

![](assets/weighted-bounce-rate.png)

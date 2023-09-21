---
title: Semana
description: La semana en la que se produjo la métrica.
feature: Dimensions
exl-id: 944ec843-998c-473f-b8e6-16cf126745b4
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 92%

---

# Semana

La &quot;semana&quot; [dimensión](overview.md) informa de la semana en que se produjo una métrica determinada. El primer elemento de dimensión es la primera semana del intervalo de fechas y el último elemento de dimensión es la última semana del intervalo de fechas. Esta dimensión es vital para los informes de tendencias, ya que le permite ver las métricas a lo largo del tiempo.

## Rellene esta dimensión con datos

Esta dimensión funciona de forma predeterminada para todas las implementaciones. Si un grupo de informes contiene datos, esta dimensión funciona.

## Elementos de dimensión

En Analysis Workspace, los elementos de dimensión incluyen la fecha (mes, día y año) del primer día de la semana.

En Data Warehouse, los elementos de dimensión incluyen semanas numeradas en función del intervalo de fechas de la solicitud. Por ejemplo, la primera semana completa es `"Week 1"`. Si una solicitud incluye una semana parcial, los datos se agrupan en el elemento de dimensión `"Week 0"`.

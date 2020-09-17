---
title: Semana
description: La semana en la que se produjo la métrica.
translation-type: tm+mt
source-git-commit: a94b8e090b9a3c75a57fd396cac8486bba2e5d79
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 42%

---


# Semana

La dimensión “Semana” indica la semana en que se produjo una métrica determinada. El primer elemento de dimensión es la primera semana del intervalo de fechas y el último elemento de dimensión es la última semana del intervalo de fechas. Esta dimensión es vital para los informes de tendencias, ya que le permite ver las métricas a lo largo del tiempo.

## Rellene esta dimensión con datos

Esta dimensión funciona de forma predeterminada para todas las implementaciones. Si un grupo de informes contiene datos, esta dimensión funciona.

## Elementos de Dimension

En Analysis Workspace, los elementos de dimensión incluyen la fecha (mes, día y año) del primer día de la semana.

En Data Warehouse, los elementos de dimensión incluyen semanas numeradas en función del intervalo de fechas de la solicitud. Por ejemplo, la primera semana completa es `"Week 1"`. Si una solicitud incluye una semana parcial, los datos se agrupan en el elemento de dimensión `"Week 0"`.

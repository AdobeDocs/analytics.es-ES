---
title: Visitantes únicos
description: Número de ID de visitante único.
feature: Metrics
exl-id: 56e7bad4-4802-49ac-a0f1-ae77441fc016
source-git-commit: f26f406848ab26092738089aac64ed9b4fc08019
workflow-type: ht
source-wordcount: '172'
ht-degree: 100%

---

# Visitantes únicos

La [métrica](overview.md) &quot;Visitantes únicos&quot; muestra el número de ID de visitante para el elemento de dimensión. Es una de las métricas más comunes utilizadas para determinar el tráfico, ya que proporciona una visión general de alto nivel de la popularidad de un elemento de dimensión. Por ejemplo: un visitante puede llegar a su sitio todos los días durante un mes, pero contará como un visitante único.

Si utiliza [Análisis entre dispositivos](../cda/overview.md), esta métrica se sustituye por la métrica [Dispositivos únicos](unique-devices.md).

## Visitantes únicos diarios, semanales, mensuales, trimestrales y anuales

Analysis Workspace trata los visitantes únicos en función de la granularidad del informe. Por ejemplo, si utiliza la dimensión [Día](../dimensions/day.md), verá visitantes únicos diarios para cada elemento de dimensión. Sin embargo, de cara al total del informe, se anula la duplicación de visitantes únicos para el intervalo de fechas de la tabla de forma libre.

## Cálculo de esta métrica

Esta métrica cuenta el número de ID de visitante único para un elemento de dimensión determinado. Consulte [Información general de identificación de visitantes](/help/implement/id/overview.md) para obtener más información sobre cómo Adobe Analytics identifica a los visitantes únicos.

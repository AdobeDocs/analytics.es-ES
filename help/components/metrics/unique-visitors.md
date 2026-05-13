---
title: Visitantes únicos
description: Número de ID de visitante único.
feature: Metrics
exl-id: 56e7bad4-4802-49ac-a0f1-ae77441fc016
TQID: https://experienceleague.adobe.com/A0NvwoGPFLuS4e857eH-nMgmzAmz0EuGVQVDNBgiN4A
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 174
ht-degree: 100%

---

# Visitantes únicos

La [métrica](overview.md) &quot;Visitantes únicos&quot; muestra el número de ID de visitante para el elemento de dimensión. Es una de las métricas más comunes utilizadas para determinar el tráfico, ya que proporciona una visión general de alto nivel de la popularidad de un elemento de dimensión. Por ejemplo: un visitante puede llegar a su sitio todos los días durante un mes, pero contará como un visitante único.

Si utiliza [Análisis entre dispositivos](../cda/overview.md), esta métrica se sustituye por la métrica [Dispositivos únicos](unique-devices.md).

## Visitantes únicos diarios, semanales, mensuales, trimestrales y anuales

Analysis Workspace trata los visitantes únicos en función de la granularidad del informe. Por ejemplo, si utiliza la dimensión [Día](../dimensions/day.md), verá visitantes únicos diarios para cada elemento de dimensión. Sin embargo, de cara al total del informe, se anula la duplicación de visitantes únicos para el intervalo de fechas de la tabla de forma libre.

## Cálculo de esta métrica

Esta métrica cuenta el número de ID de visitante único para un elemento de dimensión determinado. Consulte [Información general de identificación de visitantes](/help/implement/id/overview.md) para obtener más información sobre cómo Adobe Analytics identifica a los visitantes únicos.

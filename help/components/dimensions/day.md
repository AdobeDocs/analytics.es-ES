---
title: Día
description: El día en el que se produjo la métrica.
feature: Dimensions
exl-id: 2f93ae8b-422c-4e1e-81d3-43cc0aa442c4
TQID: https://experienceleague.adobe.com/q9gioxGcmj2xB-yamZUyM3jLLlTpT4NHq1CFCMqm-6I
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 59%
---
# Día

La dimensión [Día](overview.md) indica el día en el que se produjo una métrica determinada. El primer elemento de dimensión es el primer día del intervalo de fechas y el último elemento de dimensión es el último día del intervalo de fechas. Esta dimensión es vital para los informes de tendencias, ya que le permite ver las métricas a lo largo del tiempo.

## Rellene esta dimensión con datos

Esta dimensión se deriva de la marca de tiempo de cada visita individual. No hay ninguna variable que establecer; funciona de forma predeterminada en cualquier implementación.

| Propiedad | Valor |
| --- | --- |
| **variable de AppMeasurement** | Ninguno (derivado de la marca de tiempo de la visita) |
| **Campo Web SDK / XDM** | Ninguno (derivado de la marca de tiempo de la visita) |
| **Parámetro de consulta** | n/a |
| **etiqueta XML** | n/a |
| **Límite de bytes** | n/a |
| **Persistencia** | Hit |

## Elementos de dimensión

Los elementos de dimensión incluyen la fecha de un día determinado. Incluye el mes, el día y el año como parte del elemento de dimensión.

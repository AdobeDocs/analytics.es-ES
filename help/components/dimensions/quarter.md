---
title: Trimestre
description: El trimestre en el que se produjo la métrica.
feature: Dimensions
exl-id: e7c837d2-f891-4029-b520-4bc6c4387622
TQID: 'https://experienceleague.adobe.com/uKfzD1fZ3q1p6Np0C3QcWDgJMKMqvRa2NEVzCorRafY'
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
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '140'
ht-degree: 57%
---
# Trimestre

La dimensión [Trimestre](overview.md) indica el trimestre en el que se produjo una métrica determinada. El primer elemento de dimensión es el primer trimestre del intervalo de fechas y el último elemento de dimensión es el último trimestre del intervalo de fechas. Esta dimensión es ideal para los informes de tendencias, ya que le permite ver las métricas a lo largo del tiempo.

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

Los elementos de dimensión incluyen el trimestre y el año de una fecha determinada.

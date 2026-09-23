---
title: Visitas a una sola página (dimensiones)
description: Un indicador que indica que la visita consistió en una sola página.
feature: Dimensions
exl-id: f7b58941-add4-4e7b-8645-a64280fd9dcb
TQID: https://experienceleague.adobe.com/mMxxlVpQi7IsSuxSZGijnvWeoqCa-ybf8otPRDf6AyQ
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
source-wordcount: '187'
ht-degree: 64%
---
# Visitas de página única

>[!BEGINSHADEBOX]

*Esta página de ayuda describe cómo funciona &quot;Visitas de página única&quot; como [dimensión](overview.md). Consulte la métrica [Visita de página única](../metrics/single-page-visits.md) para obtener más información.*

>[!ENDSHADEBOX]

La dimensión Visitas de página única indica el número de visitas que consistieron en un único elemento de dimensión de [Página](page.md). Es la forma de dimensión de la métrica [Visitas de página única](../metrics/single-page-visits.md).

Esta dimensión se utiliza comúnmente como un componente dentro de la [segmentación](../segmentation/seg-home.md). No suele utilizarse como dimensión en los informes.

## Rellene esta dimensión con datos

Adobe calcula esta dimensión del lado del servidor mediante la evaluación de si cada visita contenía una sola página única. No hay ninguna variable que establecer; funciona de forma predeterminada para todas las implementaciones.

| Propiedad | Valor |
| --- | --- |
| **variable de AppMeasurement** | Ninguno (calculado por Adobe) |
| **Campo Web SDK / XDM** | Ninguno (calculado por Adobe) |
| **Parámetro de consulta** | n/a |
| **etiqueta XML** | n/a |
| **Límite de bytes** | n/a |
| **Persistencia** | N/A |

## Elementos de dimensión

El único elemento de dimensión es `"Enabled"`. Si una visita consta de una sola página, el hit se establece en este valor. Todos los demás hits se omiten en este informe.

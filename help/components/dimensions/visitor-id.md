---
title: ID de visitante
description: El identificador único de un visitante disponible en Data Warehouse.
feature: Dimensions
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
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
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '133'
ht-degree: 18%
---
# ID de visitante

La &quot;ID de visitante&quot; [dimension](overview.md) proporciona el identificador único para cada visitante.

>[!IMPORTANT]
>
>Esta dimensión solo está disponible en Data Warehouse.

## Rellene esta dimensión con datos

Adobe genera automáticamente un ID de visitante para cada visitante. Este valor es el mismo que el valor concatenado de las columnas `visid_high` y `visid_low` en las fuentes de datos. Puede anular el valor generado automáticamente con la variable `visitorID`. Consulte [Referencia de columna de datos](../../export/analytics-data-feed/c-df-contents/datafeeds-reference.md) para obtener más información.

| Propiedad | Valor |
| --- | --- |
| **variable de AppMeasurement** | [`visitorID`](/help/implement/vars/config-vars/visitorid.md) |
| **Campo Web SDK / XDM** | Ninguno |
| **Parámetro de consulta** | [`vid`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **etiqueta XML** | [`<visitorId>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Límite de bytes** | 255 bytes |
| **Persistencia** | N/A |

## Elementos de dimensión

Los elementos de Dimension incluyen el identificador único de cada visitante.

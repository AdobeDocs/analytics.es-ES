---
title: ID de visitante de Experience Cloud
description: El Experience Cloud ID (ECID) del visitante, disponible en Data Warehouse.
feature: Dimensions
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
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
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 18%
---
# ID de visitante de Experience Cloud

La &quot;ID de visitante de Experience Cloud&quot; [dimension](overview.md) proporciona el ECID para cada visitante. Es un número de 128 bits que consta de dos números concatenados de 64 bits seguidos de 19 dígitos.

>[!IMPORTANT]
>
>Esta dimensión solo está disponible en Data Warehouse.

## Rellene esta dimensión con datos

Esta dimensión requiere una implementación que utilice el servicio de ID de visitante (VisitorAPI) o el servicio de ID de Experience Platform. Corresponde a la columna `mcvisid` de las fuentes de datos. Consulte [Referencia de columna de datos](../../export/analytics-data-feed/c-df-contents/datafeeds-reference.md) para obtener más información.

| Propiedad | Valor |
| --- | --- |
| **variable de AppMeasurement** | Ninguno (lo establece el servicio de ID de visitante de Experience Cloud) |
| **Campo Web SDK / XDM** | Ninguno (configurado por el servicio de identidad de Experience Cloud) |
| **Parámetro de consulta** | [`mid`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **etiqueta XML** | [`<marketingCloudVisitorId>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Límite de bytes** | n/a |
| **Persistencia** | N/A |

## Elementos de dimensión

Los elementos de Dimension incluyen el Experience Cloud ID de cada visitante.

---
title: ID de compra
description: El identificador único de una compra, disponible en Data Warehouse.
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
source-wordcount: '124'
ht-degree: 18%
---
# ID de compra

La &quot;ID de compra&quot; [dimensión](overview.md) proporciona el identificador único de una compra.

>[!IMPORTANT]
>
>Esta dimensión solo está disponible en Data Warehouse.

## Rellene esta dimensión con datos

Esta dimensión se ha establecido mediante la variable [`purchaseID`](/help/implement/vars/page-vars/purchaseid.md). Corresponde a la columna `purchaseid` de las fuentes de datos. Consulte [Referencia de columna de datos](../../export/analytics-data-feed/c-df-contents/datafeeds-reference.md) para obtener más información.

| Propiedad | Valor |
| --- | --- |
| **variable de AppMeasurement** | [`purchaseID`](/help/implement/vars/page-vars/purchaseid.md) |
| **Campo Web SDK / XDM** | [`commerce.order.purchaseID`](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/event/commerce-details) |
| **Parámetro de consulta** | [`purchaseID`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **etiqueta XML** | [`<purchaseId>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Límite de bytes** | 20 bytes |
| **Persistencia** | Hit |

## Elementos de dimensión

Los elementos de Dimension incluyen los ID de compra recopilados en el sitio.

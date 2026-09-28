---
title: Búsqueda de pago
description: Distingue las métricas de la búsqueda de pago y la búsqueda natural.
feature: Dimensions
exl-id: b12665a3-e92f-4fc1-acd3-ea17a316e5e5
TQID: 'https://experienceleague.adobe.com/s9jhjGeXaOCo-Wz-Jyof951NZdRWfz-9tjrVrjHvTS0'
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
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 59%
---
# Búsqueda de pago

La [dimensión](overview.md) &quot;Búsqueda de pago&quot; le permite ver cualquier métrica y compararla entre la búsqueda de pago y la búsqueda natural. Se omiten todos los demás hits fuera de los motores de búsqueda. Esta dimensión es útil para comprender cómo se comparan los esfuerzos de búsqueda de pago con la búsqueda orgánica.

## Rellene esta dimensión con datos

Adobe deriva esta dimensión mediante la detección de búsqueda de pago, que clasifica el tráfico del motor de búsqueda como de pago o natural. No hay ninguna variable que establecer. El único requisito es tener [Detección de búsqueda de pago](/help/admin/tools/manage-rs/edit-settings/general/paid-search-detection/paid-search-detection.md) configurada correctamente en la configuración del grupo de informes. Si la detección de búsqueda de pago está configurada correctamente y el grupo de informes tiene datos, esta dimensión siempre funciona.

| Propiedad | Valor |
| --- | --- |
| **variable de AppMeasurement** | Ninguno (derivado por detección de búsqueda de pago) |
| **Campo Web SDK / XDM** | Ninguno (derivado por detección de búsqueda de pago) |
| **Parámetro de consulta** | n/a |
| **etiqueta XML** | n/a |
| **Límite de bytes** | n/a |
| **Persistencia** | N/A |

## Elementos de dimensión

Los elementos de dimensión incluyen dos valores estáticos: `"Natural"` y `"Paid"`. Si una visita coincide con los criterios de un motor de búsqueda y también con la detección de búsqueda de pago, pertenece al elemento de dimensión `"Paid"`. Si una visita coincide con los criterios de un motor de búsqueda y *no* coincide con la detección de búsqueda de pago, pertenece al elemento de dimensión `"Natural"`.

---
title: Compatibilidad con cookies
description: Determina si el explorador admite cookies.
feature: Dimensions
exl-id: 07d4fe12-0d60-469d-98b1-e93ce5a0fd21
TQID: 'https://experienceleague.adobe.com/axOR-Ut8kkRSCTYPescoSCa44g25E8xxp4gg-yQlyYw'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
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
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 38%
---
# Compatibilidad con cookies

El informe &quot;Compatibilidad con cookies&quot; [dimension](overview.md) indica si el explorador admite cookies para una visita determinada. Es útil determinar la proporción de visitantes que utilizan exploradores que admiten cookies y los que las deshabilitan intencionalmente.

## Rellene esta dimensión con datos

La compatibilidad con cookies se recopila automáticamente en el lado del cliente: AppMeasurement intenta establecer una cookie denominada `s_cc` y, a continuación, informa de si existe: `Y` si el explorador admite y tiene las cookies habilitadas; o `N` si las cookies están deshabilitadas. Funciona de forma predeterminada en cualquier implementación de AppMeasurement o Web SDK (etiquetas); no hay ninguna variable que establecer. Si recopila datos fuera de AppMeasurement o de Web SDK (por ejemplo, a través de la API), envíe `Y` o `N` en cada visita.

| Propiedad | Valor |
| --- | --- |
| **variable de AppMeasurement** | Ninguno (recopilado automáticamente) |
| **Campo Web SDK / XDM** | Ninguno (recopilado automáticamente) |
| **Parámetro de consulta** | [`k`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **etiqueta XML** | [`<cookiesEnabled>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Límite de bytes** | 1 byte |
| **Persistencia** | N/A |

## Elementos de dimensión

Los elementos de dimensión incluyen `Enabled`, `Disabled` y `Unknown`.

* **`Enabled`**: El explorador admite cookies y las tiene habilitadas.
* **`Disabled`**: El explorador no admite cookies o el visitante las ha deshabilitado.
* **`Unknown`**: AppMeasurement no pudo determinar la compatibilidad con cookies. La cadena de consultas `k` no estaba presente en la solicitud de imagen.

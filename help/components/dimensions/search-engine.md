---
title: Motor de búsqueda
description: Motor de búsqueda que el visitante utilizó para llegar al sitio.
feature: Dimensions
exl-id: 2815f1fa-d938-4d2b-b864-c4ed834f3ed3
TQID: 'https://experienceleague.adobe.com/fOk6ypu24XzT6aypOHUAE-RYSW39wyrzkyt-lvOKy7Y'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
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
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 69%
---
# Motor de búsqueda

El &quot;Motor de búsqueda&quot; [dimension](overview.md) indica los motores de búsqueda que los visitantes utilizan para llegar al sitio. Un remitente del reenvío debe cumplir los dos requisitos siguientes para clasificarse como motor de búsqueda:

* Adobe reconoce el dominio de referencia como un motor de búsqueda válido.
* Existe un parámetro de cadena de consulta de palabra clave en la dirección URL de referencia. El parámetro de cadena de consulta puede estar en blanco (como sucede con varios motores de búsqueda debido a políticas de privacidad).

Si desea distinguir la búsqueda de pago y la búsqueda natural, se requiere la [detección de búsquedas de pago](/help/admin/tools/manage-rs/edit-settings/general/paid-search-detection/paid-search-detection.md). Hay varias dimensiones disponibles para los motores de búsqueda:

* **Motor de búsqueda**: Motor de búsqueda utilizado para llegar a su sitio, independientemente de si es de pago o natural.
* **Motor de búsqueda - de pago**: Motor de búsqueda utilizado para llegar al sitio, que coincidió con la detección de búsquedas de pago.
* **Motor de búsqueda - natural**: Motor de búsqueda utilizado para llegar al sitio, que no coincidió con la detección de búsquedas de pago.

## Rellene esta dimensión con datos

Adobe deriva esta dimensión del [referente](referrer.md) de cada visita, comparándola con varias tablas de búsqueda internas de Adobe. No hay ninguna variable que establecer. Dado que cada valor depende del referente, asegúrese de que la dimensión de referente y los [filtros de URL internos](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md) estén correctamente configurados.

| Propiedad | Valor |
| --- | --- |
| **variable de AppMeasurement** | Ninguno (derivado del referente) |
| **Campo Web SDK / XDM** | Ninguno (derivado del referente) |
| **Parámetro de consulta** | n/a |
| **etiqueta XML** | n/a |
| **Límite de bytes** | n/a |
| **Persistencia** | N/A |

## Elementos de dimensión

Los elementos de dimensión incluyen motores de búsqueda utilizados para llegar al sitio. Los valores de ejemplo incluyen `"Google"`, `"Microsoft Bing"` y `"DuckDuckGo"`. El elemento de dimensión `"Unspecified"` es todo el tráfico que no sea de búsqueda.

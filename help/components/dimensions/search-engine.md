---
title: Motor de búsqueda
description: Motor de búsqueda que el visitante utilizó para llegar al sitio.
feature: Dimensions
exl-id: 2815f1fa-d938-4d2b-b864-c4ed834f3ed3
TQID: https://experienceleague.adobe.com/fOk6ypu24XzT6aypOHUAE-RYSW39wyrzkyt-lvOKy7Y
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 225
ht-degree: 93%

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

Esta dimensión hace referencia a varias tablas de búsqueda internas de Adobe. Cada valor se basa en el [remitente del reenvío](referrer.md) de la visita, que depende de los [filtros de URL internos](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md). Asegúrese de que la dimensión de remitente del reenvío y los filtros de URL internos están correctamente configurados.

## Elementos de dimensión

Los elementos de dimensión incluyen motores de búsqueda utilizados para llegar al sitio. Los valores de ejemplo incluyen `"Google"`, `"Microsoft Bing"` y `"DuckDuckGo"`. El elemento de dimensión `"Unspecified"` es todo el tráfico que no sea de búsqueda.

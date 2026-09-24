---
title: Palabra clave de búsqueda
description: La palabra clave de búsqueda que el visitante utilizó para llegar al sitio.
feature: Dimensions
exl-id: 5a1236a6-f94b-4679-906a-b539afe36887
TQID: https://experienceleague.adobe.com/4naavrC42ddsxGFJfkOJ0wzHLTa7tdMeI9nKDgVWrBY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
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
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 70%
---
# Palabra clave de búsqueda

La &quot;Palabra clave de búsqueda&quot; [dimension](overview.md) indica las palabras clave de búsqueda que los visitantes utilizan para llegar al sitio.

>[!IMPORTANT]
>
>La mayoría de los motores de búsqueda ya no pasan la palabra clave de búsqueda debido al aumento de las prácticas de privacidad. Los hits en los que Adobe reconoce un motor de búsqueda pero en las que no puede reconocer una palabra clave se agrupan en el elemento de dimensión `"Keyword unavailable"`.

Un remitente del reenvío debe cumplir los dos requisitos siguientes para clasificarse como palabra clave de búsqueda:

* Adobe reconoce el dominio de referencia como un [motor de búsqueda](search-engine.md) válido.
* Existe un parámetro de cadena de consulta de palabra clave en la dirección URL de referencia. Si la cadena de consulta de palabra clave existe pero no contiene un valor, se agrupa bajo el elemento de dimensión `"Keyword unavailable"`.

Si desea distinguir la búsqueda de pago y la búsqueda natural, se requiere la [detección de búsquedas de pago](/help/admin/tools/manage-rs/edit-settings/general/paid-search-detection/paid-search-detection.md). Hay varias dimensiones disponibles para las palabras clave de búsqueda:

* **Palabra clave de búsqueda**: La palabra clave de búsqueda utilizada para llegar al sitio, independientemente de si es una búsqueda de pago o natural.
* **Palabra clave de búsqueda - de pago**: La palabra clave de búsqueda utilizada para llegar a su sitio, que coincidió con la detección de búsquedas de pago.
* **Palabra clave de búsqueda - natural**: La palabra clave de búsqueda utilizada para llegar a su sitio, que no coincide con la detección de búsquedas de pago.

## Rellene esta dimensión con datos

Adobe deriva esta dimensión del motor de búsqueda [referente](referrer.md) de cada visita, y extrae la palabra clave de la cadena de consulta del referente. No hay ninguna variable que establecer. Dado que cada valor depende del referente, asegúrese de que la dimensión de referente y los [filtros de URL internos](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md) estén correctamente configurados.

| Propiedad | Valor |
| --- | --- |
| **variable de AppMeasurement** | Ninguno (derivado del referente del motor de búsqueda) |
| **Campo Web SDK / XDM** | Ninguno (derivado del referente del motor de búsqueda) |
| **Parámetro de consulta** | n/a |
| **etiqueta XML** | n/a |
| **Límite de bytes** | n/a |
| **Persistencia** | N/A |

## Elementos de dimensión

Los elementos de dimensión incluyen las palabras clave de búsqueda utilizadas para llegar al sitio. El elemento de dimensión `"Unspecified"` es todo el tráfico que no sea de búsqueda.

---
title: Motor de búsqueda
description: Motor de búsqueda que el visitante utilizó para llegar al sitio.
exl-id: 2815f1fa-d938-4d2b-b864-c4ed834f3ed3
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '224'
ht-degree: 100%

---

# Motor de búsqueda

La dimensión “Motor de búsqueda” indica los motores de búsqueda que los visitantes utilizan para llegar al sitio. Un remitente del reenvío debe cumplir los dos requisitos siguientes para clasificarse como motor de búsqueda:

* Adobe reconoce el dominio de referencia como un motor de búsqueda válido.
* Existe un parámetro de cadena de consulta de palabra clave en la dirección URL de referencia. El parámetro de cadena de consulta puede estar en blanco (como sucede con varios motores de búsqueda debido a políticas de privacidad).

Si desea distinguir la búsqueda de pago y la búsqueda natural, se requiere la [detección de búsquedas de pago](/help/admin/admin/paid-search-detection/paid-search-detection.md). Hay varias dimensiones disponibles para los motores de búsqueda:

* **Motor de búsqueda**: Motor de búsqueda utilizado para llegar a su sitio, independientemente de si es de pago o natural.
* **Motor de búsqueda - de pago**: Motor de búsqueda utilizado para llegar al sitio, que coincidió con la detección de búsquedas de pago.
* **Motor de búsqueda - natural**: Motor de búsqueda utilizado para llegar al sitio, que no coincidió con la detección de búsquedas de pago.

## Rellene esta dimensión con datos

Esta dimensión hace referencia a varias tablas de búsqueda internas de Adobe. Cada valor se basa en el [remitente del reenvío](referrer.md) de la visita, que depende de los [filtros de URL internos](/help/admin/admin/internal-url-filter-admin.md). Asegúrese de que la dimensión de remitente del reenvío y los filtros de URL internos están correctamente configurados.

## Elementos de dimensión

Los elementos de dimensión incluyen motores de búsqueda utilizados para llegar al sitio. Los valores de ejemplo incluyen `"Google"`, `"Microsoft Bing"` y `"DuckDuckGo"`. El elemento de dimensión `"Unspecified"` es todo el tráfico que no sea de búsqueda.

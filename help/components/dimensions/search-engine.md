---
title: Motor de búsqueda
description: Motor de búsqueda que el visitante utilizó para llegar al sitio.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 1%

---


# Motor de búsqueda

La dimensión &#39;Motor de búsqueda&#39; informa los motores de búsqueda que los visitantes utilizan para llegar al sitio. Un remitente del reenvío debe cumplir los dos requisitos siguientes para clasificarse como motor de búsqueda:

* Adobe reconoce el dominio de referencia como un motor de búsqueda válido;
* Existe un parámetro de cadena de consulta de palabra clave en la dirección URL de referencia. El parámetro de cadena de consulta puede estar en blanco (como sucede con varios motores de búsqueda debido a prácticas de privacidad).

Si desea distinguir la búsqueda paga y la búsqueda natural, se requiere la detección [de búsqueda](/help/admin/admin/paid-search-detection/paid-search-detection.md) paga. Existen varias dimensiones disponibles para los motores de búsqueda:

* **Motor** de búsqueda: Motor de búsqueda utilizado para llegar a su sitio, independientemente de si es pago o natural.
* **Motor de búsqueda - pago**: Motor de búsqueda utilizado para llegar al sitio, que coincidió con la detección de búsqueda paga.
* **Motor de búsqueda - natural**: Motor de búsqueda utilizado para llegar al sitio, que no coincide con la detección de búsqueda paga.

## Rellenar esta dimensión con datos

Esta dimensión hace referencia a varias tablas de búsqueda internas de Adobe. Cada valor se basa en el [remitente del reenvío](referrer.md) de la visita, que depende de los filtros [de URL](/help/admin/admin/internal-url-filter-admin.md)internos. Asegúrese de que la dimensión de remitente del reenvío y los filtros de URL internos están correctamente configurados.

## Elementos de dimensión

Los elementos de dimensión incluyen los motores de búsqueda utilizados para llegar al sitio. Los valores de ejemplo incluyen `"Google"`, `"Microsoft Bing"`y `"DuckDuckGo"`. El elemento de dimensión es todo tráfico que no sea de búsqueda. `"Unspecified"`

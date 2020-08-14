---
title: Palabra clave de búsqueda
description: La palabra clave de búsqueda que el visitante utilizó para llegar al sitio.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 78%

---


# Palabra clave de búsqueda

La dimensión “Palabra clave de búsqueda” indica las palabras clave de búsqueda que los visitantes utilizan para llegar al sitio.

>[!IMPORTANT]
>
>La mayoría de los motores de búsqueda ya no pasan la palabra clave de búsqueda debido al aumento de las prácticas de privacidad. Hits where Adobe recognizes a search engine but is missing a keyword groups under the dimension item `"Keyword unavailable"`.

Un remitente del reenvío debe cumplir los dos requisitos siguientes para clasificarse como palabra clave de búsqueda:

* Adobe reconoce el dominio de referencia como un [motor de búsqueda](search-engine.md) válido.
* Existe un parámetro de cadena de consulta de palabra clave en la dirección URL de referencia. If the keyword query string exists but does not contain a value, it groups under the dimension item `"Keyword unavailable"`.

Si desea distinguir la búsqueda de pago y la búsqueda natural, se requiere la [detección de búsquedas de pago](/help/admin/admin/paid-search-detection/paid-search-detection.md). Hay varias dimensiones disponibles para las palabras clave de búsqueda:

* **Palabra clave de búsqueda**: La palabra clave de búsqueda utilizada para llegar al sitio, independientemente de si es una búsqueda de pago o natural.
* **Palabra clave de búsqueda - de pago**: La palabra clave de búsqueda utilizada para llegar a su sitio, que coincidió con la detección de búsquedas de pago.
* **Palabra clave de búsqueda - natural**: La palabra clave de búsqueda utilizada para llegar a su sitio, que no coincide con la detección de búsquedas de pago.

## Rellene esta dimensión con datos

Esta dimensión hace referencia a varias tablas de búsqueda internas de Adobe. Cada valor se basa en el [remitente del reenvío](referrer.md) de la visita, que depende de los [filtros de URL internos](/help/admin/admin/internal-url-filter-admin.md). Asegúrese de que la dimensión de remitente del reenvío y los filtros de URL internos están correctamente configurados.

## Elementos de Dimension

Los elementos Dimension incluyen palabras clave de búsqueda utilizadas para llegar al sitio. The `"Unspecified"` dimension item is all non-search traffic.

---
title: Palabra clave de búsqueda
description: La palabra clave de búsqueda que el visitante utilizó para llegar al sitio.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 0%

---


# Palabra clave de búsqueda

La dimensión &#39;Palabra clave de búsqueda&#39; informa las palabras clave de búsqueda que los visitantes utilizan para llegar al sitio.

>[!IMPORTANT]
>
>La mayoría de los motores de búsqueda ya no pasan la palabra clave de búsqueda debido al aumento de las prácticas de privacidad. Visitas en las que Adobe reconoce un motor de búsqueda pero le falta un grupo de palabras clave en el elemento de dimensión `"Keyword unavailable"`.

Un remitente del reenvío debe cumplir los dos requisitos siguientes para clasificarse como palabra clave de búsqueda:

* Adobe reconoce el dominio de referencia como un motor de [búsqueda](search-engine.md)válido;
* Existe un parámetro de cadena de consulta de palabra clave en la dirección URL de referencia. Si la cadena de consulta de palabra clave existe pero no contiene un valor, se agrupa bajo el elemento de dimensión `"Keyword unavailable"`.

Si desea distinguir la búsqueda paga y la búsqueda natural, se requiere la detección [de búsqueda](/help/admin/admin/paid-search-detection/paid-search-detection.md) paga. Hay varias dimensiones disponibles para las palabras clave de búsqueda:

* **Palabra clave** de búsqueda: La palabra clave de búsqueda utilizada para llegar al sitio, independientemente de si es paga o natural.
* **Palabra clave de búsqueda: paga**: La palabra clave de búsqueda utilizada para llegar a su sitio, que coincidió con la detección de búsqueda paga.
* **Palabra clave de búsqueda: natural**: La palabra clave de búsqueda utilizada para llegar a su sitio, que no coincide con la detección de búsqueda paga.

## Rellenar esta dimensión con datos

Esta dimensión hace referencia a varias tablas de búsqueda internas de Adobe. Cada valor se basa en el [remitente del reenvío](referrer.md) de la visita, que depende de los filtros [de URL](/help/admin/admin/internal-url-filter-admin.md)internos. Asegúrese de que la dimensión de remitente del reenvío y los filtros de URL internos están correctamente configurados.

## Elementos de dimensión

Los elementos de dimensión incluyen palabras clave de búsqueda utilizadas para llegar al sitio. El elemento de dimensión es todo tráfico que no sea de búsqueda. `"Unspecified"`

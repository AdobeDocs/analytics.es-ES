---
description: Los filtros le permiten reducir el informe para incluir o excluir elementos de línea que concuerden con un filtro.
title: Filtrado de datos de los informes
topic: Reports and analytics
uuid: b6dcaaf7-61f0-4793-870d-e1d156575d5a
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Filtrar datos del informe {#concept_09DC5B986A644738B12204DAC76A90E1}

Los filtros le permiten reducir el informe para incluir o excluir elementos de línea que concuerden con un filtro.

## Filtro simple  {#section_5C4DE873F8D5484BB77F38A4AEB57B4A}

![](assets/filter.png)

El filtro simple aparece en la mayoría de informes para que pueda encontrar rápidamente elementos de línea concretos. Los filtros simples no utilizan ningún carácter especial, por lo que `-, ", ', +` y otros caracteres especiales concuerdan con el valor literal en el informe. Puede utilizar el espacio para encontrar elementos de línea que contienen múltiples términos.

Por ejemplo:

```
help search
```

Coincide con las páginas siguientes:

```
help:Search
help:Paid Search Detection
help:Configure paid search detection
help:Search Keywords Report
help:Internal Search Term
```

## Filtros avanzados {#section_E016626C084640E8A066B2FDA5B932BF}

Los filtros avanzados le permiten controlar el ámbito de su búsqueda a través de una serie de filtros. Puede seleccionar que coincida con todos los filtros o con cualquier filtro.

![](assets/advanced_filter.png)

**Contiene**

Coincide si el término se encuentra en cualquier punto del elemento de línea. Opera igual que un filtro simple.

>[!NOTE] No se pueden utilizar espacios en los filtros, ya que los espacios son delimitadores en las búsquedas

**No contiene**

Coincide si el término no se encuentra en cualquier punto del elemento de línea. Puede filtrar “sin especificar”, “ninguno”, “teclado no disponible” y otros [valores especiales](https://marketing.adobe.com/resources/help/es_ES/reference/none-unspecified-unknown-other.html) desde los informes mediante “No contiene”.

No contiene: `none`

Para un filtro más exacto, puede usar un filtro avanzado (caracteres especiales):

* Avanzado (carácter especial): `-^none$`
* Avanzado (carácter especial): `-"keyword unavailable"`

Por ejemplo, el siguiente elemento de línea se ha filtrado según el criterio &quot;No contiene&quot;, pero no se ha filtrado según el criterio &quot;Avanzado&quot; (carácter especial):

```
help:Rename the None classification key
```

**Contiene uno de**

Coincide si algún término, separado por espacios, se encuentra en el elemento de línea. El filtro siguiente muestra todas las páginas que contienen &quot;hombre&quot; o &quot;venta&quot;:

Contiene uno de: `mens sale`

Coincide con las páginas siguientes:

```
Womens
Mens
Mens:Desk & TravelJewelry & Accessories:Accessories:Hats:Mens
Sale & Values
```

**Es igual a**

Coincide si todo el elemento de línea, incluidos los espacios y otros caracteres, coinciden con la frase especificada.

Es igual a: `mens:desk & travel`

`Mens:Desk & Travel`

**Comienza con**

Coincide si el elemento de línea, incluidos los espacios y otros caracteres, empieza por la frase especificada.

Comienza con: `mens`

Coincide con las páginas siguientes:

```
Mens
Mens:Desk & Travel
Mens:Apparel
Mens Perfume Spray
Mens Hemp/Bamboo Flip Flops
```

**Finaliza con**

Coincide si el elemento de línea, incluidos los espacios y otros caracteres, acaba con la frase especificada.

Finaliza con: `jean`

Coincide con las páginas siguientes:

```
Bell Bottom Jean
Velvet Dream Skinny Leg Jean
Dark Slimmer Jean
Bling Belt High Waist Jean
Ocean Blue Jean
```

## Avanzado (carácter especial) {#section_83DA3B6C23EB4C119DB6D74062DB501D}

Avanzado le permite realizar una búsqueda con comodines y otras búsquedas complejas.

| Avanzado (carácter especial) | Descripción |
|--- |--- |
| `" "` | Coincide la frase exacta. |
| `*` | Comodín, coincidencia amplia. <br>Por ejemplo, `r*p` coincide con “Registro de suscripción”. |
| `^` | Comienza con. <br>No incluya un espacio entre los caracteres especiales y la frase de búsqueda. |
| `$` | Finaliza con. <br>No incluya un espacio entre los caracteres especiales y la frase de búsqueda. |
| `-` | No. <br>No incluya un espacio entre los caracteres especiales y la frase de búsqueda. |
| `|` | O<br>Nota:  Debe incluir un espacio a cada lado del carácter de barra vertical `" | "`. |

## Crear filtros específicos de informes {#task_DEBB0632411D4CA8AA0B3BA267A5B35F}

Instrucciones sobre cómo crear filtros de informes.

<!-- 

t_reports_filter_specific.xml

 -->

Ciertos informes contienen un filtro que es específico para ese informe. Por ejemplo, un [!UICONTROL Purchase Conversion Funnel Report] informe le permite filtrar por páginas web. A [!UICONTROL Geosegmentation Report] lets you filter by geographical region. Otros informes tienen otros filtros específicos.

Cuando accede a estos filtros, puede ver las métricas del informe para los artículos especificados en la lista.

**Para crear filtros específicos del informe**

1. Genere un informe, como un [!UICONTROL Purchase Report] ( **[!UICONTROL Site Metrics]** > **[!UICONTROL Purchases]** > **[!UICONTROL Purchase Conversion Funnel]**).
1. In the report header, click the **[!UICONTROL Filter]** link.
1. En la [!UICONTROL Filter Selector] página, haga clic en **[!UICONTROL Apply a Filter]** y seleccione un tipo de filtro.
1. To search for an item, type a character string in the **[!UICONTROL Search]** field.
1. Haga clic en **[!UICONTROL OK]**.

## Añadir un filtro de correlación {#task_065042E384DA4BF3864C58AF2B88D6E2}

Instrucciones sobre cómo añadir un filtro de correlación.

<!-- 

t_reports_correlation_filter.xml

 -->

Ciertos informes permiten que se les añadan filtros de correlación personalizados. For example, if you are viewing the [!UICONTROL Pages Report] for a report suite that has Site Sections correlated with a Women&#39;s page, you can create a filter rule that generates a report showing the most popular pages when Site Sections = Women.

Puede filtrar los datos que se muestran en un informe de correlación usando cualquier correlación disponible. Este ejemplo muestra cómo se agrega un filtro de correlación de motor de búsqueda.

**Para agregar un filtro de correlación**

1. Ejecute un informe que admita correlaciones. (Consulte [Ejecución de un informe de desglose](/help/analyze/reports-analytics/reports-customize/breakdowns.md#task_F685624830E64C829C8BE6435A107F69).)
1. In the report header, click the **[!UICONTROL Correlation Filter]** link.
1. En [!UICONTROL Filter Rule Creator], seleccione una categoría para correlacionarla con un elemento.
1. Haga clic en **[!UICONTROL OK.]**

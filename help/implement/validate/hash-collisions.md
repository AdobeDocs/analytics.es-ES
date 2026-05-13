---
title: Conflictos de hash
description: Describe lo que es un conflicto de hash y cómo se puede manifestar.
feature: Implementation Basics
exl-id: 693d5c03-4afa-4890-be4f-7dc58a1df553
role: Admin, Developer
TQID: https://experienceleague.adobe.com/yjYX-h-8jJA7k-jzRMOJ0l2BxN5-no2kCfySkGYss8w
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 9b4525e014170b72688044a6ead344b1bde8c39b
workflow-type: tm+mt
source-wordcount: 539
ht-degree: 5%

---

# Conflictos de hash

Las dimensiones en Adobe Analytics recopilan valores de cadena. A veces estas cadenas tienen cientos de caracteres, mientras que otras veces son cortas. Para mejorar el rendimiento, estos valores de cadena no se utilizan directamente en el procesamiento de intervalo de tiempo. En su lugar, se calcula un hash para cada valor, lo que produce un identificador de tamaño uniforme. Para la mayoría de los campos, el valor se convierte a minúsculas antes del hash, lo que reduce el número total de valores únicos. Todos los informes se ejecutan en estos valores con hash, lo que aumenta drásticamente su rendimiento.

Adobe Analytics mantiene una tabla hash independiente para cada variable y cada tabla se vuelve a crear cada mes. Dentro de cualquiera de esas tablas, dos valores de origen diferentes pueden producir ocasionalmente el mismo hash, conocido como *conflicto de hash*.

Los conflictos de hash pueden manifestarse en los informes de la siguiente manera:

* Si ve un informe a lo largo del tiempo y observa un pico inesperado, es posible que varios valores únicos para esa variable utilicen el mismo hash.
* Si utiliza un segmento y ve un valor inesperado, es posible que el elemento de dimensión inesperado utilice el mismo hash que otro elemento de dimensión que coincidió con el segmento.

## Probabilidades de un conflicto de hash

Adobe Analytics usa hashes de 32 bits para la mayoría de las dimensiones, lo que significa que hay 2<sup>32</sup> combinaciones de hash posibles (aproximadamente 4.300 millones). Las probabilidades aproximadas de encontrar un conflicto de hash basado en el número de valores únicos son las siguientes. Estas probabilidades se basan en una sola dimensión para un solo mes.

| Valores únicos | Probabilidades |
| --- | --- |
| 1.000 | 0.01% |
| 10.000 | 1% |
| 50 000 | 26% |
| 100.000 | 71% |

Similar a la [paradoja del cumpleaños](https://en.wikipedia.org/wiki/Birthday_problem), la probabilidad de que se produzcan conflictos de hash aumenta drásticamente a medida que aumenta el número de valores únicos. Con un millón de valores únicos, es probable que haya al menos 100 conflictos de hash para esa dimensión.

## Mitigación de conflictos de hash

Los conflictos de hash no se pueden eliminar por completo, pero su impacto en los informes se puede mitigar. La mayoría de los conflictos de hash se producen con dos valores poco comunes, que no tienen un impacto significativo en los informes. Incluso si un hash entra en conflicto con un valor común y poco común, el resultado es insignificante. Sin embargo, en casos excepcionales en los que dos valores populares experimentan un conflicto de hash, es posible ver su efecto con claridad. Adobe recomienda lo siguiente para reducir su efecto en los informes:

* **Cambiar el intervalo de fechas**: Las tablas hash cambian cada mes. Si se cambia el intervalo de fechas para que abarque otro mes, se pueden dar a cada valor hashes diferentes que no entren en conflicto. Suele ser la forma más rápida de borrar una anomalía visible de un informe específico.
* **Reduzca la cantidad de valores únicos**: Puede ajustar la implementación o usar [Reglas de procesamiento](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md) para ayudar a reducir la cantidad de valores únicos que recopila una dimensión. Por ejemplo, si la dimensión recopila una dirección URL, puede eliminar las cadenas de consulta o el protocolo.
* **Usar [Data Warehouse](/help/export/data-warehouse/data-warehouse.md) o [fuentes de datos](/help/export/analytics-data-feed/data-feed-overview.md)**: estas herramientas no dependen de las tablas hash.
* **Mover a [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html?lang=es)**: Customer Journey Analytics no tiene capa de hash y [no tiene límites de cardinalidad en las dimensiones](https://experienceleague.adobe.com/docs/analytics-platform/using/components/dimensions/high-cardinality.html). Considere pasar a este producto si los conflictos de hash o [[!UICONTROL Poco tráfico]](/help/technotes/low-traffic.md) afectan con frecuencia sus informes.

>[!MORELIKETHIS]
>
>* Valor de [[!UICONTROL poco tráfico] en Adobe Analytics](/help/technotes/low-traffic.md)
>* [Resumen de reglas de procesamiento](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)

<!-- https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=OmniArch&title=Uniques -->

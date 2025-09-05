---
title: Conflictos de hash
description: Describe lo que es un conflicto de hash y cómo se puede manifestar.
feature: Implementation Basics
exl-id: 693d5c03-4afa-4890-be4f-7dc58a1df553
role: Admin, Developer
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 6%

---

# Conflictos de hash

Las dimensiones en Adobe Analytics recopilan valores de cadena. A veces estas cadenas tienen cientos de caracteres, mientras que otras veces son cortas. Para mejorar el rendimiento, estos valores de cadena no se utilizan directamente en el procesamiento. En su lugar, se calcula un hash para cada valor a fin de que todos los valores tengan un tamaño uniforme. Todos los informes se ejecutan en estos valores con hash, lo que aumenta drásticamente su rendimiento.

Para la mayoría de los campos, la cadena primero se convierte a minúsculas. La conversión a minúsculas reduce el número de valores únicos. Los valores se colocan en hash mensualmente: en el caso de un valor determinado se utiliza el primer valor que se ve cada mes. De un mes a otro, existe una pequeña posibilidad de que dos valores de variables únicos tengan hash con el mismo valor. Esto se conoce como *conflicto de hash*.

Los conflictos de hash pueden manifestarse en los informes de la siguiente manera:

* Si ve un informe a lo largo del tiempo y observa un pico inesperado, es posible que varios valores únicos para esa variable utilicen el mismo hash.
* Si utiliza un segmento y ve un valor inesperado, es posible que el elemento de dimensión inesperado utilice el mismo hash que otro elemento de dimensión que coincidió con el segmento.

## Probabilidades de un conflicto de hash

Adobe Analytics usa hashes de 32 bits para la mayoría de las dimensiones, lo que significa que hay 2<sup>32</sup> combinaciones de hash posibles (aproximadamente 4.300 millones). Cada mes se crea una nueva tabla hash para cada dimensión. Las probabilidades aproximadas de encontrar un conflicto de hash basado en el número de valores únicos son las siguientes. Estas probabilidades se basan en una sola dimensión para un solo mes.

| Valores únicos | Probabilidades |
| --- | --- |
| 1000 | 0,01 % |
| 10.000 | 1 % |
| 50 000 | 26% |
| 100.000 | 71 % |

{style="table-layout:auto"}

Similar a la [paradoja del cumpleaños](https://en.wikipedia.org/wiki/Birthday_problem), la probabilidad de que se produzcan conflictos de hash aumenta drásticamente a medida que aumenta el número de valores únicos. Con un millón de valores únicos, es probable que haya al menos 100 conflictos de hash para esa dimensión.

## Mitigación de conflictos de hash

La mayoría de los conflictos de hash se producen con dos valores poco comunes, que no tienen un impacto significativo en los informes. Incluso si un hash entra en conflicto con un valor común y poco común, el resultado es insignificante. Sin embargo, en casos excepcionales en los que dos valores populares experimentan un conflicto de hash, es posible ver su efecto con claridad. Adobe recomienda lo siguiente para reducir su efecto en los informes:

* **Cambiar el intervalo de fechas**: Las tablas hash cambian cada mes. Si se cambia el intervalo de fechas para que abarque otro mes, se pueden dar a cada valor hashes diferentes que no entren en conflicto.
* **Reduzca la cantidad de valores únicos**: Puede ajustar la implementación o usar [Reglas de procesamiento](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md) para ayudar a reducir la cantidad de valores únicos que recopila una dimensión. Por ejemplo, si la dimensión recopila una dirección URL, puede eliminar las cadenas de consulta o el protocolo.

<!-- https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=OmniArch&title=Uniques -->

---
description: Vea los valores principales de una dimensión antes de utilizarla en un proyecto.
title: Vista preliminar de dimensiones
feature: Dimensions
role: User, Admin
exl-id: 897edc76-6744-4d8c-ab0e-20672838f7b3
source-git-commit: a629b2be66d9458bf10872a95aaec739aed9d791
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 21%

---

# Previsualización de dimensiones en Analysis Workspace

Puede usar la [información de componente](/help/analyze/analysis-workspace/components/use-components-in-workspace.md#component-info) de un componente para mostrar los elementos principales de una dimensión.

![Información de componente](assets/component-info.png)

<!--
Now, by default, we show dynamic values instead of static ones, with the option to turn them into static values. Other things to note:

* As your data updates, the dynamic dimension columns will update to show the current 5/15 dimension items.
* A dynamic dimension column that is copied or moved will become static.
* When hovering a static dimension column you will see a lock icon, indicating that the dimension is static.

![Dimension column popup highlighting the lock icon.](assets/dimension_static.png)

-->


## Mostrar los elementos de la dimensión

Cuando selecciona ![ChevronRight](/help/assets/icons/ChevronRight.svg) para una dimensión en el panel Componentes, aparece una lista de sus elementos de dimensión. La lista de elementos de dimensión generalmente muestra los elementos principales de los últimos 30 días. Cuando haya más elementos disponibles, fuera del intervalo de fechas seleccionado para el panel, seleccione el vínculo para mostrar más elementos. Por ejemplo, **[!UICONTROL mostrar elementos del mes pasado]**.

![Mostrar elementos de dimensión](assets/dimension-items.png)


<!--
# Preview dimensions

Hover over the information (i) icon next to a dimension. This shows the top 5 values for non-time dimensions (and 15 for time dimensions). We used to keep those values static (i.e., the 5 values picked never changed).

![](assets/dimension-preview.png)

Now, by default, we show dynamic values instead of static ones, with the option to turn them into static values. Other things to note:

* As your data updates, the dynamic dimension columns will update to show the current 5/15 dimension items.
* A dynamic dimension column that is copied or moved will become static.
* When hovering a static dimension column you will see a lock icon, indicating that the dimension is static.

![](assets/dimension_static.png)

## Show dimension items

When you hover over a dimension and click the grey right-arrow next to it, a list of its dimension items appears. Any list of dimension items usually shows the top items for the last 30 days.

If you scroll down to the bottom of the list, you see **[!UICONTROL Show Top Items From Last 18 Months]**. Click this option to see top dimension items from the last 547 days.

-->

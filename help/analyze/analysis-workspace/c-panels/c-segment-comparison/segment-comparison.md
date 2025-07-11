---
title: Información general del panel Comparación de segmentos
description: Aprenda a utilizar el panel de comparación de segmentos para comparar segmentos en Analysis Workspace.
keywords: Analysis Workspace;IQ de segmento
feature: Segmentation
role: User, Admin
exl-id: 1f5df6fb-1e9f-4b8f-885c-bf9e68d88c89
source-git-commit: b4c1636bdc9d5be522b16f945a46beabf4f7a733
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 76%

---

# Información general del panel de comparación de segmentos {#segment-comparison-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_segmentcomparison_button"
>title="Comparación de segmentos "
>abstract="Compare rápidamente dos segmentos en todos los puntos de datos para encontrar diferencias relevantes."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_segmentcomparison_panel"
>title="Panel de comparación de segmentos "
>abstract="Compare rápidamente dos segmentos en todos los puntos de datos para encontrar diferencias relevantes.<br/><br/>**Parámetros **<br/>**Añadir un segmento**: el primer segmento que desea analizar.<br/>**Comparar con**: el segundo segmento con el que desea comparar, se rellena automáticamente con *Todos los demás* (lo contrario al primer segmento). Si lo desea, puede reemplazar *Todos los demás* por un segmento diferente.<br/>**Configuración avanzada**: la posibilidad de excluir componentes del análisis en la comparación de segmentos."
<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_Este artículo documenta el panel Comparación de segmentos en_ ![Adobe Analytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**._<br/>_No hay un panel equivalente en_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**._

>[!ENDSHADEBOX]

El panel Comparación de segmentos detecta las diferencias estadísticamente más significativas entre un número ilimitado de segmentos. La función se repite mediante un análisis automatizado de todas las dimensiones y métricas a las que tiene acceso. La comparación revela automáticamente las características clave de los segmentos de audiencia que dirigen el KPI de su empresa y le permite ver cuánto se superponen los segmentos.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Comparación de segmentos](https://video.tv.adobe.com/v/23976?quality=12&learn=on){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]



## Usar

Para usar un panel **[!UICONTROL Atribución]**:

1. Cree un panel **[!UICONTROL Atribución]**. Para obtener información sobre cómo crear un panel, consulta [Crear un panel](../panels.md#create-a-panel).

1. Especifica la [entrada](#panel-input) para el panel.

1. Observa la [salida](#panel-output) del panel.



### Entrada de panel

Puede configurar el panel [!UICONTROL Comparación de segmentos] utilizando estos ajustes de entrada:

![Panel de entrada de comparación de segmentos](assets/segment-comparison-input.png)

| Entrada | Descripción |
| --- | --- |
| **[!UICONTROL Añadir un segmento]** | Seleccione la dimensión con la que desee comparar. |
| **[!UICONTROL Comparar con]** | Seleccione la dimensión que desee utilizar para comparar el segmento seleccionado inicialmente. Si no selecciona un segmento específico, se usará el segmento predeterminado **[!UICONTROL Todos los demás]**. |
| **[!UICONTROL Mostrar u ocultar ajustes avanzados]** | Seleccione **[!UICONTROL Mostrar ajustes avanzados]** para configurar **[!UICONTROL Componentes excluidos]**, seleccione **[!UICONTROL Ocultar ajustes avanzados]** para ocultar **[!UICONTROL Componentes excluidos]**. |
| **[!UICONTROL Componentes excluidos]** | Componentes que puede especificar, como **[!UICONTROL Dimensiones]**, **[!UICONTROL Métricas]** o **[!UICONTROL Segmentos]** para la exclusión.<br><ul><li>Arrastre y suelte una o más dimensiones, métricas o segmentos de los contenedores en el contenedor de **[!UICONTROL Componentes excluidos]**.</li><li>Para quitar un componente, seleccione el tipo (**[!UICONTROL Dimensión]** **[!UICONTROL Métricas]** o **[!UICONTROL Segmentos]**) y seleccione ![CrossSize75](/help/assets/icons/CrossSize75.svg) para quitarlo. Para quitar todos los componentes, seleccione **[!UICONTROL Borrar todo]**.</li><li>Para establecer la selección actual de dimensiones, métricas y segmentos como predeterminada, seleccione **[!UICONTROL Establecer como predeterminado]**.</li></ul> |

Seleccione **[!UICONTROL Generar]** para generar el panel.

### Salida del panel

Una vez que Adobe Analytics termina de analizar los dos segmentos deseados, los paneles de salida muestran los resultados a través de varias visualizaciones:

![Comparación de segmentos de resultado del panel](assets/segment-comparison-output.png)

| Visualización | Descripción |
|---|---|
| **[!UICONTROL Tamaño y superposición]** | Ilustra con una visualización [Venn](/help/analyze/analysis-workspace/visualizations/venn.md) los tamaños comparativos de cada segmento seleccionado y cuánto se solapan entre sí. |
| **[!UICONTROL Visitantes únicos para el primer segmento]** | Una visualización [Número de resumen](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) que muestra los visitantes únicos del primer segmento (en el ejemplo Visitas a una sola página) |
| **[!UICONTROL Visitantes únicos para el segundo segmento]** | Una visualización [Número de resumen](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) que muestra los visitantes únicos del segundo segmento (en el ejemplo Visitas por primera vez) |
| **[!UICONTROL Métricas principales con segmentos]** | Una [tabla de forma libre](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md) que muestra las principales métricas de los segmentos seleccionados. |
| **[!UICONTROL Métrica a lo largo del tiempo por segmento]** | Una visualización de [Línea](/help/analyze/analysis-workspace/visualizations/line.md) que muestra las métricas a lo largo del tiempo de los segmentos seleccionados. |
| **[!UICONTROL Elementos de dimensión principales con respecto a Segmentos]** | Una [tabla de forma libre](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md) que muestra los elementos de dimensión mixtos de los segmentos seleccionados. |
| **[!UICONTROL Elementos de dimensión por segmentos]** | Una visualización de [barras horizontales](/help/analyze/analysis-workspace/visualizations/horizontal-bar.md) que muestra los elementos de dimensión por segmento. |
| **[!UICONTROL Segmentos principales con respecto a Segmentos]** | Una [Tabla de forma libre](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md) que muestra los segmentos principales con respecto a los Segmentos. |
| **[!UICONTROL Superposición de segmentos]** | Una visualización [Venn](/help/analyze/analysis-workspace/visualizations/venn.md) que muestra la superposición de segmentos. |

Use ![Editar](/help/assets/icons/Edit.svg) para reconfigurar y regenerar el panel.


<!--
#### Size and overlap

Illustrates the comparative sizes of each selected segment and how much they overlap with each other using a venn diagram. You can hover over the visual to see how many visitors were in each overlapping or non-overlapping section. You can also right click on the overlap to create a brand new segment for further analysis. If the two segments are mutually exclusive, no overlap is shown between the two circles (typically seen with segments using a hit container).

![Size and overlap](assets/size-overlap.png)

#### Population summaries

To the right of the Size and Overlap visualization, the total unique visitor count in each segment and overlap is shown.

![Population summaries](assets/population_summaries.png)

#### Top metrics

Displays the most statistically significant metrics between the two segments. Each row in this table represents a differentiating metric, ranked by how different it is between each segment. A difference score of 1 means it is statistically significant, while a difference score of 0 means there is no statistical significance.

This visualization is similar to freeform tables in Analysis Workspace. If deeper analysis on a specific metric is desired, hover over a line item and click 'Create visual'. A new table is created to analyze that specific metric. If a metric is irrelevant to your analysis, hover over the line item and click the 'X' to remove it.

>[!NOTE]
>
>Metrics added to this table after the segment comparison has finished do not receive a Difference Score.

![Top metrics](assets/top-metrics.png)

#### Metric over time by segment

To the right of the metrics table is a linked visualization. You can click a line item in the table on the left, and this visualization updates to show that metric trended over time.

![Top metrics line](assets/linked-viz.png)

#### Top dimensions

Shows the most statistically significant dimension items across all of your dimensions. Each row shows the percentage of each segment exhibiting this dimension item. For example, this table might reveal that 100% of visitors in 'Segment A' had the dimension item 'Browser Type: Google', whereas only 19.6% of 'Segment B' had this dimension item. A difference score of 1 means it is statistically significant, while a difference score of 0 means there is no statistical significance.

This visualization is similar to freeform tables in Analysis Workspace. If deeper analysis on a specific dimension item is desired, hover over a line item and click 'Create visual'. A new table is created to analyze that specific dimension item. If a dimension item is irrelevant to your analysis, hover over the line item and click the 'X' to remove it.

>[!NOTE]
>
>Dimension items added to this table after the segment comparison has finished do not receive a Difference Score.

![Top dimensions](assets/top-dimension-item1.png)

#### Dimension items by segment

To the right of the dimensions table is a linked bar chart visualization. It shows all displayed dimension items in a bar chart. Clicking a line item in the table on the left updates the visualization on the right.

![Top dimensions bar chart](assets/top-dimension-item.png)

#### Top segments

Shows which other segments (other than the two segments selected for comparison) have statistically significant overlap. For example, this table can show that a third segment, 'Repeat Visitors', overlaps highly with 'Segment A' but does not overlap with 'Segment B'. A difference score of 1 means it is statistically significant, while a difference score of 0 means there is no statistical significance.

This visualization is similar to freeform tables in Analysis Workspace. If deeper analysis on a specific segment is desired, hover over a line item and click 'Create visual'. A new table is created to analyze that specific segment. If a segment is irrelevant to your analysis, hover over the line item and click the 'X' to remove it.

>[!NOTE]
>
>Segments added to this table after the segment comparison has finished do not receive a Difference Score.

![Top segments](assets/top-segments.png)

#### Segment overlap

To the right of the segments table is a linked venn diagram visualization. It shows the most statistically significant segment applied to your compared segments. For example, 'Segment A' + 'Statistically significant segment' vs. 'Segment B' + 'Statistically significant segment'. Clicking a segment line item in the table on the left updates the venn diagram on the right.

![Top segments venn diagram](assets/segment-overlap.png)

-->

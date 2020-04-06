---
description: 'null'
title: Ejecutar análisis de contribución
uuid: 5282a5f9-0771-4974-93cb-335204bde114
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Ejecutar análisis de contribución

La Análisis de contribución es un proceso intensivo de aprendizaje automático diseñado para descubrir los factores que contribuyen a una anomalía observada en Adobe Analytics. El propósito es ayudar al usuario a encontrar áreas de interés u oportunidades de análisis adicional mucho más rápido de lo que sería posible de otro modo.

## Ejecutar análisis de contribución {#section_7D2C5E48A5664727941DF4C90976D9DC}

Hay dos formas de invocar el análisis de contribución en un proyecto:

* In a freeform table with daily granularity, right-click any row and select **[!UICONTROL Run Contribution Analysis]**. Incluso puede ejecutarlo en filas que no muestren ninguna anomalía.

   >[!NOTE]
   >
   >Actualmente únicamente se admite el análisis de contribución con granularidad diaria.

   ![](assets/run_ca.png)

* En un gráfico de líneas, sitúese sobre un punto de datos de anomalía. Click the **[!UICONTROL Analyze]** link that appears.

   ![](assets/contribution-analysis.png)

1. (Optional) After you have clicked **[!UICONTROL Run Contribution Analysis]** in either the line chart or a table, you can narrow the scope of (and thus speed up) the analysis by [excluding dimensions](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/run-contribution-analysis.md#section_F6932F4BF74544B5872164E7B1E0C6FC).

1. Espere mientras se carga la análisis de contribución. Esto podría llevar una considerable cantidad de tiempo, según el tamaño del grupo de informes y la cantidad de dimensiones. La análisis de contribución realiza la análisis en los 50.000 elementos principales por dimensión.
1. Análisis Workspace carga un nuevo panel de Análisis de contribución directamente en este proyecto. Verá muchos paneles familiares si ya ha utilizado la Análisis de contribución en Informes y análisis anteriormente:

   * Una visualización que muestra el número de **visitas** ese día.
   * Línea **de tendencias de** visitas mensual para contexto.
   * **Los elementos** principales que contribuyeron a esta anomalía, ordenados por la puntuación [de la](https://marketing.adobe.com/resources/help/es_ES/analytics/contribution/ca_contribution_score.html)contribución, además de la métrica en cuestión y una métrica Visitantes únicos para poner la métrica en contexto desde una perspectiva de tamaño.

   * La tabla Segmentos [](https://marketing.adobe.com/resources/help/es_ES/analytics/contribution/ca_workflow_premium.html) generados (grupos de elementos principales) identifica las asociaciones de los elementos principales según la puntuación de contribución, las ocurrencias de anomalías y el porcentaje general que contribuye a la métrica anómala. A continuación, esto se captura como un segmento de audiencia (segmento de contribución 1, segmento de contribución 2, etc.). Al hacer clic en el botón &quot;i&quot; (información), obtendrá una vista de la definición de cada segmento automático, incluidos los elementos principales de los que está compuesto:

      ![](assets/auto_segment.png)

1. Como la análisis de contribución ahora forma parte de Espacio de trabajo de Análisis, puede aprovechar varias de sus funciones desde el menú que aparece al hacer clic con el botón derecho de una tabla para que su análisis sea aún más significativa, como por ejemplo:

   * [Desglosar todos los elementos de la dimensión por otra dimensión.](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md)
   * [Realizar la tendencia de una fila o más.](/help/analyze/analysis-workspace/analysis-workspace-features.md#section_34930C967C104C2B9092BA8DCF2BF81A)
   * [Añadir nuevas visualizaciones.](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)
   * [Crear alertas.](/help/components/c-alerts/intellligent-alerts.md)
   * [Crear o comparar segmentos.](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md)

>[!NOTE] La anomalía analizada se resalta con un punto azul en el análisis de contribución y en los proyectos de alerta inteligente vinculados con ella. Esto proporciona una indicación más clara de la anomalía que se está analizando.

## Excluir dimensiones del análisis de contribución {#section_F6932F4BF74544B5872164E7B1E0C6FC}

Puede haber ocasiones en las que desea excluir algunas dimensiones del análisis de contribución. Por ejemplo, puede que no le importe ninguna dimensión relacionada con el navegador o el hardware y desea acelerar la análisis eliminándola.

1. Después de hacer clic **[!UICONTROL Run Contribution Analysis]** (o **[!UICONTROL Analyze]** en un gráfico de líneas), se muestra el **[!UICONTROL Excluded Dimensions]** panel.

1. Basta con arrastrar cualquier dimensión no deseada al **[!UICONTROL Excluded Dimensions]** panel y, a continuación, guardar la lista haciendo clic en **[!UICONTROL Set as Default]**. Or, click **[!UICONTROL Clear All]** to start over with selecting dimensions to exclude.

   ![](assets/exclude_dimensions.png)

1. After you have added dimensions to exclude (or chosen not to), click **[!UICONTROL Run Contribution Analysis]** again.
1. Si alguna vez necesita revisar la lista de dimensiones excluidas, haga doble clic en Dimensiones y aparecerá la lista de dimensiones excluidas:

   ![](assets/excluded-dimensions.png)

1. Just delete any unwanted dimensions by clicking the x next to them, then save the list by clicking **[!UICONTROL Set as Default]**.


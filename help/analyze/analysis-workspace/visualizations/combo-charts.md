---
description: Aprenda a visualizar datos de comparación en Analysis Workspace, como comparaciones con el mes o el año pasado, etc.
title: Combo
feature: Visualizations
role: User, Admin
exl-id: 08e49857-aa58-4527-bdfd-b1663a75a02b
source-git-commit: bf8bc40e3ec325e8e70081955fb533eee66a1734
workflow-type: tm+mt
source-wordcount: '603'
ht-degree: 96%

---

# Combo {#combo}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_combo_button"
>title="Combo"
>abstract="Cree una visualización de gráfico combinado rápido, sin necesidad de crear primero una tabla de forma libre."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Este artículo documenta la visualización combinada en_ ![Adobe Analytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics**._

_Consulte [Combo](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-workspace/visualizations/combo-charts) para la versión de_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics** de este artículo._

>[!ENDSHADEBOX]


La visualización ![Gráfico combinado](/help/assets/icons/ComboChart.svg) **[!UICONTROL Combo]** facilita la generación rápida de una visualización de comparación sin tener que generar una tabla primero. Puede ver fácilmente las tendencias en sus datos en una combinación de líneas/barras.

Utilice un [!UICONTROL Combo] para lo siguiente:

* Compare los pedidos de esta semana con los del mismo período del mes pasado (y del año pasado).
* Analice y compare rápidamente varias métricas (por ejemplo, [!UICONTROL Personas] e [!UICONTROL Ingresos]) en el mismo gráfico.
* Analizar una métrica con una función (como [!UICONTROL Promedio acumulado]) en un horizonte temporal.

Tenga en cuenta lo siguiente:

* Puede agregar varias comparaciones en un solo [!UICONTROL Gráfico combinado].
* Si añade una o más comparaciones, deben ser del mismo tipo, como una [!UICONTROL Comparación temporal].
* Se pueden añadir hasta cinco comparaciones.
* Puede aplicar hasta tres filtros (segmentos) a una métrica.
* Las métricas calculadas no son compatibles con los gráficos combinados.

## Utiliza

1. Añada una visualización ![Comentario](/help/assets/icons/ComboChart.svg) [!UICONTROL Combo]. Consulte [Añadir una visualización a un panel](freeform-analysis-visualizations.md#add-visualizations-to-a-panel)

1. En las listas desplegables, seleccione una dimensión para el eje X y una métrica para el eje Y.

1. Seleccione el tipo de [!UICONTROL Comparación de líneas] que desea utilizar.

   | Tipo de comparación de líneas | Definición |
   | --- | --- |
   | **[!UICONTROL Comparación del tiempo]** | El tipo de comparación más común: comparar este período de tiempo con hace cuatro semanas, por ejemplo. Si ha seleccionado [!UICONTROL Comparación temporal], realice una selección secundaria de qué período de tiempo quiere comparar.<p>![Comparación lineal con el período de tiempo seleccionado y el campo de selección secundario para el período de tiempo.](assets/combo-time-period.png) |
   | **[!UICONTROL Función]** | Puede introducir una función como [!UICONTROL Promedio] en la comparación. Consulte la lista de [funciones admitidas](#supported-functions).<p>![Menú desplegable de comparación de líneas que muestra las funciones seleccionadas y una lista de las funciones compatibles disponibles.](assets/combo-functions.png) |
   | **[!UICONTROL Métrica secundaria]** | Por ejemplo, podría comparar [!UICONTROL Ingresos] con otra métrica.<p>![Gráfico combinado que compara dos métricas.](assets/combo-2metrics-settings.png) |

   {style="table-layout:auto"}

1. Seleccione **[!UICONTROL Generar]**.

   El resultado es similar al siguiente:

   ![Gráfico combinado que muestra el período actual en un gráfico de barras y un período de comparación en el gráfico de líneas ](assets/combo-output.png)

   El periodo actual se muestra en el gráfico de barras. El gráfico de líneas representa el periodo de comparación. Los puntos en el gráfico de líneas se conocen como *marcadores*.

## Funciones compatibles

Si selecciona **[!UICONTROL Función]** como el [!UICONTROL Tipo de comparación de líneas], se devuelve una función de la métrica que haya elegido.

| Función | Definición |
| --- | --- |
| **[!UICONTROL Suma de la columna]** | Suma todos los valores numéricos de una métrica dentro de una columna (entre los elementos de una dimensión). |
| **[!UICONTROL Promedio acumulado]** | Devuelve el promedio de las últimas N filas. |
| **[!UICONTROL Mediana]** | Devuelve la mediana de una métrica en una columna. La mediana es el número situado en medio de un conjunto de números. La mitad de los números tienen valores mayores o iguales a la mediana y la mitad son menores o iguales a la mediana. |
| **[!UICONTROL Acumulativo]** | La suma acumulada de N filas. |
| **[!UICONTROL Máximo de la columna]** | Devuelve el mayor valor en un conjunto de elementos de una dimensión para una columna de métrica. |
| **[!UICONTROL Media]** | Devuelve la media aritmética o el promedio de una métrica. |
| **[!UICONTROL Mínimo de columna]** | Devuelve el menor valor en un conjunto de elementos de una dimensión para una columna de métrica. |

{style="table-layout:auto"}

Este es un ejemplo de la media acumulada de la métrica Ingresos:

![Gráfico combinado que muestra el promedio acumulado](assets/combo-cumul-avg.png)

Este es un ejemplo de un gráfico combinado con las funciones Media acumulada y Media:

![Gráfico combinado que muestra las funciones media y media acumulativa.](assets/combo-three-functions.png)

>[!MORELIKETHIS]
>
>[Añadir una visualización a un panel](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>&#x200B;>[Configuración de visualización](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>&#x200B;>[Menú contextual de visualización](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

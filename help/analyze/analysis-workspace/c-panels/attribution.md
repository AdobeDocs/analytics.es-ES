---
title: Panel de atribución
description: Aprenda a utilizar e interpretar el panel de atribución en Analysis Workspace.
feature: Attribution
role: User, Admin
exl-id: 96ce3cb9-7753-4ec0-b551-e70a1508e3b7
TQID: https://experienceleague.adobe.com/u7h9V-K7lJQnVJuo-Hwk4xtB7lBW-JlH2W2pFGq0TgQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4
  - id: e38cbddc-1633-4cd5-bed5-9f289f2a6029
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5520579-b31f-4df7-9281-f0d9f91e2edc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 714
ht-degree: 91%

---

# Panel de atribución {#attribution-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_attribution_button"
>title="Atribución"
>abstract="Compare y visualice rápidamente los modelos de atribución utilizando cualquier dimensión y métrica de conversión"
>additional-url="https://www.youtube.com/watch?v=Yu0hy2klzA0" text="Panel de Attribution IQ"

>[!CONTEXTUALHELP]
>id="workspace_attribution_panel"
>title="Panel de atribución"
>abstract="Compare y visualice rápidamente cualquier número de modelos de atribución utilizando cualquier dimensión y métrica de conversión.<br/><br/>**Parámetros &#x200B;**<br/>**Canal**<br/> La dimensión contra la que atribuir. Esta dimensión puede ser canales de marketing, campañas o cualquier otra dimensión.<br/>**Modelos**<br/> El modelo determina cómo se asigna crédito a los puntos de contacto.<br/>**Ventana retroactiva**<br/> Este ajuste determina la ventana de atribución de datos que se aplica a cada conversión."
>additional-url="https://www.youtube.com/watch?v=Yu0hy2klzA0" text="Panel de Attribution IQ"

<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_Este artículo documenta el panel Atribución en_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics**._<br/>_Vea [Panel de atribución](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-workspace/panels/attribution) para la_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics** versión de este artículo._

>[!ENDSHADEBOX]

El panel **[!UICONTROL Atribución]** es una forma sencilla de generar un análisis comparando varios modelos de atribución. El panel le proporciona un espacio de trabajo dedicado para utilizar y comparar modelos de atribución.

Adobe Analytics mejora la atribución al permitir lo siguiente:

* Definir la atribución más allá del contenido multimedia de pago: cualquier dimensión, métrica, canal o evento puede aplicarse a modelos (por ejemplo, búsqueda interna), no solo campañas de marketing.
* Utilizar la comparación de modelos de atribución sin límites: compare dinámicamente todos los modelos que desee.
* Evitar cambios de implementación: con el procesamiento de tiempo de los informes y las sesiones según el contexto, el contexto del recorrido del cliente puede incorporarse y aplicarse en tiempo de ejecución.
* Construir la sesión más adecuada para su escenario de atribución.
* Desglosar la atribución por segmentos: compare fácilmente el rendimiento de sus canales de marketing en cualquier segmento importante (por ejemplo, clientes nuevos frente a repetidos, producto X frente a producto Y, nivel de lealtad o CLV).
* Inspeccionar análisis de canales cruzados y de múltiples contactos mediante Diagramas de Venn e Histogramas, y resultados de atribución de tendencias.
* Analizar visualmente secuencias de marketing clave: explore las rutas que generaron una conversión visualmente con las visualizaciones de visitas en el orden previsto y flujo de varios nodos.
* Generar métricas calculadas: Utilice todos los métodos de asignación de atribuciones que desee.

## Utiliza

Para usar un panel **[!UICONTROL Atribución]**:

1. Cree un panel **[!UICONTROL Atribución]**. Para obtener información sobre cómo crear un panel, consulta [Crear un panel](panels.md#create-a-panel).

1. Especifica la [entrada](#panel-input) para el panel.

1. Observa la [salida](#panel-output) del panel.

### Entrada de panel

Puede configurar el panel Atribución con esta configuración de entrada:

1. Añada una **[!UICONTROL métrica de éxito]** y una dimensión del **[!UICONTROL canal]** que desee atribuir. Algunos ejemplos son Canales de marketing o dimensiones personalizadas, como las promociones internas.

   ![Ventana del panel Atribución que muestra varias dimensiones y métricas seleccionadas.](assets/attribution-panel.png)

1. Seleccione uno o más [modelos de atribución](#attribution-models) de **[!UICONTROL modelos incluidos]**, el [contenedor](#container) de **[!UICONTROL Contenedor]** y una [ventana retrospectiva](#lookback-window) de **[!UICONTROL ventana retrospectiva]** que desee usar para la comparación.

1. Seleccione **[!UICONTROL Generar]** para generar las visualizaciones en el panel.

### Salida del panel

El panel **[!UICONTROL Atribución]** devuelve un conjunto completo de datos y visualizaciones que comparan la atribución para la dimensión y la métrica seleccionadas.

![Visualizaciones del panel Atribución que comparan métricas y dimensiones seleccionadas.](assets/attr_panel_vizs.png)

### Visualizaciones de atribución

La siguiente visualización forma parte de la salida del panel.

* **Métrica total**: El número total de conversiones que ocurrieron durante la ventana de tiempo de creación de informes y que se atribuyen a la dimensión seleccionada.
* **Barra comparativa de la atribución**: Compara visualmente las conversiones atribuidas en cada uno de los elementos de dimensión de la dimensión seleccionada. Cada color de barra representa un modelo de atribución distinto.
* **Tabla comparativa de la atribución**: Muestra los mismos datos que el gráfico de barras, representados como una tabla. Al seleccionar distintas columnas o filas en esta tabla, se filtra el gráfico de barras, así como varias de las demás visualizaciones del panel. Esta tabla actúa de manera similar a cualquier otra tabla de forma libre en Workspace, lo que le permite añadir componentes como métricas, segmentos o desgloses.
* **Diagrama de superposición**: Un diagrama de Venn que muestra los tres elementos de dimensión principales y la frecuencia con la que participan conjuntamente en una conversión. Por ejemplo, el tamaño del solapamiento de burbujas indica con qué frecuencia ocurrieron las conversiones cuando una persona estuvo expuesta a ambos elementos de dimensión. Si se seleccionan otras filas en la Tabla de forma libre adyacente, se actualizará la visualización para reflejar su selección.
* **Detalles de rendimiento**: una visualización de puntos para comparar visualmente hasta tres modelos de atribución.
* **Rendimiento de tendencias**: Muestra la tendencia de las conversiones atribuidas para el elemento de dimensión principal. Si se seleccionan otras filas en la Tabla de forma libre adyacente, se actualizará la visualización para reflejar su selección.
* **Flujo**: le permite ver con qué canales se interactúa con más frecuencia y en qué orden a lo largo del recorrido de una persona.

## Modelo de atribución

{{attribution-models-details}}

## Contenedor

{{attribution-container}}

## Ventana de retroactividad

{{attribution-lookback-window}}

## Ejemplo

{{attribution-example}}

>[!MORELIKETHIS]
>
> [Crear un panel](/help/analyze/analysis-workspace/c-panels/panels.md#create-a-panel)
>

<!--
# Attribution panel

The [!UICONTROL Attribution] panel is an easy way to build an analysis comparing various attribution models. It is a feature in [Attribution](/help/analyze/analysis-workspace/attribution/overview.md) that gives you a dedicated workspace to use and compare attribution models.

>[!VIDEO](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/attribution-iq/using-the-attribution-iq-panel)

## Create an attribution panel

1. Click the panel icon on the left.
1. Drag the [!UICONTROL Attribution] panel into your Analysis Workspace Project.

   ![New attribution panel](assets/Attribution_Panel_1.png)

1. Add a metric that you want to attribute and add any dimension to attribute against. Examples include Marketing Channels or custom dimensions, such as internal promotions.

   ![Select dimension and metric](assets/attribution_panel2.png)

1. Select the [attribution models and lookback window](../attribution/models.md) you want to compare.

1. The Attribution panel returns a rich set of data and visualizations that compare attribution for the selected dimension and metric.

   ![Attribution visualizations](assets/attr_panel_vizs.png)

## Attribution visualizations

* **Total metric**: The total number of conversions that occurred over the reporting time window. These are the conversions that are attributed across the dimension that you selected.
* **Attribution Comparison Bar**: Visually compares the attributed conversions across each of the dimension items from your selected dimension. Each bar color represents a distinct attribution model.
* **Attribution Comparison Table**: Shows the same data as the bar chart, represented as a table. Selecting different columns or rows in this table filters the bar chart as well as several of the other visualizations in the panel. This table acts similar to any other Freeform Table in Workspace - allowing you to add components such as metrics, segments, or breakdowns.
* **Overlap Diagram**: A Venn Diagram showing the top three dimension items and how often they participate jointly in a conversion. For example, the size of the bubble overlap indicates how often conversions occurred when a visitor was exposed to both dimension items. Selecting other rows in the adjacent Freeform table updates the visualization to reflect your selection.
* **Performance Detail**: Lets you to compare up to three attribution models visually using a scatter plot.
* **Trended Performance**: By default, shows the conversion performance trend by attribution model for the first dimension listed in the adjacent Freeform table. You can select different dimension rows in the Freeform table to show the trend for the selected dimensions (such as Total Revenue for each attribution model for Social Campaigns and Paid Search). Alternately, you can select cells in the columns for any metric and attribution type combinations in the Freeform table to see the trended performance by dimension value for the specified attribution models (such as Total Revenue by Marketing Channel using Last Touch and First Touch attribution).
* **Flow**: Lets you see which channels are interacted with most commonly, and in what order across a visitor's journey.

-->
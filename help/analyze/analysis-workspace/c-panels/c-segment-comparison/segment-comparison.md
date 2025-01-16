---
title: Información general del panel de comparación de segmentos
description: Aprenda a utilizar el panel de comparación de segmentos, que forma parte de IQ de segmento en Analysis Workspace.
keywords: Analysis Workspace;IQ de segmento
feature: Segmentation
role: User, Admin
exl-id: 1f5df6fb-1e9f-4b8f-885c-bf9e68d88c89
source-git-commit: 60836f5632cfd19d94f33441eaa9d949609d5712
workflow-type: tm+mt
source-wordcount: '1223'
ht-degree: 92%

---

# Información general del panel de comparación de segmentos {#segment-comparison-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_segmentcomparison_button"
>title="Comparación de segmentos"
>abstract="Compare rápidamente dos segmentos en todos los puntos de datos para encontrar automáticamente diferencias relevantes."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_segmentcomparison_panel"
>title="Panel de comparación de segmentos"
>abstract="Compare rápidamente dos segmentos en todos los puntos de datos para encontrar automáticamente diferencias relevantes.<br/><br/>**Parámetros **<br/>**Agregar un segmento**: El primer segmento que desea analizar.<br/>**Comparar con**: El segundo segmento con el que desea comparar. Esto se rellenará automáticamente con *Todos los demás*, que es lo contrario de su primer segmento. Si lo desea, puede reemplazarlo por un segmento diferente.<br/>**Configuración avanzada**: La capacidad para excluir componentes del análisis en la comparación de segmentos."
<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

*Este artículo describe el panel Comparación de segmentos en **Adobe Analytics**.<br/>No hay ningún panel equivalente en **Customer Journey Analytics**.*

>[!ENDSHADEBOX]

El panel Comparación de segmentos es una parte de la herramienta de [IQ de segmento](../../segment-iq.md) que detecta las diferencias estadísticamente más significativas entre un número ilimitado de segmentos. La función se repite mediante un análisis automatizado de todas las dimensiones y métricas a las que tiene acceso. De forma automática, muestra las características clave de los segmentos de audiencia que dirigen el KPI de su empresa y le permite observar cuánto se superponen los segmentos.

+++ Este es un vídeo sobre la comparación de segmentos:

>[!VIDEO](https://video.tv.adobe.com/v/23976/?quality=12)

+++

## Utiliza

Para usar un panel **[!UICONTROL Atribución]**:

1. Cree un panel de **[!UICONTROL Atribución]**. Para obtener información sobre cómo crear un panel, consulta [Crear un panel](../panels.md#create-a-panel).

1. Especifica la [entrada](#panel-input) para el panel.

1. Observa la [salida](#panel-output) del panel.



### Entrada de panel

![Comparar panel](assets/seg-compare-panel.png)

1. Seleccione segmentos para comparar y suéltelos en el panel.

   ![Comparar audiencias](assets/compare-audiences.png)

   Después de arrastrar un segmento al panel, Analytics crea automáticamente un segmento [!UICONTROL “Todos los demás”] que incluye a todos los que NO están en el segmento que ha elegido. Se trata de un segmento que se utiliza con frecuencia en el panel de comparación, pero puede eliminarlo y comparar otro segmento de su elección.

   ![Todos los demás](assets/everyone-else.png)

1. Una vez que haya determinado qué dos segmentos comparar, haga clic en [!UICONTROL Generar].

   Esta acción inicia un proceso backend que busca diferencias estadísticas entre los dos segmentos seleccionados y todas las dimensiones, métricas y otros segmentos. Una barra de progreso en la parte superior del panel indica el tiempo restante hasta que se analizan todas las métricas y dimensiones. Las métricas, dimensiones y segmentos utilizados con más frecuencia tienen prioridad para ejecutarse primero, de modo que los resultados más relevantes se devuelvan de manera oportuna.

## Excluir componentes de comparación

A veces se desea excluir algunas dimensiones, métricas o segmentos de las comparaciones de segmentos. Por ejemplo, desea comparar el segmento “Usuarios móviles de EE. UU.” con “Usuarios móviles alemanes”. Incluir dimensiones relacionadas con la geografía no tendría sentido, ya que estos segmentos ya implican esas diferencias.

1. Una vez que los dos segmentos deseados estén en el panel, haga clic en [!UICONTROL “Mostrar opciones avanzadas”].
1. Arrastre y suelte los componentes que desea excluir en cualquier sitio del panel [!UICONTROL Componentes excluidos].

   ![Componentes excluidos](assets/excluded-components.png)

Haga clic en [!UICONTROL Establecer como predeterminado] para excluir automáticamente los componentes actuales en todas las comparaciones de segmentos futuras. Si desea editar componentes excluidos, haga clic en un tipo de componente y, a continuación, haga clic en la “X” situada junto a un componente para volver a incluirlos en el análisis. Haga clic en “Borrar todo” para volver a incluir todos los componentes en la comparación de segmentos.

![Dimensiones excluidas](assets/excluded-dimensions.png)

### Salida de panel

Una vez que Adobe termina de analizar los dos segmentos deseados, muestra sus resultados a través de varias visualizaciones:

![Visualizaciones 1](assets/new-viz.png)

![Visualizaciones 2](assets/new-viz2.png)

#### Tamaño y superposición

Ilustra los tamaños comparativos de cada segmento seleccionado y cuánto se superponen entre sí mediante un diagrama de Venn. Puede situarse sobre la imagen para ver cuántos visitantes estaban en cada sección superpuesta o no superpuesta. También puede hacer clic en la superposición para crear un segmento totalmente nuevo si desea hacer un análisis en mayor profundidad. Si los dos segmentos son mutuamente excluyentes, no se muestra ninguna superposición entre los dos círculos (normalmente se ve con segmentos que utilizan un contenedor de visita individual).

![Tamaño y superposición](assets/size-overlap.png)

#### Resúmenes de población

A la derecha de la visualización Tamaño y superposición, se muestra la cantidad de visitantes únicos total en cada segmento y superposición.

![Resúmenes de población](assets/population_summaries.png)

#### Métricas principales

Muestra las métricas más significativas estadísticamente entre los dos segmentos. Cada fila de dicha tabla representa una métrica diferenciadora, ordenada según lo diferente que sea de cada segmento. Una puntuación de diferencia de 1 significa que tiene relevancia estadística, mientras que una puntuación de diferencia de 0 significa que no tiene relevancia estadística.

Esta visualización es similar a las tablas improvisada en Analysis Workspace. Si desea realizar un análisis más profundo de una métrica específica, pase el ratón sobre un elemento de línea y haga clic en “Crear imagen”. Se crea una nueva tabla para analizar esa métrica específica. Si una métrica no es relevante para el análisis, pase el ratón sobre el elemento de línea y haga clic en la “X” para eliminarla.

>[!NOTE]
>
>Las métricas que se agreguen a esta tabla una vez finalizada la comparación de segmentos no reciben una puntuación de diferencia.

![Métricas principales](assets/top-metrics.png)

#### Métrica a lo largo del tiempo por segmento

A la derecha de la tabla de métricas se encuentra la visualización vinculada. Puede hacer clic en un elemento de línea en la tabla de la izquierda y esta visualización se actualiza para mostrar esa métrica con las tendencias históricas.

![Línea de métricas principales](assets/linked-viz.png)

#### Dimensiones principales

Muestra los elementos de dimensión más significativos estadísticamente en todas las dimensiones. Cada fila muestra el porcentaje de cada segmento con este elemento de dimensión. Por ejemplo, esta tabla podría revelar que el 100% de los visitantes del segmento A tenían el elemento de dimensión “Tipo de explorador: Google”, mientras que solo el 19,6% del “segmento B” tenía este elemento de dimensión. Una puntuación de diferencia de 1 significa que tiene relevancia estadística, mientras que una puntuación de diferencia de 0 significa que no tiene relevancia estadística.

Esta visualización es similar a las tablas improvisada en Analysis Workspace. Si desea realizar un análisis más profundo de un elemento de dimensión específico, pase el ratón sobre un elemento de línea y haga clic en “Crear elemento visual”. Se crea una nueva tabla para analizar ese elemento de dimensión específico. Si un elemento de dimensión es irrelevante para el análisis, pase el ratón sobre el elemento de línea y haga clic en la “X” para eliminarlo.

>[!NOTE]
>
>Los elementos de dimensión que se agreguen a esta tabla después de que la comparación de segmentos haya finalizado no reciben una puntuación de diferencia.

![Dimensiones principales](assets/top-dimension-item1.png)

#### Elementos de dimensión por segmento

A la derecha de la tabla de dimensiones se encuentra la visualización de gráfico de barras vinculada. En ella aparecen todos los elementos de dimensión en un gráfico de barras. Al hacer clic en un elemento de línea en la tabla de la izquierda, se actualiza la visualización de la derecha.

![Gráfico de barras de dimensiones principales](assets/top-dimension-item.png)

#### Segmentos principales

Muestra qué otros segmentos (que no sean los dos seleccionados para la comparación) tienen una superposición estadísticamente significativa. Por ejemplo: esta tabla puede mostrar que un tercer segmento, “Visitantes repetidos”, se superpone con el segmento A pero no con el segmento B. Una puntuación de diferencia de 1 significa que tiene relevancia estadística, mientras que una puntuación de diferencia de 0 significa que no tiene relevancia estadística.

Esta visualización es similar a las tablas improvisada en Analysis Workspace. Si desea realizar un análisis más profundo de un segmento específico, pase el ratón sobre un elemento de línea y haga clic en “Crear elemento visual”. Se crea una nueva tabla para analizar ese segmento específico. Si un segmento no es relevante para el análisis, pase el ratón sobre el elemento de línea y haga clic en la “X” para eliminarlo.

>[!NOTE]
>
>Los segmentos que se agreguen a esta tabla después de que la comparación de segmentos haya finalizado no reciben una puntuación de diferencia.

![Segmentos principales](assets/top-segments.png)

#### Superposición de segmentos

A la derecha de la tabla de segmentos se encuentra la visualización de diagrama de Venn vinculada. Muestra el segmento más significativo estadísticamente aplicado a los segmentos comparados. Por ejemplo, “Segmento A” + “Segmento estadísticamente significativo” vs. “Segmento B” + “Segmento estadísticamente significativo”. Al hacer clic en un elemento de línea de segmento en la tabla de la izquierda, se actualiza el diagrama de Venn de la derecha.

![Diagrama de Venn de segmentos principales](assets/segment-overlap.png)

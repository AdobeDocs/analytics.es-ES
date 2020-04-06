---
description: Un histograma es un nuevo tipo de visualización en Análisis Workspace.
title: Histograma
uuid: 8a6bd2c4-da15-4f64-b889-ab9add685046
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Histograma

Un histograma es similar a un gráfico de barras, pero agrupa los números en intervalos (bloques). Analytics automatiza el &quot;agrupamiento&quot; de números en intervalos, pero puede cambiar la configuración en Configuración [avanzada](#section_09D774C584864D4CA6B5672DC2927477).

## Crear un histograma {#section_74647707CC984A1CB6D3097F43A30B45}

Para crear un histograma:

1. Click **[!UICONTROL Visualizations]** in the left rail.
1. Drag **[!UICONTROL Histogram]** to the panel.
1. Choose a Metric to drag to the Histogram visualization and click **[!UICONTROL Build]**.

![](assets/histogram.png)

>[!NOTE] Los histogramas únicamente admiten métricas estándar, pero no métricas calculadas.

Aquí hemos utilizado la métrica Vistas de página por Visitantes únicos. El primer contenedor (izquierda) corresponde a 1 vista de página por visitante único, el segundo bloque a dos vistas de página, etc.

![](assets/histogram2.png)

## Configuración avanzada {#section_09D774C584864D4CA6B5672DC2927477}

Para ajustar la configuración del histograma, haga clic en el icono Configuración (&quot;engranaje&quot;) en la esquina superior derecha. Esta es la configuración que puede modificar:

| Configuración del histograma | Qué hace |
|---|---|
| Iniciando bloque | Determina con qué bloque inicio el histograma. &quot;1&quot; es el valor predeterminado. Puede establecer números iniciales de 0 a infinito (sin números negativos). |
| Bloques de métricas | Permite aumentar o reducir el número de intervalos de datos (bloques). El número máximo de bloques es 50. |
| Tamaño del contenedor de métricas | Permite establecer el tamaño de cada bloque. Por ejemplo, puede cambiar el tamaño del bloque de 1 vista de página a 2 vistas de página. |
| Método de recuento | Permite elegir entre [Visitante](https://marketing.adobe.com/resources/help/es_ES/reference/visitors.html), [visita](https://marketing.adobe.com/resources/help/es_ES/reference/metrics_visit.html)o [visita individual](https://marketing.adobe.com/resources/help/es_ES/reference/hit.html). Por ejemplo: vistas de página por visita o vistas de página por visitante o vistas de página por visita. Para visitas, se utiliza “Ocurrencias” como métrica del eje y en una tabla de forma libre. |

**Ejemplos**:

* Iniciando bloque: 1; Bloques de métricas: 5; Tamaño del contenedor de métricas: 2 resultará en este histograma: 1-2, 3-4, 5-6, 7-8, 9-10.
* Iniciando bloque: 0; Bloques de métricas: 3; Tamaño del contenedor de métricas: 5 resultará en este histograma: 0-4, 5-9, 10-14

## Ver y editar los datos de un histograma {#section_B2CD7CDF0F6B432F928103AE7AAA3617}

To view or change the data source for the histogram chart, click the dot next to the Histogram header to go to **[!UICONTROL Data Source Settings]** > **[!UICONTROL Show Data Source]**.

![](assets/manage-data-source.png)

Los segmentos creados previamente que se muestran en la tabla son segmentos internos y no aparecerán en el selector de segmentos. Click the &quot;i&quot; icon next to the segment name, then click **[!UICONTROL Make public]** to make the segment public.

![](assets/prebuilt_segments.png)

Para explorar más formas en las que gestionar las tablas de datos improvisadas y otras visualizaciones, como hacer desgloses de datos, vaya [aquí](https://marketing.adobe.com/resources/help/es_ES/analytics/analysis-workspace/freeform-analysis-visualizations.html).

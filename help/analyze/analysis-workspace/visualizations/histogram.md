---
description: Aprenda a utilizar un histograma, que es similar a un gráfico de barras, pero agrupa números en rangos (contenedores).
title: Histograma
uuid: 8a6bd2c4-da15-4f64-b889-ab9add685046
feature: Visualizations
role: User, Admin
exl-id: f3dd7507-db2c-495c-b6b9-6c770c7c7ddc
source-git-commit: 978bd8642011dd2c8e43564c90303f194689a64e
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 89%

---

# Histograma {#histogram}

>[!CONTEXTUALHELP]
>id="workspace_histogram_button"
>title="Histograma"
>abstract="Cree una visualización de histograma para representar la distribución de datos numéricos en grupos de intervalos."


>[!BEGINSHADEBOX]

_Este artículo documenta la visualización del histograma en_ ![Adobe Analytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics**._<br/>_Consulte [Histograma](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-workspace/visualizations/histogram) para la versión_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics** de este artículo._

>[!ENDSHADEBOX]


La visualización ![Histograma](/help/assets/icons/Histogram.svg) **[!UICONTROL Histograma]** es similar a una visualización de [!UICONTROL Barras], pero agrupa los números en rangos (contenedores). Analytics automatiza la creación de contenedores de números en rangos, pero puede modificar la configuración en [Configuración avanzada](#advanced-settings).

## Utiliza

Para crear un histograma:

1. Añada una visualización ![Histograma](/help/assets/icons/Histogram.svg) **[!UICONTROL Histograma]**. Consulte [Añadir una visualización a un panel](freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
1. Arrastre una métrica de la lista de componentes **[!UICONTROL Métricas]** o seleccione una métrica del menú desplegable [!UICONTROL *Agregar una métrica*].
1. (opcional) Seleccione **[!UICONTROL Mostrar configuración avanzada]** para: Consulte [Configuración avanzada](#advanced-settings).
1. Seleccione **[!UICONTROL Generar]**.

>[!NOTE]
>
>Los histogramas únicamente admiten métricas estándar, pero no métricas calculadas.

En el ejemplo siguiente, se utiliza un histograma para agrupar las sesiones en función del número de personas. El histograma muestra que la mayoría de las personas tienen entre 16 y 21 sesiones para el intervalo de fechas seleccionado.

![](assets/histogram.png)

## Ajustes avanzados

Como parte de la visualización, hay una configuración específica del histograma.

| Configuración del histograma | Descripción |
|---|---|
| **[!UICONTROL Iniciando el intervalo]** | Determina por qué contenedor empieza el histograma. La opción predeterminada es “1”. Puede ajustar los números iniciales de 0 hasta el infinito (sin números negativos). |
| **[!UICONTROL Intervalos de métricas]** | Le permite aumentar/disminuir el número de rangos de datos (intervalos). El número máximo de intervalos es 50. |
| **[!UICONTROL Tamaño del intervalo de métricas]** | Le permite establecer el tamaño de cada contenedor. Por ejemplo, puede cambiar el tamaño del contenedor de 1 vista de página a 2 vistas de página. |
| **[!UICONTROL Método de recuento]** | Seleccione entre **[!UICONTROL Persona]**, **[!UICONTROL Sesión]** o **[!UICONTROL Evento]**. Por ejemplo, vistas de página por sesión o vistas de página por persona o visitas de página por evento.  |

<!--Russ or Meike - Check Hit Type link above. -->

**Ejemplos**:

| Iniciando el intervalo | Intervalos de métricas | Tamaño del intervalo de métricas | Resultado  |
|:----:|:--:|:--:|:--|
| 1 | 5 | 2 | ![Histograma, iniciando el intervalo 1, intervalos de métricas 5, tamaño de intervalo de métricas 2](assets/histogram-1-5-2.png) |
| 0 | 3 | 5 | ![Histograma, iniciando el intervalo 0, intervalos de métricas 3, tamaño del intervalo de métricas 5](assets/histogram-0-3-5.png) |

>[!MORELIKETHIS]
>
>[Añadir una visualización a un panel](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>&#x200B;>[Configuración de visualización](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>&#x200B;>[Menú contextual de visualización](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>&#x200B;>[Uso de histogramas para identificar valores de datos inesperados](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/using-histograms-to-identify-unexpected-data-values/ba-p/596168?profile.language=es)


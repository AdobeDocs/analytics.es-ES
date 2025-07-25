---
description: Utilice la visualización de líneas para visualizar conjuntos de datos de tendencias (basados en el tiempo).
title: Líneas
uuid: 0508ff29-43fe-4f3a-a5f7-051869271b55
feature: Visualizations
role: User, Admin
exl-id: d177b39f-add7-4011-977a-1bdf3a9368cb
source-git-commit: bf8bc40e3ec325e8e70081955fb533eee66a1734
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 98%

---

# Líneas {#line}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_line_button"
>title="Líneas"
>abstract="Cree una visualización de líneas que muestre cómo cambian los valores con el paso del tiempo. Una visualización de líneas solo se puede usar cuando se utiliza el tiempo como dimensión."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Este artículo documenta la visualización de Línea en_ ![Adobe Analytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics**._<br/>_Consulte [Línea](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-workspace/visualizations/line) para la versión_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics** de este artículo._

>[!ENDSHADEBOX]

La visualización de **[!UICONTROL Líneas]**![GraphTrend](/help/assets/icons/GraphTrend.svg) representa las métricas con una línea para mostrar cómo cambian los valores con el paso del tiempo. Una visualización de líneas solo se puede usar cuando se utiliza el tiempo como dimensión.

![Visualización de líneas](assets/line-viz.png)


## Configuración

Como parte de [configuración de visualización](freeform-analysis-visualizations.md#settings), hay disponible una configuración de visualización de línea específica.

| Configuración | Descripción |
|---|---|
| **[!UICONTROL Granularidad]** | Seleccione en la lista desplegable de granularidad para cambiar una visualización de tendencias de diaria a semanal, mensual, etc. La granularidad también se actualiza en la tabla del origen de datos. |
| **[!UICONTROL Mostrar mínimo]** <br/>**[!UICONTROL Mostrar máximo &#x200B;]** | Puede superponer una etiqueta de valor mínimo y máximo para resaltar los valores mínimo y máximo de una métrica. Los valores mínimo/máximo se derivan de los puntos de datos visibles en la visualización, no del conjunto completo de valores dentro de una dimensión.<br/>![Una superposición con la etiqueta de valor mínimo y máximo.](assets/min-max-labels.png) |
| **[!UICONTROL Mostrar línea de tendencia]** | Puede añadir una regresión o una línea de tendencia de promedio móvil a la serie de líneas. Las líneas de tendencia ayudan a mostrar un patrón más claro en los datos. Cuando esté seleccionado, elija un modelo de la lista. Consulte [Modelos](#models) para obtener información general y detallada de los modelos disponibles.<br/>![Línea de tendencia lineal](assets/show-linear-trendline.png). |

>[!TIP]
>
>Se recomienda aplicar las líneas de tendencia a datos que no incluyan fechas de hoy (datos parciales) o futuras. Las fechas de hoy o futuras distorsionan la línea de tendencia. Sin embargo, si necesita incluir fechas futuras, quite ceros de los datos para evitar que se distorsione durante esos días. Vaya a la tabla de fuente de datos de la visualización, elija la columna de métrica y, a continuación, habilite **[!UICONTROL Configuración de columna]** > **[!UICONTROL Interpretar cero como sin valor]**.



### Modelos

Todas las líneas de tendencia del modelo de regresión se ajustan con los mínimos cuadrados normales:

| Modelo | Descripción |
| --- | --- |
| **[!UICONTROL Lineal]** | Crea una línea recta que se adapta mejor para conjuntos de datos lineales simples y resulta útil cuando los datos aumentan o disminuyen a una velocidad constante. Ecuación: `y = a + b * x` |
| **[!UICONTROL Logarítmica]** | Crea una línea curva que se adapta mejor y resulta útil cuando la velocidad de cambio de los datos aumenta o disminuye rápidamente y luego se nivela. Una línea de tendencia logarítmica puede utilizar valores negativos y positivos. Ecuación: `y = a + b * log(x)` |
| **[!UICONTROL Exponencial]** | Crea una línea curva y resulta útil cuando los datos suben o bajan a tasas de crecimiento constantes. Esta opción no debe utilizarse si los datos contienen valores cero o negativos. Ecuación: `y = a + e^(b * x)` |
| **[!UICONTROL Potencia]** | Crea una línea curva y resulta útil para conjuntos de datos que comparan mediciones que aumentan a una velocidad específica. Esta opción no debe utilizarse si los datos contienen valores cero o negativos. Ecuación: `y = a * x^b` |
| **[!UICONTROL Cuadrática]** | Busca el mejor ajuste para un conjunto de datos con forma de parábola (cóncava arriba o abajo). Ecuación: `y = a + b * x + c * x^2` |
| **[!UICONTROL Promedio móvil]** | Crea una línea de tendencia suave basada en un conjunto de promedios. Un promedio móvil utiliza una cantidad determinada de puntos de datos (definida por su selección de [!UICONTROL Granularidad]), los promedia y utiliza el promedio como punto en la línea. Algunos ejemplos son un promedio móvil de siete días o un promedio móvil de cuatro semanas. |

>[!MORELIKETHIS]
>
>[Añadir una visualización a un panel](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>&#x200B;>[Configuración de visualización](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>&#x200B;>[Menú contextual de visualización](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>


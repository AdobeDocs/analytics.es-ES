---
description: Utilice la visualización de resumen de métricas clave para comparar el rendimiento de las métricas en dos cronologías.
title: Resumen de métricas clave
feature: Visualizations
role: User, Admin
exl-id: c74e77ff-15d6-48f1-a845-85bdf3444c3a
source-git-commit: bf8bc40e3ec325e8e70081955fb533eee66a1734
workflow-type: tm+mt
source-wordcount: '948'
ht-degree: 96%

---

# Resumen de métricas clave {#key-metric-summary}

>[!CONTEXTUALHELP]
>id="workspace_keymetricsummary_button"
>title="Resumen de métricas clave"
>abstract="Cree una visualización que sea una combinación de los gráficos de líneas, resumen de cambios y resumen de números. Utilice esta visualización para comparar la tendencia de las métricas importantes entre dos períodos de tiempo."


>[!BEGINSHADEBOX]

_Este artículo documenta la visualización Resumen de métricas clave en_ ![Adobe Analytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics**._<br/>_Consulte [Resumen de métricas clave](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-workspace/visualizations/key-metric) para la versión de_ ![CustomerJourney Analytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics** de este artículo._

>[!ENDSHADEBOX]


La visualización ![KeyMetrics](/help/assets/icons/KeyMetrics.svg) **[!UICONTROL Resumen de métricas clave]** le permite ver las tendencias de una métrica importante en un único período de tiempo. También le permite comparar el rendimiento de las métricas en dos intervalos de tiempo. Proporciona las ventajas de varias visualizaciones combinadas en una sola:

* La visualización **[!UICONTROL Línea]** muestra la tendencia de la métrica para los intervalos de fechas principales y de comparación

* El **[!UICONTROL Cambio de porcentaje de resumen]** muestra el aumento o la disminución de la métrica entre los intervalos de fechas principal y de comparación

* Valor total actual ([!UICONTROL **número de resumen**]) para la métrica

## Casos prácticos

Esta visualización aborda una variedad de casos de uso comunes, entre los que se incluyen:

* Un analista que trata de entender qué aspecto tenía la creación de oportunidades este mes en comparación con el mismo periodo de tiempo del año pasado.

* Un experto en marketing que explora cómo la generación de posibles clientes para un tipo de posible cliente específico ha cambiado de este mes al último.

* Un ejecutivo que quiere entender cómo han variado las nuevas reservas de este trimestre al último.

## Utiliza

1. Añada una visualización ![KeyMetrics](/help/assets/icons/KeyMetrics.svg) **[!UICONTROL Resumen de métricas clave]**. Consulte [Añadir una visualización a un panel](freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

1. Configure la visualización seleccionando una **[!UICONTROL Métrica]**, un **[!UICONTROL Intervalo de fechas principal]**, un **[!UICONTROL Intervalo de fechas de comparación]** (opcional) y un **[!UICONTROL Filtro]** (opcional):

   ![Configuración de la métrica clave mostrando las opciones de métrica, intervalo de fechas principal, intervalo de fechas de comparación y segmento.](assets/key-metrics-config.png)

   | Opción | Descripción |
   | --- | --- |
   | **[!UICONTROL Métrica]** | Seleccione la métrica que desea examinar. Todas las métricas son compatibles. |
   | **[!UICONTROL Intervalo de fechas principal]** | El intervalo de fechas actual para la tabla de forma libre.<p>Elija entre cualquier intervalo de fechas disponible en la vista de datos.</p> <p>Elija [!UICONTROL **Intervalo de fechas del panel**] si desea utilizar el mismo intervalo de fechas que se está utilizando en el panel en el que se encuentra la visualización.</p> |
   | **[!UICONTROL Intervalo de fechas de comparación]** | El intervalo de fechas con el que se desea comparar el intervalo de fechas principal. |
   | **[!UICONTROL Segmento (opcional)]** | Cualquier segmento que le interese específicamente para este resumen. |

   {style="table-layout:auto"}

   >[!NOTE]
   >
   >Cuando el campo [!UICONTROL **Intervalo de fechas principal**] se establece en [!UICONTROL **Intervalo de fechas del panel**], el **[!UICONTROL Intervalo de fechas de comparación]** se puede actualizar automáticamente, dependiendo de si la opción **[!UICONTROL Intervalo de fechas de comparación]** que elija es relativa al intervalo de fechas principal o fijo.
   >
   >* **Relativo:** si el campo **[!UICONTROL Intervalo de fechas de comparación]** se establece en una opción relativa al intervalo de fechas principal (como [!UICONTROL **Día anterior**], [!UICONTROL **Mismo día la semana pasada**], [!UICONTROL **Mismo día cuatro semanas antes**], etc.), cualquier actualización del campo [!UICONTROL **Intervalo de fechas principal**] hará que el **[!UICONTROL Intervalo de fechas de comparación]** se actualice automáticamente al período que sigue inmediatamente al intervalo de fechas del panel.
   >* **Fijo:** si el campo [!UICONTROL **Intervalo de fechas de comparación**] se establece en un intervalo de fechas fijo (como **3 de febrero de 2023**), los cambios realizados en el campo [!UICONTROL **Intervalo de fechas principal**] o en el intervalo de fechas del panel no tendrán ningún efecto sobre el [!UICONTROL **Intervalo de fechas de comparación**]. Sin embargo, cualquier actualización del intervalo de fechas del panel hace que [!UICONTROL **Intervalo de fechas principal**] se actualice automáticamente.

1. Seleccione **[!UICONTROL Generar]**.

El resultado del resumen de métricas clave es el siguiente:

![Resultado de las métricas clave que muestra la métrica, el cambio de resumen, el número de resumen y los gráficos de líneas.](assets/key-metrics.png)

Tenga en cuenta lo siguiente al visualizar esta columna:

* El gráfico de líneas **[!UICONTROL Período anterior]** (siempre mostrado en gris) corresponde al **[!UICONTROL Intervalo de fechas de comparación]** en el paso de configuración.

* Si no se especifica un intervalo de fechas de comparación durante la configuración o está oculto en los ajustes de visualización, solo se muestra el gráfico de líneas del intervalo de fechas principal. El cambio de resumen estará oculto.

* Desde aquí, puede pasar el puntero por encima de los gráficos de líneas para ver las estadísticas de los días individuales:


## Configuración

Después de crear la visualización, puede editar la configuración original.

1. Seleccione ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Configurar visualización]** en la parte superior de la visualización.

   Ahora volverá al diálogo de configuración original.

1. Cambie la configuración de acuerdo con sus preferencias. Seleccione **[!UICONTROL Restablecer]** para restablecer la configuración actual. Seleccione **[!UICONTROL Generar]** para volver a construir la visualización.

## Configuración

Como parte de la configuración de visualización, hay disponibles opciones específicas de resumen de las métricas clave.

| Configuración | Descripción |
| --- | --- |
| **[!UICONTROL Enfatizar el cambio porcentual]** | Mostrar el cambio de resumen en negrita destacado en el centro de la visualización |
| **[!UICONTROL Enfatización del valor numérico]** | Mostrar el número de resumen en negrita destacado en el centro de la visualización |
| **[!UICONTROL Leyenda visible]** | Mostrar u ocultar la leyenda en la parte inferior de la visualización |
| **[!UICONTROL Mostrar anotaciones]** | Mostrar u ocultar anotaciones añadidas por un administrador |
| **[!UICONTROL Ocultar título]** | Ocultar el título de la visualización. |
| **[!UICONTROL Porcentajes]** | Mostrar la visualización en un porcentaje en lugar de un número. |
| **[!UICONTROL Mostrar líneas de tendencia]** | Mostrar las líneas de tendencia en la visualización. |
| **[!UICONTROL Mostrar el máx. y el mín. en las líneas de tendencia]** | Mostrar u ocultar valores mínimos y máximos en gráficos de líneas principales y de comparación |
| **[!UICONTROL Mostrar porcentaje de comparación y líneas de tendencia]** | Muestre u oculte los datos de comparación. Cuando están ocultos, el gráfico de líneas de comparación y los objetos de cambio de resumen no se ven. |
| **[!UICONTROL Mostrar número total]** | Mostrar u ocultar el número de resumen |
| **[!UICONTROL Mostrar diferencia en bruto]** | Mostrar u ocultar la diferencia en bruto entre el valor total de la métrica en el intervalo de fechas principal y el secundario |
| **[!UICONTROL Valor abreviado]** | Seleccione **[!UICONTROL Abreviar valor]** para abreviar de forma inteligente el valor numérico. Cuando esta opción esté seleccionada, introduzca un número para definir la cantidad de abreviatura. Por ejemplo:<br/><table><tr><td>**Valor original**</td><td>**Abreviatura**</td><td>**Resultado**</td></tr><tr><td>12.011.141,25 USD</td><td>No seleccionado</td><td align="right">12.011.141,25 USD</td></tr><tr><td>12.011.141,25 USD</td><td>Seleccionado, establecido en 1</td><td align="right">12 mills. USD</td></tr><tr><td>12.011.141,25 USD</td><td>Seleccionado, establecido en 2</td><td align="right">12,0 mills. USD</td></tr><tr><td>12.011.141,25 USD</td><td>Seleccionado, establecido en 2</td><td align="right">12,011 mills. USD</td></tr><tr><td>12.011.141,25 USD</td><td>Seleccionado, establecido en 3</td><td align="right">12,011 mills. USD</td></tr></table> |

## Edición de la visualización

Después de crear la visualización, puede editar la configuración original.

1. Seleccione ![Editar](/help/assets/icons/Edit.svg) en la esquina superior derecha de la visualización.


   Ahora volverá a la [vista de configuración](#configure) original.

1. Cambie la métrica, el intervalo de fechas principal, el intervalo de fechas de comparación o el segmento como prefiera.

>[!MORELIKETHIS]
>
>[Añadir una visualización a un panel](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>&#x200B;>[Configuración de visualización](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>&#x200B;>[Menú contextual de visualización](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)


---
description: Crear una cohorte y ejecutar un informe de análisis de cohorte en Analysis Workspace.
keywords: Analysis Workspace
title: Ejecutar un informe de análisis de cohorte
feature: Visualizations
role: User, Admin
exl-id: 523e6f62-b428-454b-9460-6b06e96742c3
source-git-commit: 1281bdc569c9ebc5d8daa151b19dc21710633eab
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Configuración de una tabla de cohorte

Para crear y configurar una [!UICONTROL tabla de cohorte]:

1. Añada una visualización ![TextNumbered](/help/assets/icons/TextNumbered.svg) **[!UICONTROL Tabla de cohorte]**. Consulte [Añadir una visualización a un panel](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

1. Defina los **[!UICONTROL Criterios de inclusión]**, **[!UICONTROL Criterios de retorno]**, **[!UICONTROL Tipo de cohorte]** y la **[!UICONTROL Configuración]** tal y como se indica en la siguiente tabla.

   ![Configuración de una tabla de cohorte](assets/cohort-configure.png)

   | Elemento | Descripción |
   |--- |--- |
   | **[!UICONTROL Criterios de inclusión]** | Puede aplicar hasta 10 filtros de inclusión y hasta 3 métricas de inclusión. La métrica especifica a qué cohorte pertenece un usuario. Por ejemplo, si la métrica de inclusión es Pedidos, solo se incluirán en la cohorte inicial aquellos usuarios que hayan realizado un pedido durante el intervalo de tiempo del análisis de cohorte.<br>El operador predeterminado entre métricas es AND, aunque se puede cambiar a OR. Además, se puede añadir filtrado numérico a estas métricas. Por ejemplo: `Sessions >= 1`.</br> |
   | **[!UICONTROL Criterios de regreso]** | Puede aplicar hasta 10 filtros de regreso y hasta 3 métricas de regreso. La métrica indica si se ha retenido al usuario (retención) o no (pérdida). Por ejemplo, si la métrica de regreso es Vistas de vídeo, solo se representan como retenidos aquellos usuarios que hayan visto vídeos durante períodos de tiempo siguientes (después del período en el que se añadieron a una cohorte). Otra métrica que cuantifica la retención es Sesiones. |
   | **[!UICONTROL Granularidad]** | La granularidad de tiempo de Día, Semana, Mes, Trimestre o Año. |
   | **[!UICONTROL Tipo]** | **[!UICONTROL Retención]** (predeterminado): Una cohorte de **[!UICONTROL Retención]** mide en qué medida sus cohortes de personas regresan a su propiedad a lo largo del tiempo. Una cohorte de retención es la cohorte estándar e indica un comportamiento de regreso y repetición por parte del usuario. El color verde indica una cohorte de [!UICONTROL Retención] en la tabla.<br>**[!UICONTROL Pérdida &#x200B;]**: una cohorte de&#x200B;**[!UICONTROL &#x200B; pérdida &#x200B;]**(también conocida como desgaste o abandono) mide cómo las cohortes de visitantes se alejan de su propiedad a lo largo del tiempo. La pérdida es lo contrario a la retención: `Churn = 1 - Retention`. [!UICONTROL La pérdida] es una buena medida de la permanencia y una oportunidad, ya que muestra con qué frecuencia no regresan los clientes. Puede utilizar la pérdida para analizar e identificar áreas en las que centrarse: ¿qué filtros de cohorte deben recibir más atención? Un color rojo indica una cohorte [!UICONTROL Pérdida] en la tabla (similar al abandono en la visualización&#x200B;**[!UICONTROL &#x200B; Flujo &#x200B;]**).</br> |
   | **[!UICONTROL Configuración]** | **[!UICONTROL Cálculo móvil]**: calcule la retención o la pérdida en función de la columna previa, no de la columna Incluido (valor predeterminado). [!UICONTROL Cálculo móvil] cambia el método de cálculo para sus períodos de &quot;regreso&quot;. El cálculo normal encuentra a los usuarios que cumplen los criterios de regreso y que formaron parte del período de inclusión. Independientemente de si estaban o no en la cohorte durante el período anterior. Por su parte, [!UICONTROL Cálculo móvil] encuentra usuarios que cumplen los criterios de “regreso” y que fueron parte del periodo anterior. Por tanto, [!UICONTROL Cálculo móvil] filtra y canaliza a los usuarios que cumplen de forma continua los criterios de “regreso”, periodo tras periodo. Los criterios de [!UICONTROL regreso] se aplican a cada uno de los periodos previos al periodo seleccionado. </br><br>**[!UICONTROL Tabla de latencia &#x200B;]**: Una [!UICONTROL tabla de latencia] mide el tiempo transcurrido antes y después de que se produzca el evento de inclusión. [!UICONTROL La tabla de latencia] es muy útil para el análisis previo y posterior. Por ejemplo: tiene un próximo lanzamiento de producto o campaña y desea rastrear el comportamiento antes y después del lanzamiento. La [!UICONTROL tabla de latencia] muestra el comportamiento previo y posterior en paralelo para ver el impacto directo. Las celdas de preinclusión en la [!UICONTROL tabla de latencia] calculan los usuarios que cumplen los criterios de [!UICONTROL inclusión] en el periodo de inclusión y que luego cumplen los criterios de [!UICONTROL regreso] en los periodos anteriores al periodo de inclusión.  Tenga en cuenta que [!UICONTROL Tabla de latencia] y [!UICONTROL Cohorte de dimensión personalizada] no se pueden utilizar juntos.</br><br>**[!UICONTROL Cohorte de dimensión personalizada]**: cree cohortes basadas en la dimensión seleccionada, en lugar de cohortes basadas en el tiempo (predeterminado). Muchos clientes desean analizar sus cohortes en función de un criterio distinto del tiempo. La nueva función de cohorte de dimensión personalizada ofrece la flexibilidad para generar cohortes basadas en dimensiones de su elección. Utilice dimensiones como canal de marketing, campaña, producto, página, región o cualquier otra dimensión para mostrar cómo cambia la retención en función de los distintos valores que adoptan. La definición del filtro de la cohorte de [!UICONTROL dimensión personalizada] aplica el elemento de dimensión solo como parte del período de inclusión, y no como parte de la definición de regreso.</br><br>Después de elegir la opción [!UICONTROL Cohorte de dimensión personalizada], puede arrastrar y soltar la dimensión que desee en la zona de colocación. Añadir dimensiones le permite comparar artículos de dimensiones similares en el mismo periodo de tiempo. Por ejemplo, puede comparar el rendimiento de ciudades, de productos, de campañas, etc. La tabla de cohorte devuelve los 14 elementos de dimensión principales. Sin embargo, puede usar un filtro ![Filtro](/help/assets/icons/Filter.svg) para mostrar solo los elementos de dimensión que desee. No se puede utilizar una [!UICONTROL Cohorte de dimensión personalizada] con la función [!UICONTROL Tabla de latencia].</br> |

1. Haga clic en **[!UICONTROL Generar]**.
1. Para volver a configurar la [!UICONTROL tabla de cohortes], seleccione ![Editar](/help/assets/icons/Edit.svg).

1. (Opcional) Cree un segmento a partir de una selección.

   Seleccione una o más celdas (contiguas o no) y, a continuación, haga clic con el botón derecho del ratón en > **[!UICONTROL Crear segmento a partir de la selección]**.


1. En el [Generador de segmentos](/help/components/segmentation/segmentation-workflow/seg-build.md), continúe editando el segmento y luego haga clic en **[!UICONTROL Guardar]**.

   El segmento guardado está disponible para usar en el panel [!UICONTROL Segmento] en [!UICONTROL Analysis Workspace].

## Configuración

Puede definir la configuración específica de una [!UICONTROL tabla de cohortes].

1. Seleccione ![Configuración](/help/assets/icons/Setting.svg) para ajustar la configuración de la [!UICONTROL tabla de cohortes].

   | Configuración | Descripción |
   |---|---|
   | **Mostrar solo porcentaje** | Elimina el valor numérico y solo muestra el porcentaje. |
   | **Redondear el porcentaje al entero más cercano** | Redondea el valor porcentual al total más cercano en lugar de mostrar el valor decimal. |
   | **Mostrar fila de porcentaje medio** | Inserta una nueva fila en la parte superior de la tabla y, a continuación, agrega el promedio de los valores dentro de cada columna. |


>[!MORELIKETHIS]
>
>[Añadir una visualización a un panel](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>&#x200B;>[Configuración de visualización](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>&#x200B;>[Menú contextual de visualización](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>


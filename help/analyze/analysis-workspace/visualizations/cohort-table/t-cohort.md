---
description: Crear una cohorte y ejecutar un informe de análisis de cohorte en Analysis Workspace.
keywords: Analysis Workspace
title: Ejecutar un informe de análisis de cohorte
topic: Reports and analytics
uuid: 5574230f-8f35-43ea-88d6-cb4960ff0bf4
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Configurar un informe de análisis de cohorte

Crear una cohorte y ejecutar un informe de análisis de cohorte en Analysis Workspace.

1. En Analysis Workspace, haga clic en el icono **[!UICONTROL Visualizaciones]** en el panel izquierdo y, a continuación, arrastre una **[!UICONTROL tabla asociada]** al lienzo.

   ![](assets/cohort-table.png)

1. Defina los **[!UICONTROL Criterios de inclusión]**, **[!UICONTROL Criterios de retorno]**, **[!UICONTROL Tipo de cohorte]** y la **[!UICONTROL Configuración]** tal y como se indica en la siguiente tabla.

| Elemento | Descripción |
|--- |--- |
| **[!UICONTROL Criterios de inclusión]** | Puede aplicar hasta 10 segmentos de inclusión y hasta 3 métricas de inclusión. La métrica indica qué factores colocan a un usuario en una cohorte determinada. Por ejemplo, si la métrica de inclusión es Órdenes, solo se incluirán en la cohorte inicial aquellos usuarios que hayan realizado una orden durante el intervalo de tiempo del análisis de cohorte.<br>El operador predeterminado entre métricas es Y, aunque se puede cambiar a O. Además, se puede añadir filtrado numérico a estas métricas. Por ejemplo: &quot;Visitas >= 1&quot;.</br> |
| **[!UICONTROL Criterios de regreso]** | Puede aplicar hasta 10 segmentos de regreso y hasta 3 métricas de regreso. La métrica indica si se ha retenido al usuario (retención) o no (pérdida). Por ejemplo, si la métrica de regreso es Vistas de vídeo, solo se representarán como retenidos aquellos usuarios que hayan visto vídeos durante periodos de tiempo siguientes (después del periodo en el que se agregaron a una cohorte). Otra métrica que cuantifica la retención es Visitas. |
| **[!UICONTROL Granularidad]** | La granularidad de tiempo de Día, Semana, Mes, Trimestre o Año. |
| **[!UICONTROL Tipo]** | **[!UICONTROL Retención]** (predeterminado): una cohorte de retención mide en qué medida las cohortes de visitantes regresan a su propiedad a lo largo del tiempo. Esta es la cohorte estándar que siempre hemos tenido y que indica un comportamiento de regreso y repetición por parte del usuario. Una cohorte de retención se indica con el color verde en la tabla.<br>**[!UICONTROL Pérdida ]**: una cohorte de pérdida (también conocida como “desgaste” o “abandono”) mide cómo las cohortes de visitantes se alejan de su propiedad a lo largo del tiempo. Pérdida = 1 - Retención. La pérdida es una buena medida de la adherencia y una oportunidad, ya que muestra con qué frecuencia no regresan los clientes. Puede utilizar la pérdida para analizar e identificar áreas en las que centrarse: ¿qué segmentos de cohorte deben recibir más atención? Una cohorte de pérdida se indica con el color rojo en la tabla (como los abandonos en una visualización de **[!UICONTROL  Flujo ]** ).</br> |
| **[!UICONTROL Configuración]** | **[!UICONTROL Cálculo móvil]**: calcule la retención o la pérdida en función de la columna previa, no de la columna Incluido (valor predeterminado). Cálculo móvil cambia el método de cálculo para sus periodos de &quot;regreso&quot;. El cálculo normal encuentra de forma independiente usuarios que satisfacen los criterios de &quot;regreso&quot; y que fueron parte del periodo de inclusión, sin importar si estaban o no en la cohorte durante el periodo anterior. Por su parte, Cálculo móvil encuentra usuarios que satisfacen los criterios de &quot;regreso&quot; y que fueron parte del periodo anterior. Por tanto, Cálculo móvil filtra y canaliza a los usuarios que satisfacen de forma continua los criterios de &quot;regreso&quot;, periodo tras periodo. Los criterios de devolución se aplican a cada uno de los periodos previos al periodo seleccionado. </br><br>**[!UICONTROL Tabla de latencia ]**: mide el tiempo transcurrido antes y después de que el evento de inclusión ocurriese. La latencia es muy útil para el análisis previo/posterior. Por ejemplo, si se acerca el lanzamiento de un producto o campaña y quiere realizar un seguimiento del comportamiento anterior, además de ver el desempeño posterior, la tabla de latencia muestra juntos el comportamiento anterior y el posterior para así comprobar el impacto directo. Las celdas de preinclusión en la tabla de latencia se calculan con los usuarios que satisfacen los criterios de &quot;inclusión&quot; en el periodo de inclusión y que después satisfacen los criterios de &quot;regreso&quot; en los periodos anteriores al periodo de inclusión. Tenga en cuenta que las tablas de latencia y la cohorte de dimensión personalizada no se pueden utilizar al mismo tiempo.</br><br>**[!UICONTROL Cohorte de dimensión personalizada]**: cree cohortes basadas en la dimensión seleccionada, no en el tiempo (valor predeterminado). Muchos clientes desean analizar sus cohortes en función de un criterio distinto del tiempo. La nueva función de cohorte de dimensión personalizada ofrece la flexibilidad para generar cohortes basadas en dimensiones de su elección. Utilice dimensiones como canal de marketing, campaña, producto, página, región o cualquier otra dimensión de Adobe Analytics para mostrar cómo cambia la retención en función de los distintos valores que adoptan. La definición de segmento Dimensión de cohorte personalizada aplica el elemento de dimensión solo como parte del periodo de inclusión, y no como parte de la definición de devolución.</br><br>Después de elegir la opción Cohorte de dimensión personalizada, puede arrastrar y soltar cualquier dimensión que desee en la zona de colocación. De este modo puede comparar elementos de dimensión similares durante el mismo periodo de tiempo. Por ejemplo, puede comparar el rendimiento de ciudades, de productos, de campañas, etcétera. Devuelve sus 14 elementos de dimensión principales. Sin embargo, puede utilizar un filtro (al que se accede manteniendo el puntero a la derecha de la dimensión que ha arrastrado) para que solo se muestren los elementos de dimensión que desee. No es posible utilizar una cohorte de dimensión personalizada junto a la función de tablas de latencia.</br> |

1. Para ajustar la configuración de la **[!UICONTROL tabla asociada]**, haga clic en el icono de engranaje.

| Configuración | Descripción |
| Solo mostrar porcentaje | Elimina el valor numérico y solo muestra el porcentaje. |
| Porcentaje de redondeo al total más cercano | Redondea el valor porcentual al total más cercano en lugar de mostrar el valor decimal. |
| Mostrar fila de porcentaje promedio | Inserta una nueva fila en la parte superior de la tabla y, a continuación, agrega el promedio de los valores dentro de cada columna. |

## Generar el informe de Análisis de cohorte

1. Haga clic en **[!UICONTROL Generar]**.

   ![Resultado](assets/cohort-report.png)

   El informe muestra los visitantes que realizaron un pedido (columna *`Included`*) y que regresaron al sitio en visitas posteriores. La reducción en visitas durante el tiempo le permite identificar problemas y tomar medidas.
1. (Opcional) Cree un segmento a partir de una selección.

   Seleccione celdas (contiguas o no) y haga clic con el botón secundario en > **[!UICONTROL Crear segmento a partir de la selección]**.

1. En el [Generador de segmentos](https://marketing.adobe.com/resources/help/es_ES/analytics/segment/seg_build.html), continúe editando el segmento y luego haga clic en **[!UICONTROL Guardar]**.

   El segmento guardado está disponible para usar en el panel [!UICONTROL Segmento] en Analysis Workspace.
1. Especifique un nombre y guarde su proyecto de cohorte.
1. (Opcional) [Depure y comparta](/help/analyze/analysis-workspace/curate-share/curate.md) los componentes del proyecto.

   >[!NOTE]
   >
   >Debe guardar el proyecto antes de que la depuración esté disponible.


---
description: La sincronización de visualizaciones le permite controlar qué tabla de datos o fuente de datos corresponde con una visualización.
keywords: Analysis Workspace;Synchronize visualization with data source
title: Administración de fuentes de datos
translation-type: tm+mt
source-git-commit: 6eda9e3e5bd450213253a8181042c24c318c0300

---


# Administración de fuentes de datos

La sincronización de visualizaciones le permite controlar qué tabla de datos o fuente de datos corresponde con una visualización.

**Sugerencia:** Puede saber qué visualizaciones están relacionadas por el color del punto al lado del título. Los colores coincidentes significan que las visualizaciones se basan en la misma fuente de datos.

La administración de una fuente de datos permite mostrar la fuente de datos o bloquear la selección. Esta configuración determina cómo cambia (o no) la visualización cuando entran nuevos datos.

1. [Cree un proyecto](/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md) con una tabla de datos y [una visualización](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md).
1. En la tabla de datos, seleccione las celdas (fuente de datos) que desee asociar con la visualización.
1. In the visualization, click the dot next to the title to bring up the **[!UICONTROL Data Source]** dialog. Seleccione **[!UICONTROL Show Data Source]** o **[!UICONTROL Lock Selection]**.

   ![](assets/manage-data-source.png)

   Al sincronizar una visualización con una celda de tabla, se crea una nueva tabla (oculta) y se codifica con colores la visualización sincronizada con esa tabla.

| Elemento | Descripción |
|--- |--- |
| Visualizaciones vinculadas | Si hay visualizaciones conectadas a una tabla improvisada o de cohorte, el punto superior izquierdo se abre para mostrar las visualizaciones conectadas, con una opción “mostrar” que muestra u oculta la tabla.  Al pasar el ratón por encima se resalta la visualización vinculada y al hacer clic en ella se accede a ella. |
| Mostrar fuente de datos | Permite mostrar (activando la casilla de verificación) u ocultar (desactivando) la tabla de datos que corresponde a la visualización. |
| Bloquear selección | Habilite esta configuración para bloquear la visualización a los datos seleccionados actualmente en la tabla de datos correspondiente. Una vez habilitada, elija entre:  <ul><li>**Posiciones** seleccionadas: Seleccione esta opción si desea que la visualización permanezca bloqueada en las posiciones seleccionadas en la tabla de datos correspondiente. Estas posiciones se seguirán visualizando, incluso si cambian los elementos específicos de estas posiciones. Por ejemplo, elija esta opción si desea mostrar los cinco nombres de campaña principales en esta visualización en todo momento, independientemente de los nombres de campaña que se muestren en los cinco primeros.</li> <li>**Elementos** seleccionados: Seleccione esta opción si desea que la visualización permanezca bloqueada en los elementos específicos seleccionados actualmente en la tabla de datos correspondiente. Estos elementos se seguirán visualizando, aunque cambien su clasificación entre los elementos de la tabla. Por ejemplo, elija esta opción si desea mostrar los mismos cinco nombres de campaña específicos en esta visualización en todo momento, independientemente de la clasificación de esos nombres de campaña.</li></ul> |

La diferencia de esta nueva arquitectura con respecto a la anterior es que Analysis Workspace ya no crea una tabla oculta duplicada que almacena la selección bloqueada. Ahora, el origen de datos apunta a la tabla desde la que creó la visualización.

**Casos de uso de ejemplo:**

* Puede crear una visualización de resumen y bloquearla en una celda de la tabla desde la que la creó. Al habilitar &quot;Mostrar fuente de datos&quot;, se muestra exactamente de dónde proviene esta información en la tabla. Los datos de origen aparecerán atenuados:

   ![](assets/data-source2.png)>
* Puede agregar muchas visualizaciones y originarlas desde diferentes celdas de la misma tabla, como se muestra aquí. La tabla es la misma que en el ejemplo anterior, pero la celda (y métrica) de origen es diferente:

   ![](assets/data-source3.png)>
* Puede ver si hay visualizaciones conectadas a una tabla improvisada o de cohorte haciendo clic en el punto superior izquierdo (Configuración de fuente de datos). Al pasar el ratón por encima se resaltará la visualización vinculada y al hacer clic en ella se le dirigirá.

   ![](assets/linked-visualizations.png)>

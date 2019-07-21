---
description: La sincronización de visualizaciones le permite controlar qué tabla de datos o fuente de datos corresponde con una visualización.
keywords: Analysis Workspace; Visualización de sincronización con fuente de datos
seo-description: La sincronización de visualizaciones le permite controlar qué tabla de datos o fuente de datos corresponde con una visualización.
seo-title: Administración de fuentes de datos
solution: Analytics
title: Administración de fuentes de datos
topic: Reports and Analytics
uuid: 7 bacf 497-a 933-463 a-bf 9 d-f 6 d 0 c 5 de 0 cba
translation-type: tm+mt
source-git-commit: 0bd28ea64b4e225b33c1fec7f185c7006bdb7f7c

---


# Administración de fuentes de datos

La sincronización de visualizaciones le permite controlar qué tabla de datos o fuente de datos corresponde con una visualización.

**Sugerencia:** puede saber qué visualizaciones están relacionadas por el color del punto al lado del título. La coincidencia de colores significa que las visualizaciones están basadas en la misma fuente de datos.

Al administrar una fuente de datos, puede mostrar la fuente de datos o bloquear la selección. Esta configuración determina cómo cambia (o no) la visualización al introducir nuevos datos.

1. [Cree un proyecto](../../../analyze/analysis-workspace/build-workspace-project/t-freeform-project.md#task_C2C698ACC7954062A28E4784911E6CF2) con una tabla de datos y [una visualización](../../../analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#concept_09242627629147A88A68F1506954C276).
1. En la tabla de datos, seleccione las celdas (fuente de datos) que desee asociar con la visualización.
1. In the visualization, click the dot next to the title to bring up the **[!UICONTROL Data Source]** dialog. Seleccione **[!UICONTROL Mostrar fuente de datos]** o **[!UICONTROL Bloquear selección]**.

   ![](assets/manage-data-source.png)

   Al sincronizar una visualización con una celda de tabla, se crea una nueva tabla (oculta) y se codifica con colores la visualización sincronizada con esa tabla.

| Elemento | Descripción |
|--- |--- |
| Visualizaciones conectadas | Si hay visualizaciones conectadas a una tabla improvisada o de cohorte, el punto superior izquierdo se abre para mostrar las visualizaciones conectadas, con una opción “mostrar” que muestra u oculta la tabla.  Al pasar el ratón por encima, se resalta la visualización vinculada y, al hacer clic en ella, se abre. |
| Mostrar fuente de datos | Le permite mostrar (al activar la casilla de verificación) u ocultar (al desactivarla) la tabla de datos correspondiente a la visualización. |
| Bloquear selección | Active este ajuste para bloquear la visualización de los datos seleccionados actualmente en la tabla de datos correspondiente. Una vez activado, elija entre:  <ul><li>**Posiciones seleccionadas**: elija esta opción si desea que la visualización permanezca bloqueada en las posiciones seleccionadas en la tabla de datos correspondiente. Estas posiciones seguirán visualizándose, incluso si cambian los elementos específicos de estas posiciones. Por ejemplo, elija esta opción si desea mostrar los cinco nombres de campaña principales en esta visualización en todo momento, independientemente de qué nombres de campaña se muestran en los cinco principales.</li> <li>**Elementos seleccionados**: elija esta opción si desea que la visualización permanezca bloqueada en elementos específicos seleccionados actualmente en la tabla de datos correspondiente. Estos elementos se seguirán visualizando, incluso si cambian su clasificación entre los elementos de la tabla. Por ejemplo, elija esta opción si desea mostrar los mismos cinco nombres de campaña específicos en esta visualización en todo momento, sin importar la posición en la clasificación de estos nombres en la campaña.</li></ul> |

Esta arquitectura difiere de la anterior, ya que Analysis Workspace ya no crea una tabla oculta duplicada que almacena la selección bloqueada. Ahora, la fuente de datos apunta a la tabla desde la que creó la visualización.

**Casos de uso de ejemplo:**

* Puede crear una visualización de resumen y bloquearla en una celda de la misma tabla en la que la creó. Al activar “Mostrar fuente de datos”, se muestra la procedencia exacta de esta información en la tabla. Los datos de origen aparecerán atenuados:

   ![](assets/data-source2.png)&gt;
* Puede agregar muchas visualizaciones cuyo origen sean diferentes celdas de una misma tabla, como se muestra aquí. Esta tabla es la misma que en el ejemplo anterior, pero la celda de origen (y la métrica) es diferente:

   ![](assets/data-source3.png)&gt;
* Puede ver si existen visualizaciones conectadas a una tabla improvisada o de cohorte haciendo clic en el punto superior izquierdo (Configuración de fuente de datos). Al pasar el ratón por encima, se resalta la visualización vinculada y, al hacer clic en ella, se abre.

   ![](assets/linked-visualizations.png)&gt;

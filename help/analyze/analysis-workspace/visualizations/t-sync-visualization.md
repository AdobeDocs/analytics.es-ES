---
description: Obtenga información sobre cómo sincronizar una tabla de forma libre o una fuente de datos con la visualización correspondiente.
keywords: Analysis Workspace;Sincronizar visualización con fuente de datos
title: Administrar fuentes de datos
feature: Visualizations
role: User, Admin
exl-id: 0500b27a-032e-4dc8-98b7-58519ef59368
source-git-commit: f258a1150a4bee11f5922d058930dc38b1ddfa14
workflow-type: tm+mt
source-wordcount: '436'
ht-degree: 89%

---

# Administración de fuentes de datos {#manage-data-sources}

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection"
>title="Bloquear selección"
>abstract="Habilite esta configuración para bloquear la visualización en las posiciones o en los elementos seleccionados de la fuente de datos."

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection_showtable"
>title="Mostrar tabla"
>abstract="Si se selecciona **[!UICONTROL Mostrar tabla]**, se generará un nuevo origen de datos para la visualización actual, independiente del origen de datos original."

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_showtable"
>title="Mostrar tabla"
>abstract="Seleccione **[!UICONTROL Mostrar tabla]** para generar una nueva fuente de datos para la visualización actual, independiente de la fuente de datos original."


La sincronización de visualizaciones le permite controlar qué tabla de forma libre o fuente de datos corresponde con una visualización.


>[!TIP]
>
>Puede saber qué visualizaciones están relacionadas por el color ![StatusOrange](/help/assets/icons/StatusOrange.svg) situado junto al título de las visualizaciones. La coincidencia de colores significa que las visualizaciones están basadas en la misma fuente de datos.
>

Puede mostrar u ocultar la fuente de datos. También puede bloquear la selección en las posiciones seleccionadas o a los elementos seleccionados. Esta configuración determina cómo cambia (o no) la visualización al introducir nuevos datos.

![Opción Fuente de datos que muestra las opciones que se describen en la siguiente sección.](assets/lock-selection.png)

<!--
**Tip:** You can tell which visualizations are related by the color of the dot next to the title. Matching colors mean that visualizations are based on the same data source.

Managing a data source lets you show the data source or lock the selection. These settings determine how the visualization changes (or doesn't change) when new data comes in.

1. [Create a project](/help/analyze/analysis-workspace/home.md) with a data table and a [visualization](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md).
1. In the data table, select the cells (data source) you want to associate with the visualization.
1. In the visualization, click the dot next to the title to bring up the **[!UICONTROL Data Source]** dialog. Select **[!UICONTROL Show Data Source]** or **[!UICONTROL Lock Selection]**.

   ![](assets/manage-data-source.png)

   Synchronizing a visualization to a table cell creates a new (hidden) table and color-codes the synchronized visualization with that table.

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Data source settings](https://video.tv.adobe.com/v/23729?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->

| Opción | Descripción |
|--- |--- |
| **[!UICONTROL Fuente de datos]** | En el menú desplegable, seleccione la fuente de datos en la que se basa la visualización. |
| **[!UICONTROL Visualizaciones vinculadas]** | Enumera todas las visualizaciones vinculadas. Se aplica a la fuente de datos (tabla de forma libre). |
| **[!UICONTROL Mostrar fuente de datos]** | Permite mostrar u ocultar la fuente de datos (tabla de forma libre) que corresponde a la visualización. |
| **[!UICONTROL Bloquear selección]** | Seleccione esta opción para bloquear la visualización ![LockClosed](/help/assets/icons/LockClosed.svg) en los datos seleccionados actualmente en la tabla de datos correspondiente. Una vez habilitada, elija entre:  <ul><li>**Posiciones seleccionadas**: la visualización está bloqueada en las **posiciones** seleccionadas en la tabla de datos correspondiente. Estas posiciones se siguen visualizando, incluso si cambian los elementos específicos de estas posiciones (por ejemplo, debido a la ordenación o al filtrado). Por ejemplo, seleccione esta opción si desea mostrar los cinco nombres de campaña principales enumerados en la fuente de datos en esta visualización en todo momento. No importa qué nombres de campaña aparezcan.</li> <li>**Elementos seleccionados**: la visualización está bloqueada en **elementos** específicos seleccionados actualmente en la tabla de datos correspondiente. Estos elementos se seguirán visualizando, incluso si cambian su clasificación entre los elementos de la tabla. Por ejemplo, seleccione esta opción si desea mostrar los mismos cinco nombres de campaña específicos enumerados en la fuente de datos en esta visualización en todo momento. No importa cómo se clasifiquen esos nombres de campaña.</li></ul>Si la visualización está bloqueada en datos que ya no son visibles en la tabla de datos conectada, puede generar una nueva tabla. Seleccione **[!UICONTROL Mostrar tabla]**, se generará un nuevo origen de datos para la visualización actual, independiente del origen de datos original. |

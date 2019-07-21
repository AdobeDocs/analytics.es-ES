---
description: Describe los pasos involucrados en la aplicación de filtros a un informe de visitas en el orden previsto.
seo-description: Describe los pasos involucrados en la aplicación de filtros a un informe de visitas en el orden previsto.
seo-title: Filtrar un informe de visitas en el orden previsto utilizando el Asistente para solicitudes
solution: Analytics
title: Filtrar un informe de visitas en el orden previsto utilizando el Asistente para solicitudes
topic: Creador de informes
uuid: 269 e 900 e -23 bd -48 d 8-9 bac -69 e 3167 a 9 c 18
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Filtrar un informe de visitas en el orden previsto utilizando el Asistente para solicitudes

Describe los pasos involucrados en la aplicación de filtros a un informe de visitas en el orden previsto.

En este ejemplo se muestra el informe de visitas en el orden previsto de página.

1. In Adobe Report Builder, click **[!UICONTROL Create]** to open the Request Wizard.
1. Seleccione el grupo de informes adecuado.
1. In the tree view on the left, select **[!UICONTROL Paths]** &gt; **[!UICONTROL Page]** &gt; **[!UICONTROL Page Fallout]**.

   ![](assets/page_fallout.png)

1. Configure the appropriate [date ranges](../../../../analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md).
1. Click **[!UICONTROL Next]**.
1. In Step 2 of the Wizard, under **[!UICONTROL Row Labels]**, click the **[!UICONTROL Define Checkpoints]** link. (En un informe de visitas en el orden previsto, siempre tiene que definir los elementos de ruta, a diferencia de en un informe de ruta, donde se aplica un patrón previamente). 

   ![](assets/define_checkpoints.png)

1. Select the **[!UICONTROL Filter]** option.

1. In the **[!UICONTROL Define Site Section Fallout Checkpoints]** dialog, define checkpoints from a range of cells or from a list. A continuación, haga clic en **[!UICONTROL Aceptar]**.
1. Decida si desea seleccionar de un rango de celdas o de una lista.
1. If you select from a list, click **[!UICONTROL Add]** to select checkpoints to add to the fallout path. Puede definir entre 3 y 8 puntos de comprobación. (Search for available elements by clicking **[!UICONTROL More]**.)

   For more information on refining the filter, see [Filter Dimensions](../../../../analyze/report-builder/layout/c-filter-dimensions/filter-dimensions.md#concept_9C0518E2CF604AADA97DDBB1B4ECAAF8). 1. Move **[!UICONTROL Available Elements]** from the left column to the right by selecting them and clicking the orange arrow.
1. Click **[!UICONTROL OK]** three times, then click **[!UICONTROL Finish]**.

   El informe debería actualizarse en este momento.
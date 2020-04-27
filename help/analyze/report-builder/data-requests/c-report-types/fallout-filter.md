---
description: Describe los pasos involucrados en la aplicación de filtros a un informe de visitas en el orden previsto.
title: Filtrado de un informe de abandonos mediante el Asistente para solicitudes
topic: Report builder
uuid: 269e900e-23bd-48d8-9bac-69e3167a9c18
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Filtrado de un informe de abandonos mediante el Asistente para solicitudes

Describe los pasos involucrados en la aplicación de filtros a un informe de visitas en el orden previsto.

En este ejemplo se muestra el informe de visitas en el orden previsto de página.

1. In Adobe Report Builder, click **[!UICONTROL Create]** to open the Request Wizard.
1. Seleccione el grupo de informes adecuado.
1. En la vista de árbol de la izquierda, seleccione **[!UICONTROL Paths]** > **[!UICONTROL Page]** > **[!UICONTROL Page Fallout]**.

   ![](assets/page_fallout.png)

1. Configure los [intervalos de fechas](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md) adecuados.
1. Haga clic en **[!UICONTROL Next]**.
1. En el paso 2 del asistente, en **[!UICONTROL Row Labels]**, haga clic en el **[!UICONTROL Define Checkpoints]** vínculo. (En un informe de visitas en el orden previsto, siempre tiene que definir los elementos de ruta, a diferencia de en un informe de ruta, donde se aplica un patrón previamente).

   ![](assets/define_checkpoints.png)

1. Seleccione la opción **[!UICONTROL Filter]**.

1. En el **[!UICONTROL Define Site Section Fallout Checkpoints]** cuadro de diálogo, defina los puntos de comprobación de un rango de celdas o de una lista. A continuación, haga clic en **[!UICONTROL OK]**.
1. Decida si desea seleccionar de un rango de celdas o de una lista.
1. If you select from a list, click **[!UICONTROL Add]** to select checkpoints to add to the fallout path. Puede definir entre 3 y 8 puntos de comprobación. (Search for available elements by clicking **[!UICONTROL More]**.)

   Si desea información sobre cómo perfeccionar un filtro, consulte [Dimensiones de filtros](/help/analyze/report-builder/layout/c-filter-dimensions/filter-dimensions.md). 1. Move **[!UICONTROL Available Elements]** from the left column to the right by selecting them and clicking the orange arrow.
1. Haga clic **[!UICONTROL OK]** tres veces y, a continuación, haga clic en **[!UICONTROL Finish]**.

   El informe debería actualizarse en este momento.

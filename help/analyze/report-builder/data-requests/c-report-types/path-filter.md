---
description: Describe los pasos involucrados en la aplicación de filtros a un informe de ruta.
title: Filtrado de un informe de rutas mediante el Asistente para solicitudes
topic: Report builder
uuid: 9b22d5b5-7ae8-49a2-90ae-0c1075562bbe
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Filtrado de un informe de rutas mediante el Asistente para solicitudes

Describe los pasos involucrados en la aplicación de filtros a un informe de ruta.

En este ejemplo se utilizan las rutas de sección del sitio.

1. In Adobe Report Builder, click **[!UICONTROL Create]** to open the Request Wizard.
1. Seleccione el grupo de informes adecuado.
1. En la vista de árbol de la izquierda, seleccione **[!UICONTROL Paths]** > **[!UICONTROL Site Sections]** > **[!UICONTROL Site Section Paths]**.

   ![](assets/site_section_path_1.png)

1. Especifique las fechas adecuadas.
1. Haga clic en **[!UICONTROL Next]**.
1. En el paso 2 del asistente, en **[!UICONTROL Row Labels]**, haga clic en el **[!UICONTROL Top 1-10 (pattern applied)]** vínculo. En un informe de ruta, se aplica un patrón de forma predeterminada.

   ![](assets/site_section_path_2.png)

1. Seleccione la opción **[!UICONTROL Filter]**.

   ![](assets/filter_option.png)

1. En el cuadro de diálogo **[!UICONTROL Define 'Site Section Paths' Path Pattern]** , puede especificar
   1. la clasificación inicial del primer informe.
   1. el número de entradas que desea que se muestren en este informe.
1. Click **[!UICONTROL Edit]** to define a path pattern.
1. If you want a custom pattern, drag and drop any **[!UICONTROL Pattern Objects]** from the list on the left into the **[!UICONTROL Pattern Build Canvas]** on the right.

   ![](assets/custom_pattern.png)

1. You can also select a predefined pattern from the **[!UICONTROL Select a Pattern]** drop-down list and modify it. A continuación verá los patrones disponibles:

   ![](assets/select_a_pattern.png)

   Algunos de estos patrones son específicos de Report Builder: patrón de elemento siguiente de la ruta de entrada, patrón de elemento anterior de la ruta de salida, patrón de elemento siguiente.
1. Para editar un patrón predefinido:
   1. Selecciónelo. Por ejemplo, seleccione el **[!UICONTROL Exited Site Pattern]**: ![](assets/exited_site_pattern.png)

   1. En este momento debería definir la ruta de la sección del sitio que sigue el usuario antes de salir. Haga clic en **[!UICONTROL Specific Item(s): 0 selected]**. Puede definir esta ruta seleccionándola entre un rango de celdas (si edita una solicitud existente) o seleccionándola de una lista de secciones.
   1. To select from a range of cells from a previous request, select **[!UICONTROL From range of cells]** and click the cell selector icon. A continuación, seleccione las celdas de un informe. ![](assets/choose_site_section_paths.png)

   1. To select from a list of site sections, select **[!UICONTROL From list]** and click **[!UICONTROL Add]**.
   1. Move elements from the **[!UICONTROL Available Elements]** column to the **[!UICONTROL Selected Elements]** column by selecting them and clicking the orange arrow. El clic **[!UICONTROL OK]**. ![](assets/move_site_section_elements.png)

   1. To save the pattern you just established, click **[!UICONTROL Save]**.
   1. Haga clic **[!UICONTROL OK]** tres veces y, a continuación, haga clic en **[!UICONTROL Finish]**. En este momento se genera la solicitud de ruta filtrada.

---
description: Filtros que aplican términos de dimensión específicos.
title: Filtros específicos
topic: Report builder
uuid: b3a8187a-3d59-4da0-abca-e933664332e3
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Filtros específicos

Filtros que aplican términos de dimensión específicos.

Se puede buscar en elementos de dimensión específicos mediante la creación de un filtro que coincida con criterios exactos. Por ejemplo, puede crear el siguiente tipo de filtro: página en [!DNL homepage.htm], [!DNL contact_us.html], [!DNL corporate_info.html].

**Para crear un filtro específico**

1. Cree o edite una solicitud y avance hasta la [!UICONTROL Request Wizard: Step 2].

   ![Resultado](assets/dimension_filter.png)

1. On the [!UICONTROL Request Wizard: Step 2], click the link next to the dimension in the grid, then choose **[!UICONTROL Filter]**.

   ![Resultado](assets/choose_page_specific01.png)

1. Enable **[!UICONTROL Specific]**, then enable one of the following options:

   * **Desde el rango de celdas:** permite seleccionar datos de celdas. Puede seleccionar:
   * **Todas las celdas del rango:** permite asignar todas las celdas del rango. El texto descriptivo explica cuántos grupos de celdas se deben seleccionar. Para asignar varios grupos de celdas, presione la tecla Ctrl conforme realice las sucesivas selecciones. Si el rango que se debe asignar solo contiene una celda, esta es la única opción disponible.
   * **Primera celda del rango:** solo es necesario seleccionar la celda superior izquierda del rango y, a continuación, elegir una dirección para los datos. Asimismo, si la solicitud tiene varios períodos, se selecciona la dirección de los mismos y si desea omitir un número establecido de celdas entre los períodos.
   * **Desde la lista:** permite seleccionar datos desde una lista en la que se puede añadir información.
1. If you enable **[!UICONTROL From List]**, select any available listed items or click **[!UICONTROL Add]**.

   When you click **[!UICONTROL Add]**, the [!UICONTROL Select From List] form displays a list of available dimension values for the current request date range, limited to the first 10,000 items. You can search across these items or click **[!UICONTROL More ...]**, which displays the [!UICONTROL Search Form], so that you can create a more detailed search for dimensions.
1. En el [!UICONTROL Select From List], haga clic en **[!UICONTROL OK]**.
1. On the [!UICONTROL Choose Page] form, save your Specific filter if you want, then click **[!UICONTROL OK]**.

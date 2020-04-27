---
description: Filtros condicionales y de clasificación que se configuran mediante la lógica booleana con las expresiones de búsqueda Y/O.
title: Filtros más utilizados
topic: Report builder
uuid: 558fa592-41be-4e66-8705-81262afe1fc7
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Filtros más utilizados

Filtros condicionales y de clasificación que se configuran mediante la lógica booleana con las expresiones de búsqueda Y/O.

Los filtros más populares son filtros de expresión que se configuran mediante la lógica booleana con condiciones Y/O, como [!UICONTROL Page does not contain]*`<product name>`* con condiciones o grupos de condiciones como [!UICONTROL Includes All], [!UICONTROL Includes Any]o [!UICONTROL Excludes All]. Puede [guardar](/help/analyze/report-builder/layout/c-filter-dimensions/saved-filters.md) estas expresiones para otra solicitud de este libro u otros libros de trabajo.

**Para crear un filtro de este tipo**

1. Cree o edite una solicitud y avance hasta la [!UICONTROL Request Wizard: Step 2].

   ![Información sobre los pasos](assets/dimension_filter.png)

1. On the [!UICONTROL Request Wizard: Step 2], click the link next to the dimension in the grid, then choose **[!UICONTROL Filter]**.
1. En el [!UICONTROL Choose Page] formulario, habilite **[!UICONTROL Most Popular]** y, a continuación, configure las siguientes opciones:

   **Clasificación de inicio:** La clasificación de inicio de una dimensión. La clasificación predeterminada de 1 indica el elemento principal de la lista de datos obtenidos. For example, for the dimension [!UICONTROL Page], a starting mark of 1 indicates the single most requested page of your site. Se puede especificar 10 u otro valor como celda de clasificación de inicio, lo que genera un informe que comienza con 10 como valor más alto. La métrica se organiza en orden descendente, por lo que los elementos de línea con la mayor actividad aparecen primero en la lista. Si se requieren más de 50 000 nombres de página en una solicitud, pero se dispone de miles de páginas en las que informar, se puede copiar la solicitud y cambiar la clasificación de inicio para recuperar los datos adecuados en bloques de 50 000.

   **Número de entradas:** ( [!UICONTROL Pivot Layout] solo) Define cuántos elementos se informan para una métrica en particular en un intervalo de fechas. Algunas métricas pueden incluir cientos de entradas para una métrica, mientas que otras pueden mostrar solamente unas cuantas entradas. For example, for the dimension [!UICONTROL Site Section], a number of entries of 25 indicates that the report shows the 25 most visited pages.

   Las flechas permiten cambiar el [!UICONTROL Starting Rank] y [!UICONTROL Number of Entries] del primer punto de datos de la hoja. De forma predeterminada, el valor [!UICONTROL Starting Rank] se establece en 1 y el valor [!UICONTROL Number of Entries] en 10. Estos valores se pueden ajustar de un mínimo de uno a un máximo de 50.000 para determinadas métricas. Cada métrica tiene su propio techo activado [!UICONTROL Number of Entries]. No se permiten valores negativos o de cero en estos campos. If you choose a [!UICONTROL Starting Rank] as 15 and [!UICONTROL Number of Entries] as 10, data requests for the metric return the 10 most visited pages, where the first most visited page is number 15 in the list for the specific date range. Las páginas más solicitadas del 15 al 25 se incluyen en orden descendente.

   >[!NOTE]
   >
   >La aplicación de filtros a solicitudes existentes produce cambios en los datos presentados. Supongamos que asignó los diez primeros [!UICONTROL Pages] a las celdas $A$1 a $A$10, con 1 para [!UICONTROL Starting Rank] y 10 para [!UICONTROL Number of Entries]. If you change these values to show 1 for [!UICONTROL Starting Rank] and only 3 for [!UICONTROL Number of Entries], the data previously filling cells $A$4 through $A$10 will no longer appear.

1. To create a search expression, click **[!UICONTROL Add]**.

   ![Información sobre los pasos](assets/expressions_define_filter.png)

1. On the [!UICONTROL Define Filter] form, configure the conditions appropriate for your needs.

   ![select_cell_icon.png](assets/select_cell_icon.png): Permite localizar una condición definida en el valor de una celda.

   **Añadir condición:** Añade una condición a la expresión. No existe límite en la cantidad de condiciones que se pueden añadir.

1. Haga clic en **[!UICONTROL OK]**.

   ![Información sobre los pasos](assets/choose_page_02.png)

1. En el [!UICONTROL Choose Page] formulario, haga clic en **[!UICONTROL Save]** para guardar la expresión.
1. Haga clic en **[!UICONTROL OK]**.

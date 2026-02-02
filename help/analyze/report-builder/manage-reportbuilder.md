---
title: Administración De Bloques De Datos En Report Builder
description: Obtenga información sobre cómo administrar bloques de datos en Report Builder.
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: 63e169b3-7e13-405e-83a4-17f2a9917ed2
source-git-commit: c3fe537967473754a3b5fe88c7b383647b2c742e
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 20%

---

# Administrar bloques de datos

Puede ver y administrar todos los bloques de datos de un libro mediante [!UICONTROL Administrador de bloques de datos]. El [!UICONTROL administrador de bloques de datos] proporciona capacidades de búsqueda, filtrado y ordenación que le permiten localizar bloques de datos específicos. Después de seleccionar uno o más bloques de datos, puede editar, eliminar o actualizar los bloques de datos seleccionados.

## Ver bloques de datos

Para ver una tabla que enumera todos los bloques de datos de un libro, seleccione ![TableManage](/help/assets/icons/TableManage.svg) **[!UICONTROL Manage]**.

![Opción Administrar para ver una lista de todos los bloques de datos.](./assets/image53.png){zoomable="yes"}

El **[!UICONTROL administrador de bloques de datos]** muestra una tabla con todos los bloques de datos presentes en un libro.

![La lista de todos los bloques de datos presentes en un libro.](./assets/image52.png){zoomable="yes"}

Puede usar ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) para seleccionar qué columnas desea mostrar.

## Ordenar bloques de datos

Puede ordenar la tabla de bloques de datos por una columna mostrada. Por ejemplo, puede ordenar bloques de datos por grupos de informes, segmentos, intervalos de fechas y otras variables.

Para ordenar la tabla de bloques de datos, seleccione un encabezado de columna. Seleccione el mismo encabezado de columna para invertir el orden.


## Buscar bloques de datos

Utilice el campo ![Buscar](/help/assets/icons/Search.svg) **[!UICONTROL _Buscar_]** para localizar cualquier elemento en la tabla de bloques de datos. Por ejemplo, puede buscar métricas contenidas en los bloques de datos o en el grupo de informes. También puede buscar fechas que aparezcan en las columnas de intervalo de fechas, fecha de modificación o fecha de última ejecución.


## Editar bloques de datos

Puede editar grupos de informes e intervalos de fechas para bloques de datos. O los segmentos aplicados a bloques de datos.

Por ejemplo, puede reemplazar un segmento existente con un nuevo segmento en uno o más bloques de datos.

1. Seleccione los bloques de datos que desea actualizar. Puede seleccionar la casilla de verificación de nivel superior para seleccionar todos los bloques de datos o puede seleccionar bloques de datos individuales.

   ![Icono de edición a lápiz](./assets/image56.png){zoomable="yes"}

1. Seleccione ![Editar](/help/assets/icons/Edit.svg) para mostrar la ventana **[!UICONTROL Edición rápida]**.

   ![Ventana de edición rápida](./assets/image58.png){zoomable="yes"}

1. Seleccione un vínculo para actualizar grupos de informes, intervalos de fechas o segmentos. En **[!UICONTROL Edición rápida]** - **[!UICONTROL Segmentos]** puede agregar, quitar o actualizar los segmentos de los bloques de datos seleccionados.

   ![El campo Agregar segmento en la ventana de edición rápida](./assets/image59.png){zoomable="yes"}

## Actualizar bloques de datos

Seleccione ![Actualizar](/help/assets/icons/Refresh.svg) para actualizar la tabla de bloques de datos.

Para comprobar si un bloque de datos se ha actualizado, consulte el icono de estado de la actualización:

- Un bloque de datos actualizado correctamente muestra ![CheckmarkCircleGreen](/help/assets/icons/CheckmarkCircleGreen.svg).

- Un bloque de datos que no se pudo actualizar muestra ![AlertRed](/help/assets/icons/AlertRed.svg).


## Eliminar bloques de datos

Para eliminar uno o varios bloques de datos:

1. Seleccione uno o varios bloques de datos.
1. Seleccione ![Eliminar](/help/assets/icons/Delete.svg).
1. Seleccione **[!UICONTROL Eliminar]** en el cuadro de diálogo **[!UICONTROL Eliminar bloque de datos]** o **[!UICONTROL Cancelar]** para cancelar la eliminación.

## Agrupar bloques de datos

Puede agrupar bloques de datos mediante el menú desplegable **[!UICONTROL Agrupar por]** o puede seleccionar un título de columna.

Para ordenar los bloques de datos por columna, seleccione el título de la columna. Para agrupar bloques de datos por grupos, seleccione un nombre de grupo en el menú desplegable **[!UICONTROL Agrupar por]**. Por ejemplo, la captura de pantalla siguiente muestra bloques de datos agrupados por grupo de informes.

Puede utilizar la agrupación para seleccionar rápidamente bloques de datos para los que desea modificar un elemento común, como un segmento.

![Administrador de bloques de datos que muestra la lista Agrupar por hoja.](./assets/group-data-blocks.png){zoomable="yes"}



<!--

# Manage Data Blocks in Report Builder

You can view and manage all data blocks in a workbook using the Data Block Manager. The Data Block Manager provides search, filter, and sort capabilities that allow you to quickly locate specific data blocks. After selecting one or more data blocks, you can edit, delete, or refresh the selected data blocks.

![The Data block manager screen.](./assets/image52.png)

## View Data Blocks

Click **Manage** to view a list of all data blocks in a workbook.

![The Manage option to view a list of all data blocks.](./assets/image53.png)

The Data Block Manager lists all data blocks present in a workbook. 

## Sort the Data Blocks list

You can sort the data block list by a displayed column. For example, you can sort the data block list by report suites, segments, date range, and other variables.

To sort the data block list, click a column heading.

![Sorting the data blocks.](./assets/image54.png)

## Search the Data Block list

Use the Search field to locate anything in the data block table. For example, you could search for metrics contained in the data blocks or report suite. You can also search for dates appearing in the date range, date modified, or last run date columns.

![Using the Search field to locate anything in the data block table.](./assets/image55.png)

## Edit Data Blocks

You can edit the report suite, date range, or the segments applied to one or more data blocks.

For example, you can replace an existing segment with a new segment in one or more data blocks.

1. Select the data blocks that you want to update. You can select the top-level check box to select all data blocks or you can select individual data blocks.

   ![The pencil edit icon](./assets/image56.png)

1. Click the edit icon to display the Quick edit window.

   ![The Quick edit window](./assets/image58.png)

1. Select a segment link to update report suites, date ranges, or segments.

   ![The Add Segment field in the Quick edit window](./assets/image59.png)

## Refresh Data Blocks

Click the refresh icon to refresh the data blocks in the list.

<img src="./assets/refresh-icon.png" width="15%" alt="Refresh icon"/>

To verify if a data block is refreshed, view the refresh status icon. 

A successfully refreshed data block displays a checkmark in a green circle: <img src="./assets/refresh-success.png" width="5%" alt="Green circle with check mark icon"/>. 

A data block that has failed to refresh displays a warning icon: <img src="./assets/refresh-failure.png" width="5%" alt="Red triangle with exclamation mark icon"/>.This makes it easy to identify if any data blocks have errors.


![Data block manager showing refresh status for each data block listed.](./assets/image512.png)

## Delete a Data Block

1. Select a data block in the Data Block manager. 
1. Click the trash can icon to delete the selected data block.

## Group Data Blocks

You can group data blocks using the **Group by** drop-down menu or you can click a column title. To sort data blocks by column, click the column title. To group data blocks by groups, select a group name from the **Group by** drop-down menu. For example, the screenshot below shows data blocks grouped by Sheet. It shows data blocks grouped by Sheet1 and Sheet2.  This is useful, for example, in the segment-replacing use case. If you have multiple segments applied to each data block, it is helpful to create a group containing all the data blocks that you want to replace. Then you can easily select and edit them all at once.

![Data block manager showing the Group by Sheet list.](./assets/group-data-blocks.png)

## Modify the Data Block Manager view

You can modify which columns are visible in the Data Block Manager window.


Click the column list <img src="./assets/image515.png" width="3%" alt="Column list icon"/> icon to select which columns are listed in the Data Block Manager. Select a column name to display the column. Deselect the column name to remove the column from view.

![Data block manager showing the column list](./assets/image516.png)

-->
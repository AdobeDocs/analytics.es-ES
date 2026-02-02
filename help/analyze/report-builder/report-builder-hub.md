---
title: Report Builder Hub
description: Obtenga información acerca de Report Builder hub.
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: e18381ea-b7d4-4d7a-9ded-23b2d06fa204
source-git-commit: ff1722416fe5062d16c12185d17271ebc2d6b624
workflow-type: tm+mt
source-wordcount: '534'
ht-degree: 22%

---

# Hub de Report Builder


El concentrador de Report Builder es el panel derecho que se muestra en el libro de Excel cuando se selecciona ![AdobeLogoRedonWhite](/help/assets/icons/AdobeLogoRedOnWhite.svg) **[!UICONTROL Report Builder]** en la barra de cinta de Excel.

Utilice Report Builder Hub para crear, actualizar, eliminar y administrar bloques de datos.

El concentrador de Report Builder contiene los botones ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Create]**, ![TableManage](/help/assets/icons/TableManage.svg) **[!UICONTROL Manage]** y ![Calendar](/help/assets/icons/Calendar.svg) **[!UICONTROL Schedule]**, el panel **[!UICONTROL Commands]** y el panel **[!UICONTROL Quick edit]**.

![concentrador de Report Builder](assets/hub51.png){zoomable="yes"}


Select

* ![Agregar círculo](/help/assets/icons/AddCircle.svg) **[!UICONTROL Crear]** para [crear nuevos bloques de datos](create-a-data-block.md).
* ![TableManage](/help/assets/icons/TableManage.svg) **[!UICONTROL Administrar]** para [administrar bloques de datos existentes](manage-reportbuilder.md).
* ![Calendario](/help/assets/icons/Calendar.svg) **[!UICONTROL Programar]** para [administrar programaciones para enviar el libro por correo electrónico](schedule-reportbuilder.md).

## Panel Comandos

Utilice el panel **[!UICONTROL Comandos]** para obtener acceso a comandos compatibles con las celdas seleccionadas o con una acción anterior.

| Comandos | Disponible cuando... | Finalidad |
|------|------------------|--------|
| ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar bloque de datos]** | El rango de celdas o celdas seleccionados forman parte de un solo bloque de datos. | Se utiliza para editar un bloque de datos. |
| ![Actualizar](/help/assets/icons/Refresh.svg) **[!UICONTROL Actualizar bloque de datos]** | La selección contiene al menos un bloque de datos. El comando actualiza solo los bloques de datos de la selección. | Utilice para actualizar uno o más bloques de datos. |
| ![ActualizarDocumento](/help/assets/icons/DocumentRefresh.svg) **[!UICONTROL Actualizar todos los bloques de datos]** | El libro contiene uno o más bloques de datos. | Se utiliza para actualizar todos los bloques de datos del libro |
| ![Enviar](/help/assets/icons/Send.svg) **[!UICONTROL Enviar libro]** | El libro contiene uno o más bloques de datos. | Use para [enviar el libro como archivo por correo electrónico](schedule-reportbuilder.md). |
| ![Copiar](/help/assets/icons/Copy.svg) **[!UICONTROL Copiar bloque de datos]** | La celda o el rango de celdas seleccionado forma parte de uno o más bloques de datos. | Se utiliza para copiar un bloque de datos. |
| ![Cortar](/help/assets/icons/Cut.svg) **[!UICONTROL Cortar bloque de datos]** | La celda o el rango de celdas seleccionado forma parte de uno o más bloques de datos. | Usar para cortar un bloque de datos. |
| ![Eliminar](/help/assets/icons/Delete.svg) **[!UICONTROL Eliminar bloque de datos]** | El rango de celdas o celdas seleccionados forman parte de un solo bloque de datos. | Usar para eliminar un bloque de datos |

## Panel de edición rápida

Al seleccionar uno o más bloques de datos en una hoja de cálculo, Report Builder muestra el panel **[!UICONTROL Edición rápida]**. Puede usar el panel **[!UICONTROL Edición rápida]** para cambiar parámetros en uno o más bloques de datos al mismo tiempo.

Los cambios que realice al usar las secciones **[!UICONTROL Edición rápida]** se aplican a todos los bloques de datos seleccionados.

### Grupos de informes

Los bloques de datos extraen datos de un grupo de informes seleccionado. Si se seleccionan varios bloques de datos en una hoja de cálculo y no se extraen datos del mismo grupo de informes, el vínculo **Grupos de informes** muestra **[!UICONTROL _Múltiples_]**.

Al cambiar el grupo de informes, todos los bloques de datos de la selección adoptan el nuevo grupo de informes. Los componentes del bloque de datos coinciden con el nuevo grupo de informes en función del ID. Si no se encuentra un componente en un bloque de datos, el componente se quita y se reemplaza por **[!UICONTROL Valor no válido]** o se muestra ![AlertRed](/help/assets/icons/AlertRed.svg) para el componente específico.

Para cambiar el grupo de informes, seleccione un nuevo grupo de informes en el menú desplegable **[!UICONTROL Grupo de informes]**.


### Intervalo de fechas

**Intervalo de fechas** muestra el intervalo de fechas para los bloques de datos seleccionados. Si se seleccionan varios bloques de datos con varios intervalos de fechas, el vínculo **[!UICONTROL Intervalo de fechas]** muestra **[!UICONTROL _Múltiple_]**.

### Segmentos

El vínculo **Segmentos** muestra una lista resumida de los segmentos utilizados por los bloques de datos seleccionados. Si se seleccionan varios bloques de datos con varios segmentos aplicados, el vínculo **Segmentos** muestra **[!UICONTROL _Varios_]**.

>[!MORELIKETHIS]
>
>[Selección de un grupo de informes](select-report-suite.md)
>[Seleccione un intervalo de fecha](select-date-range.md)
>[Trabajar con filtros](work-with-segments.md)
>

<!--

Use the Report Builder hub to create, update, delete, and manage data blocks.

The Report Builder hub contains the Create, Manage, and Schedule buttons, the COMMANDS panel, and The QUICK EDIT panel.

<img src="./assets/hub51.png" alt="Report Builder Hub"/>


## Create, Manage, and Schedule buttons

Use the Create, Manage, and Schedule buttons to create new data blocks, manage existing data blocks, or schedule datablocks.

## COMMANDS panel

Use the COMMANDS panel to access commands that are compatible with the selected cells or a previous action.

### Commands

| Commands displayed      | Available when…   | Purpose          |
|------|------------------|--------|
| Edit data block | The selected cell or cells range is part of one data block only. | Used to edit a data block |
| Refresh data block | The selection contains at least one data block. The command refreshes only the data blocks in the selection. | Used to refresh one or more data blocks |
| Refresh all data blocks | The workbook contains one or more data blocks. | Used to refresh ALL data blocks in the workbook |
| Send workbook |   |  Send a workbook on a schedule. |
| Copy data block   | The selected cell or cell range is part of one or more data blocks. | Used to copy a data block   |
| Cut data block |   | Used to cut a data block |
| Delete data block | The selected cell or cells range is part of one data block only. | Used to delete a data block |

## QUICK EDIT panel

When you select one or more data blocks in a spreadsheet, Report Builder displays the QUICK EDIT panel. You can use the QUICK EDIT panel to change parameters in a single data block or to change parameters in multiple data blocks at the same time.

![The Quick Edit panel in Report Builder](./assets/hub2.png)

The changes made using the Quick Edit sections apply to all selected data blocks.

### Report suites

Data blocks pull data from a selected report suite. If multiple data blocks are selected in a worksheet and they don't pull data from the same report suite, the **Report Suites** link displays *Multiple*.

When you change the report suite, all data blocks in the selection adopt the new report suite. Components in the data block are matched to the new report suite based on ID, for example, matching ```evars```). If a component isn't found in a data block, a warning message is displayed and the component is removed from the data block.

To change the report suite, select a new report suite from the drop-down menu.

![The Report Builder Hub showing the report suite drop-down menu.](./assets/image16.png)

### Date range

**[!UICONTROL Date range]** shows the date range for the selected data blocks. If multiple data blocks are selected with multiple date ranges, the **[!UICONTROL Date range]** link displays *Multiple*. [Learn more](/help/analyze/report-builder/select-date-range.md)

### Segments

The **Segments** link displays a summary list of the segments used by the selected data blocks. If multiple data blocks are selected with multiple segments applied, the **Segments** link displays *Multiple*. [Learn more](/help/analyze/report-builder/work-with-segments.md)

-->
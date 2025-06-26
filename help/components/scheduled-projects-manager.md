---
description: Consulte y administre informes programados en toda la organización.
title: Administrador de proyectos programados
feature: Admin Tools
exl-id: 8bc8d983-f680-48fa-8483-694c87a9ae4c
source-git-commit: d4d0eeac4f1f29e4c68e80b6fa0fe987a1fb32b9
workflow-type: tm+mt
source-wordcount: '789'
ht-degree: 42%

---

# Proyectos programados

Los proyectos programados de Analysis Workspace se pueden administrar en Adobe Analytics mediante **[!UICONTROL Componentes]** > **[!UICONTROL Proyectos programados]**.

En **[!UICONTROL Proyectos programados]**, puede editar y eliminar la programación recurrente de proyectos.  La [lista de proyectos programados](#scheduled-project-list) muestra los elementos que ha creado un usuario en particular. Si la cuenta del usuario está desactivada en la aplicación, se detendrán todos los envíos programados.

![Interfaz de proyectos programados](assets/scheduled-projects.png)

## Lista de proyectos programados

La lista Proyectos programados ➊ muestra columnas para:

| Columna | Descripción |
| --- | --- |
| ![SeleccionarCuadro](/help/assets/icons/SelectBox.svg) | Cuando se seleccionan uno o más proyectos programados, aparece una barra de acciones azul en la parte inferior de la interfaz Proyectos programados. Consulte las [acciones](#actions) para obtener más información.  |
| ![Star](/help/assets/icons/Star.svg) | Seleccione para favorecer a ![Star](/help/assets/icons/Star.svg) o para anular el favor de ![StarOutline](/help/assets/icons/StarOutline.svg) en un proyecto programado. |
| **[!UICONTROL ID de programación]** | ID que se utiliza principalmente con fines de depuración. |
| **[!UICONTROL Nombre]** | Nombre de este proyecto.<br/>Seleccione ![EsquemaDeInformación](/help/assets/icons/InfoOutline.svg) para ver más detalles del proyecto programado.<br/>Seleccione ![Más](/help/assets/icons/More.svg) para abrir un menú contextual. Desde este menú puede:<ul><li>![Eliminar](/help/assets/icons/Delete.svg) **[!UICONTROL Eliminar]** un proyecto programado.</li><li>![Etiquetas](/help/assets/icons/Labels.svg) **[!UICONTROL Etiquetar]** un proyecto programado.</li><li>![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Apruebe]** un proyecto programado.</li><li>![ArchivoCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Exportar CSV]**: exporte un proyecto programado a un archivo CSV.</li></ul> |
| **[!UICONTROL Propietario]** | La persona que creó el proyecto y es propietaria de él. |
| **[!UICONTROL Etiquetas]** | (opcional) El etiquetado es una buena forma de organizar los proyectos. Todos los usuarios pueden crear etiquetas y aplicar una o más a un proyecto. Sin embargo, solo verá las etiquetas de los proyectos que sean suyos o que se hayan compartido con usted. |
| **[!UICONTROL Entregado a]** | Destinatarios de este proyecto programado. |
| **[!UICONTROL Fecha de caducidad]** | Puede establecer la fecha de caducidad en un máximo de un año, independientemente de la frecuencia de programación. |
| **[!UICONTROL Frecuencia]** | La frecuencia con la que desea que este proyecto programado se envíe a uno o varios destinatarios. |
| **[!UICONTROL Hora de ejecución]** | A qué hora del día se envía este proyecto programado. |
| **[!UICONTROL Cantidad de consultas]** | Número de consultas de este proyecto. |
| **[!UICONTROL El intervalo de fecha más largo]** | Intervalo de fecha más largo definido para el proyecto programado. Este valor puede ser relevante para investigar los problemas de rendimiento. Consulte [Administrador de actividades de creación de informes](/help/admin/admin/reporting-activity-manager/reporting-activity-overview.md) para obtener más información. |
| **[!UICONTROL Cantidad de consultas]** | Número de consultas ejecutadas para el proyecto programado. Este valor puede ser relevante para investigar los problemas de rendimiento. Consulte [Administrador de actividades de creación de informes](/help/admin/admin/reporting-activity-manager/reporting-activity-overview.md) para obtener más información. |


Puede usar ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) para configurar qué columnas mostrar.

Busque un proyecto programado con ![Buscar](/help/assets/icons/Search.svg). También puede ver si se aplica algún filtro desde el panel Filtros. Para quitar un filtro, seleccione ![CrossSize75](/help/assets/icons/CrossSize75.svg) para un filtro. Para quitar todos los filtros, seleccione **[!UICONTROL Borrar todo]**.

Para editar un proyecto programado, seleccione su título. Utilice el cuadro de diálogo **[!UICONTROL Editar proyecto programado]** para actualizar los detalles de la programación. Ver [Enviar archivos a otros](../analyze/analysis-workspace/curate-share/t-schedule-report.md) para obtener más detalles.

![Editar proyecto programado](assets/edit-scheduled-project.png)

Seleccione **[!UICONTROL Actualizar]** para actualizar la programación.




## Acciones

Las siguientes son acciones comunes en el administrador de proyectos programados. Puede seleccionar acciones en el menú contextual o en la barra de acciones azul al seleccionar uno o varios proyectos programados.

| Icono | Acción | Descripción |
|:---:|---|---|
| ![Cerrar](/help/assets/icons/Close.svg) | **[!UICONTROL *x *seleccionada]** | Seleccione para anular la selección de los proyectos programados seleccionados. |
| ![Eliminar](/help/assets/icons/Delete.svg) | **[!UICONTROL Eliminar]** | Eliminar los proyectos programados seleccionados para el proyecto; los proyectos no se eliminan. |
| ![Etiquetas](/help/assets/icons/Labels.svg) | **[!UICONTROL Etiqueta]** | Etiquete los proyectos programados seleccionados. En **[!UICONTROL Etiquetar proyectos programados]**, seleccione las etiquetas y seleccione **[!UICONTROL Guardar]** para guardar. |
| ![Círculo de verificación](/help/assets/icons/CheckmarkCircle.svg) | **[!UICONTROL Aprobar]** | Apruebe los proyectos programados seleccionados. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL Exportar a CSV]** | Exportar los proyectos programados seleccionados a un archivo denominado `Export Scheduled Projects List.csv`. |


## Filtrar

Puede filtrar los proyectos programados [Lista de proyectos programados](#scheduled-project-list) mediante el panel de filtro ➌. Para mostrar u ocultar el panel de filtro, utilice ![Filtro](/help/assets/icons/Filter.svg).

El panel de filtro consta de las siguientes secciones.

### Etiquetas

| Etiquetas | Descripción |
|---|---|
| ![Etiquetas](/help/components/assets/scheduledprojects-filter-tags.png){width="300"} | La sección **[!UICONTROL Etiquetas]** le permite filtrar las etiquetas. <ul><li>Utilice ![Búsqueda](/help/assets/icons/Search.svg) **[!UICONTROL Búsqueda de etiquetas]** para buscar las etiquetas que desea utilizar para filtrar.</li><li>Puede seleccionar más de una etiqueta. Las etiquetas disponibles dependen de las selecciones realizadas en otras secciones del panel de filtro.</li><li>Los números indican lo siguiente:<ul><li>7︎⃣: número de proyectos programados asociados con la etiqueta específica.</li></ul></li></ul> |


### Propietarios

| Propietario | Descripción |
|---|---|
| ![Propietarios](/help/components/assets/scheduledprojects-filter-owners.png){width="300"} | La sección **[!UICONTROL Propietario]** le permite filtrar por los propietarios. <ul><li>Utilice ![Búsqueda](/help/assets/icons/Search.svg) *Búsqueda de propietarios* para buscar los propietarios que desea usar para filtrar.</li><li>Puede seleccionar más de un propietario. Los propietarios disponibles dependen de las selecciones realizadas en otras secciones del panel de filtros.</li><li>Los números indican lo siguiente:<ul><li>4︎⃣: número de proyectos programados asociados con el propietario específico.</li></ul></li></ul> |


### Otros filtros

| Otros filtros | Descripción |
|---|---|
| ![Otros filtros](/help/components/assets/scheduledprojects-filter-otherfilters.png){width="300"} | La sección **[!UICONTROL Otros filtros]** le permite filtrar otros filtros predefinidos.<ul><li>Puede seleccionar una o varias de las siguientes opciones:<ul><li> **[!UICONTROL Caducado]**: filtro en proyectos programados caducados.</li><li>**[!UICONTROL Error]**: filtro en proyectos programados para los que la programación ha fallado.</li></ul>Lo que puede seleccionar depende de la función y los permisos.</li><li>Puede seleccionar más de un otro filtro. Los otros filtros disponibles dependen de las selecciones realizadas en otras secciones del panel de filtros.</li><li>Los números indican lo siguiente:<ul><li>4︎⃣: número de proyectos programados asociados con el otro filtro específico.</li></ul></li></ul> |


<!--
# Scheduled projects

Scheduled Analysis Workspace projects can be managed under **Analytics > Components > Scheduled Projects**.

When you manage scheduled projects, you can edit and delete recurring project schedules:

*  Change the file type (.csv or PDF)
*  Update the project description
*  Add or remove recipients
*  Change the frequency

To modify a scheduled project

1.  Select **Analytics > Components > Scheduled Projects**.
1.  Search for a schedule in the search bar or by using the filter options in the left rail. You can filter by [!UICONTROL Tags], [!UICONTROL Owners], [!UICONTROL Favorites], and more.

![Screenshot showing the scheduled projects list with the column displaying title, owner, tags, delivered to, and other columns described in the Available columns section.](assets/scheduled-project-manager2.png)

## Available columns

| Field | Description |
| --- | --- |
| [!UICONTROL Favorites] | Selecting the star icon makes this schedule a favorite. |
| [!UICONTROL Schedule ID] | This ID is used mainly for debugging purposes. |
| [!UICONTROL Title and description] | Title and description of this project. |
| [!UICONTROL Owner] | The person who created and owns the project. |
| [!UICONTROL Tags] | (optional) Tagging is a good way to organize projects. All users can create tags and apply one or more tags to a project. However, you can see tags only for those projects that you own or that have been shared with you.  |
| [!UICONTROL Delivered to] | The recipient(s) of this scheduled project. |
| [!UICONTROL Expiration date] | For any scheduled project frequency, you can set the expiration date for up to one year in the future. |
| [!UICONTROL Frequency] | How often you want to have this schedule project sent to the recipient(s). |
| [!UICONTROL Execution time] | At what time of day this scheduled project gets sent. |
| [!UICONTROL Number of queries] | The number of queries against this project. | 

## Common actions

The following are common actions in the Scheduled Projects manager:

|Action|Description|
|---|---|
|**[!UICONTROL Edit]**|Select the title of the schedule to update its delivery settings.|
|**[!UICONTROL Delete]**|Select the scheduled project in the list and then click Delete from the menu. This will delete the selected schedule for the project; the project itself will not be deleted.|
|**[!UICONTROL Tag]**|Select the scheduled project in the list and then choose "Tag" or "Approve" to organize your schedules and make them easier to search for.|
|**[!UICONTROL View failed schedules]**|Navigate to the left rail > Other filters > Failed to see schedules that have failed.|
|**[!UICONTROL View expired schedules]**|Navigate to the left rail > Other filters > Expired to see schedules that have expired. Click the title of the schedule to setup a new delivery schedule.|
|**[!UICONTROL View schedule ID]**|Navigate to column options in the top right and add the Schedule ID column to the table. The scheduled ID is often useful for debugging.|

The Scheduled Projects manager shows the items that a specific user created. If the user account is disabled in the application, all scheduled deliveries stop. Scheduled project ownership can be transferred to a new user under **Admin** > **Analytics Users & Assets** > **Transfer Assets**.
-->
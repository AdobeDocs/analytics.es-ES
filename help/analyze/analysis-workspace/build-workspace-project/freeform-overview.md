---
description: Obtenga información sobre los conceptos básicos de un proyecto de Workspace.
keywords: Analysis Workspace
title: Información general sobre Proyectos
feature: Workspace Basics
role: User, Admin
exl-id: 75c551de-297e-4c45-95e6-77472be6628a
source-git-commit: d4d0eeac4f1f29e4c68e80b6fa0fe987a1fb32b9
workflow-type: tm+mt
source-wordcount: '1618'
ht-degree: 91%

---

# Información general sobre Proyectos

Los proyectos de Workspace le permiten paneles, tablas y visualizaciones de datos para crear un análisis y compartirlo con cualquier persona de su organización. Antes de iniciar el primer proyecto, aprenda a acceder a sus proyectos, así como a navegar por ellos y a gestionarlos.

Para acceder a los proyectos en Adobe Analytics, seleccione **[!UICONTROL Workspace]**.  El administrador de **[!UICONTROL proyectos]** enumera todos los proyectos que posee o que han compartido con usted. El administrador de proyectos con la lista de proyectos también es la página de aterrizaje predeterminada para Adobe Analytics, a menos que haya configurado lo contrario en Preferencias.

![Página de destino del proyecto que muestra la lista de proyectos.](assets/projects.png)


## Área de título

Desde el área de título ➊ puede crear un proyecto, crear una carpeta, editar sus preferencias y mostrar u ocultar un panel con mosaicos adicionales.

* Para mostrar u ocultar un panel izquierdo que le permita seleccionar entre **[!UICONTROL Proyectos]** y **[!UICONTROL Aprendizaje]**, seleccione ![Carril](/help/assets/icons/Rail.svg).
* El título muestra Proyectos que, opcionalmente, se añadirán con una ruta a la carpeta seleccionada. Por ejemplo [!UICONTROL Proyectos] > **[!UICONTROL Carpeta de la compañía]**. Puede seleccionar elementos de subcarpeta individuales para ir directamente a la carpeta específica.
* Para mostrar los mosaicos de un [**[!UICONTROL proyecto en blanco]**](create-projects.md), [**[!UICONTROL informe de valoración móvil en blanco]**](/help/analyze/mobile-app/create-scorecard.md), **[!UICONTROL Abrir la documentación]** y **[!UICONTROL Abrir notas de la versión]**, seleccione ![ChevronDown](/help/assets/icons/ChevronDown.svg) **[!UICONTROL Mostrar más]**. Para ocultar el área con mosaicos, seleccione ![ChevronDown](/help/assets/icons/ChevronDown.svg) **[!UICONTROL Mostrar menos]**.
* En función de lo que selecciones mostrar, con el [selector Mostrar](#show-selector), puedes editar las preferencias y realizar acciones en la carpeta actual visible en **[!UICONTROL Proyectos]**:

  | Acción | Descripción |
  |---|---|
  | **[!UICONTROL Crear proyecto]** | Seleccione para [crear un nuevo proyecto](create-projects.md): |
  | **[!UICONTROL Crear carpeta]** | Seleccione para [crear una nueva carpeta](workspace-folders/create-folders.md) |
  | ![UserAdmin](/help/assets/icons/UserAdmin.svg) **[!UICONTROL Editar preferencias]** | [Editar preferencias](/help/analyze/analysis-workspace/user-preferences.md) para todos sus proyectos. Cuando la ruta de exploración reduce el espacio, esta acción forma parte del submenú ![Más](/help/assets/icons/More.svg). |
  | **[!UICONTROL Agregar proyectos]** | Seleccione para [añadir proyectos](workspace-folders/add-projects.md) a la carpeta actual. Cuando la ruta de exploración reduce el espacio, esta acción forma parte del submenú ![Más](/help/assets/icons/More.svg). |
  | **[!UICONTROL Cambiar el nombre de la carpeta]** | [Cambia el nombre](workspace-folders/manage-folders.md#rename-folders) de la carpeta actual. |
  | **[!UICONTROL Mover carpeta]** | [Mueve](workspace-folders/manage-folders.md#move-folders) la carpeta actual. |
  | **[!UICONTROL Eliminar carpeta]** | [Elimina](workspace-folders/manage-folders.md#delete-folders) la carpeta actual. |




## Lista de proyectos


La lista del proyecto ➋ muestra todos los proyectos que posee y que han compartido con usted. La lista tiene las siguientes columnas:

| Columna | Descripción |
| --- | --- | 
| ![SeleccionarCuadro](/help/assets/icons/SelectBox.svg) | Cuando se seleccionan uno o más proyectos, aparece una barra de acciones azul en la parte inferior de la interfaz de proyecto. Consulte las [acciones](#actions) para obtener más información.  |
| ![StarOutline](/help/assets/icons/StarOutline.svg) | Selecciona para favorecer a ![Star](/help/assets/icons/Star.svg) o para desfavorecer a ![StarOutline](/help/assets/icons/StarOutline.svg) un proyecto. |
| **[!UICONTROL Título y descripción]** | Para editar el proyecto, seleccione el vínculo del título, que abre el [proyecto de Workspace](/help/analyze/analysis-workspace/home.md). Los proyectos compartidos con usted se indican con ![Compartir](/help/assets/icons/ShareAlt.svg). Seleccione ![InfoOutline](/help/assets/icons/InfoOutline.svg) para mostrar una ventana emergente con más detalles para el conjunto de datos. Seleccione ![Más](/help/assets/icons/More.svg) para abrir un menú contextual con acciones. Consulte las [Acciones](#actions) para obtener más información.  |
| **[!UICONTROL Tipo]** | Un proyecto de Workspace, una carpeta ![FolderUser](/help/assets/icons/FolderUser.svg) o un [Cuadro de resultados móvil](/help/analyze/mobile-app/home.md). |
| **[!UICONTROL Etiquetas]** | Las etiquetas aplicadas al proyecto.  |
| **[!UICONTROL Programado]** | Si un proyecto está programado para enviarse por correo electrónico a los destinatarios. Las opciones son ![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL On]** o ![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL Off]**. Ver [Enviar datos de proyecto a otras personas](/help/analyze/analysis-workspace/curate-share/t-schedule-report.md). |
| **[!UICONTROL Vínculo compartido (cualquiera)]** | Si un proyecto se comparte con alguien, incluso con personas que no tienen acceso a Analysis Workspace. Las opciones son ![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL Activo]** o ![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL Inactivo]**. Vea [Compartir un proyecto con alguien (no se requiere inicio de sesión)](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-a-project-with-anyone-no-login-required) en [Compartir proyectos](/help/analyze/analysis-workspace/curate-share/share-projects.md) para obtener más información. |
| **[!UICONTROL Función del proyecto]** | Su función en el proyecto. Las opciones son: Editar, Duplicar y Ver. Consulte las [funciones del proyecto](/help/analyze/analysis-workspace/curate-share/curate.md) para obtener más información. |
| **[!UICONTROL Grupo de informes]** | Grupo de informes al que está asociado el proyecto. |
| **[!UICONTROL Propietario]** | Persona que ha creado el proyecto (usted mismo o alguien que haya compartido su proyecto). |
| **[!UICONTROL Compartido con]** | Usuarios con los que se ha compartido el proyecto. |
| **[!UICONTROL Última modificación]** | Fecha y hora de última modificación del proyecto. |
| **[!UICONTROL Última apertura]** | Fecha y hora de última modificación del proyecto. |
| **[!UICONTROL ID de componente]** | El ID del componente. |
| **[!UICONTROL El intervalo de fecha más largo]** | El intervalo de fecha más largo de cualquiera de los paneles o visualizaciones del proyecto. |
| **[!UICONTROL Cantidad de consultas]** | Cantidad total de consultas contenidas en el proyecto.  |
| **[!UICONTROL Ubicación]** | Carpeta en la que reside el proyecto. |

Pase el puntero por encima de cualquier encabezado de columna para ver ![ChevronDown](/help/assets/icons/ChevronDown.svg) y seleccione en el menú contextual:

* **[!UICONTROL Orden ascendente]**
* **[!UICONTROL Orden descendente]**
* **[!UICONTROL Cambiar tamaño de columna]**. Aparecerá una línea azul para ayudarle a cambiar el tamaño de la columna.

### Acciones

Puede realizar acciones en uno o más proyectos mediante el menú contextual ![Más](/help/assets/icons/More.svg) o la barra de acciones azul.

| Icono | Acción | Descripción |
|:---:| ---|---|
| ![CrossSize75](/help/assets/icons/Close.svg) | **[!UICONTROL *x *seleccionado]** | Anule la selección de los proyectos y carpetas seleccionados y elimine la barra de acciones azul. |
| ![Eliminar](/help/assets/icons/Delete.svg) | **[!UICONTROL Eliminar]** | Elimine uno o varios proyectos o carpetas. Se le pedirá una confirmación. |
| ![Compartir](/help/assets/icons/ShareAlt.svg) | **[!UICONTROL Compartir]** | Uso compartido de un proyecto. Consulte [Compartir un proyecto](/help/analyze/analysis-workspace/curate-share/share-projects.md) para obtener más información. |
| ![Editar](/help/assets/icons/Edit.svg) | **[!UICONTROL Cambiar el nombre]** | Cambiar nombre a un proyecto. Abre un cuadro de diálogo **[!UICONTROL Cambiar nombre: *nombre de proyecto *]**. Escriba un nombre nuevo y seleccione**[!UICONTROL Guardar ]**. |
| ![Copiar](/help/assets/icons/Copy.svg) | **[!UICONTROL Copiar]** | Copie uno o varios proyectos. Proyecto no obtiene el mismo nombre y sufijo `(Copy)`. |
| ![PinOnff](/help/assets/icons/PinOff.svg) | **[!UICONTROL Anclar]** o **[!UICONTROL Desanclar]** | Anclar o desanclar uno o más proyectos o carpetas. Los proyectos y carpetas anclados aparecen en la parte superior de la lista e ignoran el orden de clasificación especificado. |
| ![Flecha arriba](/help/assets/icons/ArrowUp.svg) | **[!UICONTROL Subir]** | Mueva un proyecto o una carpeta anclados hacia arriba en la lista de proyectos. |
| ![Flecha abajo](/help/assets/icons/ArrowDown.svg) | **[!UICONTROL Bajar]** | Mueva un proyecto o una carpeta anclados hacia abajo en la lista de proyectos. |
| ![Etiqueta](/help/assets/icons/Label.svg) | **[!UICONTROL Etiqueta]** | Etiquete uno o varios proyectos o carpetas. Se muestra el cuadro de diálogo **[!UICONTROL Componentes de etiqueta]** para seleccionar una o más etiquetas. Selecciona **[!UICONTROL Guardar]** para guardar las etiquetas de los proyectos o carpetas seleccionadas. |
| ![Círculo de verificación](/help/assets/icons/CheckmarkCircle.svg) | **[!UICONTROL Aprobar]** o **[!UICONTROL Desaprobar]** | Aprobar o desaprobar un proyecto. Solo los administradores pueden aprobar proyectos. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL Exportar CSV]** | Exportar los proyectos seleccionados a un archivo CSV con el nombre `Project List.csv`. |
| ![Añadir proyecto](/help/assets/icons/ProjectAdd.svg) | **[!UICONTROL Añadir proyectos]** | Añada uno o más proyectos a una carpeta seleccionada. En **[!UICONTROL Añadir proyectos]** puede seleccionar uno o más proyectos. Seleccione **[!UICONTROL Añadir]** para añadir los proyectos a la carpeta. Consulte [Añadir proyectos a carpetas](workspace-folders/add-projects.md#from-inside-a-folder) para obtener más información. |
| ![FolderAddTo](/help/assets/icons/FolderAddTo.svg) | **[!UICONTROL Mover a]** | Mueva uno o más proyectos seleccionados a una carpeta. En **[!UICONTROL Seleccionar carpeta]**, seleccione la carpeta a la que desea mover el proyecto seleccionado y seleccione **[!UICONTROL Mover]**. Consulte [Añadir proyectos a carpetas](workspace-folders/add-projects.md#from-the-project-list) para obtener más información. |



## Mostrar selector

Puede cambiar la apariencia de la interfaz de Proyectos mediante los selectores de **[!UICONTROL Mostrar]** ➌. El selector **[!UICONTROL Mostrar]** define qué opciones están disponibles en el [Área de título](#title-area) y qué columnas se muestran en la [Lista de proyectos](#project-list).

* Para cambiar las opciones disponibles para el [Área de título](#title-area), seleccione **[!UICONTROL Mostrar]** **[!UICONTROL Todos los proyectos]** o **[!UICONTROL Mostrar]** **[!UICONTROL Carpetas y proyectos]**.

* Para definir qué columnas desea mostrar en la [Lista de proyectos](#project-list), seleccione ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) y en el cuadro de diálogo **[!UICONTROL Personalizar tabla]**, seleccione o anule la selección de columnas. Seleccione **[!UICONTROL Aplicar]** para aplicar la personalización. Consulte [Lista de proyectos](#project-list) para obtener más información sobre las columnas.

## Panel Filtro

Puede filtrar los proyectos y las carpetas de la [Lista de proyectos](#project-list) mediante el panel de filtro ➍. Para mostrar u ocultar el panel de filtro, utilice ![Filtro](/help/assets/icons/Filter.svg).

El panel de filtro consta de las siguientes secciones.

### Etiquetas

| Etiquetas | Descripción |
|---|---|
| ![Etiquetas](assets/projects-filters-tags.png){width="300"} | La sección **[!UICONTROL Etiquetas]** le permite filtrar las etiquetas. <ul><li>Utilice ![Búsqueda](/help/assets/icons/Search.svg) *Búsqueda de etiquetas* para buscar las etiquetas que desea utilizar para filtrar.</li><li>Puede seleccionar más de una etiqueta. Las etiquetas disponibles dependen de las selecciones realizadas en otras secciones del panel de filtro.</li><li>Los números indican lo siguiente:<ul><li>**2︎⃣**: el número de etiquetas disponibles para los proyectos resultantes del filtro actual.</li><li>7︎⃣: el número de proyectos asociados a la etiqueta específica.</li></ul></li></ul> |


### Grupos de informes

| Grupos de informes | Descripción |
|---|---|
| ![Grupo de informes](assets/projects-filters-reportsuites.png){width="300"} | La sección **[!UICONTROL Grupos de informes]** le permite filtrar los grupos de informes. <ul><li>Usted usa ![Buscar](/help/assets/icons/Search.svg) *Buscar grupos de informes* para buscar los grupos de informes que desea usar para filtrar.</li><li>Puede seleccionar más de un grupo de informes. Los grupos de informes disponibles dependen de las selecciones realizadas en otras secciones del panel de filtros.</li><li>Los números indican lo siguiente:<ul><li>**3︎⃣**: número de grupos de informes disponibles para los proyectos resultantes del filtro actual.</li><li>4︎⃣: número de proyectos asociados con el grupo de informes específico.</li></ul></li></ul> |


### Propietarios

| Propietario | Descripción |
|---|---|
| ![Propietarios](assets/projects-filters-owners.png){width="300"} | La sección **[!UICONTROL Propietario]** le permite filtrar por los propietarios. <ul><li>Utilice ![Búsqueda](/help/assets/icons/Search.svg) *Búsqueda de propietarios* para buscar los propietarios que desea usar para filtrar.</li><li>Puede seleccionar más de un propietario. Los propietarios disponibles dependen de las selecciones realizadas en otras secciones del panel de filtros.</li><li>Los números indican lo siguiente:<ul><li>**3︎⃣**: el número de propietarios disponibles para los proyectos resultantes del filtro actual.</li><li>4︎⃣: el número de proyectos asociados al propietario específico.</li></ul></li></ul> |


### Tipo

| Tipo | Descripción |
|---|---|
| ![Tipo](assets/projects-filters-type.png){width="300"} | La sección **[!UICONTROL Tipo]** le permite filtrar el tipo de proyectos o carpetas.<ul><li>Puede seleccionar una o varias de las siguientes opciones:<ul><li> **[!UICONTROL carpeta]**</li><li>**[!UICONTROL Proyecto del Espacio de trabajo]**</li><li>**[!UICONTROL Informe de valoración móvil]**</li></ul> <li>Puede seleccionar más de un otro filtro. Los otros filtros disponibles dependen de las selecciones realizadas en otras secciones del panel de filtros.</li><li>Los números indican lo siguiente:<ul><li>**5︎⃣**: el número de otros filtros disponibles para los proyectos resultantes del filtro actual.</li><li>4︎⃣: el número de proyectos asociados al otro filtro específico.</li></ul></li></ul> |


### Otros filtros

| Otros filtros | Descripción |
|---|---|
| ![Otros filtros](assets/projects-filters-others.png){width="300"} | La sección **[!UICONTROL Otros filtros]** le permite filtrar otros filtros predefinidos.<ul><li>Puede seleccionar una o varias de las siguientes opciones:<ul><li> **[!UICONTROL Mostrar todo]**</li><li>**[!UICONTROL Compartidos conmigo]**</li><li>**[!UICONTROL Míos]**</li><li>**[!UICONTROL Aprobado]**</li><li>**[!UICONTROL Favoritos]**</li></ul> Lo que puede seleccionar depende de la función y los permisos.</li><li>Puede seleccionar más de un otro filtro. Los otros filtros disponibles dependen de las selecciones realizadas en otras secciones del panel de filtros.</li><li>Los números indican lo siguiente:<ul><li>**5︎⃣**: el número de otros filtros disponibles para los proyectos resultantes del filtro actual.</li><li>4︎⃣: el número de proyectos asociados al otro filtro específico.</li></ul></li></ul> |

## Buscar

Utilice el área de búsqueda ➎ para buscar proyectos y carpetas mediante el campo ![Búsqueda](/help/assets/icons/Search.svg). Empiece a escribir y la [lista de proyectos](#project-list) se filtrará automáticamente en la entrada de la búsqueda.

El área Búsqueda también muestra los filtros aplicados desde el panel Filtro.

* Para quitar un filtro, seleccione ![CrossSize75](/help/assets/icons/CrossSize75.svg) en el filtro.
* Para quitar todos los filtros, seleccione Borrar todo.

Si el espacio es limitado para mostrar los filtros individuales, verá **[!UICONTROL Segmentado por *x* filtros]**.

* Para quitar un filtro:

   1. Utilice **[!UICONTROL *x *filtros]**![ChevronDown](/help/assets/icons/ChevronDown.svg) en la parte superior para abrir un menú contextual que enumere los tipos de filtros y los filtros individuales.
   1. Seleccione ![CrossSize75](/help/assets/icons/CrossSize75.svg) para quitar un filtro.


<!--

# Projects overview

Workspace projects allow you to combine data components, tables and visualizations to craft your analysis and share with anyone in your organization. Before starting your first project, learn about how to access, navigate and manage your projects. 

Here is a video on how to build a Workspace project:


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Build a Workspace project](https://video.tv.adobe.com/v/334076?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


## Project list {#project-list}

When you first go to **[!UICONTROL Analytics]** > **[!UICONTROL Workspace]**, the page lists all the projects you own or have been shared to you. This page is also the landing page for Adobe Analytics, unless you have previously set a custom landing page. 

The Projects page contains the following information: 

|  Element  | Description  |
|---|---|
| [Edit preferences](/help/analyze/analysis-workspace/user-preferences.md) | Manage settings for Analysis Workspace and its related components for all new projects or panels that you create.  |
| [Create folder](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/create-folders.md)  | Add a new folder or subfolder to the list of projects and folders. |
| [Create project](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md)  | Start a new project from scratch or from a report.  |
|  Show more  | This selection reveals options for creating a blank project or mobile scorecard, [viewing training tutorials](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/analysis-workspace-basics/analysis-workspace-introduction), or [viewing release notes](/help/release-notes/latest.md).  |
| ![Show filters](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) | To show or hide filters. You can filter on tags, report suite, owners, type (project, folder, mobile scorecard), and other filters. | 
| ![Search](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) | Use the search field to search for folders, Workspace projects or mobile scorecards. |
| Show Folders & Projects| Choose whether to show the folder structure of projects. For more information, see [About Folders in Analytics](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md). |
|  ![Customize table](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg) | This icon allows you to customize the columns you see for each project in the projects list.  |

The list of projects can display the following columns:

|  Column  | Description  |
|---|---|
| [!UICONTROL Name]  | Name of the Workspace project. Select ![Info](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) to show a popup with more details on a project or folder. Select ![More](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) to show actions available. See [Manage projects](#manage-projects) for more details.  | 
| [!UICONTROL Type] | Indicates whether this entry is a Workspace project, a folder, or a [Mobile scorecard](https://experienceleague.adobe.com/en/docs/analytics/analyze/mobapp/home). |
| [!UICONTROL Tags]  |Tags that were applied to the project.  |
| [!UICONTROL Scheduled] | Indicates whether projects are scheduled to be emailed to recipients. See [Schedule projects](/help/analyze/analysis-workspace/curate-share/t-schedule-report.md). |
| Shared link (anyone) | Projects can be shared with anyone, even with people who don't have access to Analysis Workspace. This column shows whether projects have been shared in this way. See [Share a project with anyone (no login required)](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-public-link) in [Share projects](/help/analyze/analysis-workspace/curate-share/share-projects.md) for more information. |
| [Project Role](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/curate-share/share-projects) | Indicates your role for the project - owners, edit, duplicate, view. |
| [!UICONTROL Report suite] | The report suite that the project is associated with. |
| [!UICONTROL Owner]  | The person who created this project (either you or someone who shared the project with you.)  |
| [!UICONTROL Shared with]  | Users that the project has been shared with.  |
| [!UICONTROL Last Modified]  | Date and time when the project was last modified.  |
| [!UICONTROL Last Opened]  | Date and time when the project was last opened.  |
| [!UICONTROL Last Used] | Date and time when the project was last used. | 
| [!UICONTROL Project ID]  | The ID of the project.  |
| [!UICONTROL Longest Date Range]  | The longest date range of the project.  |
| [!UICONTROL Number of Queries]  | The total number of queries contained in the project.  |
| [!UICONTROL Location]  | The folder where the project resides.  |

### Manage projects

To manage projects, select one or more projects from the project list. 

From the blue action bar, you can select the following actions:

| Action | Description | 
|---|---|
| ![Delete](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) Delete | When selected, a confirmation dialog prompts you to confirm the deletion of a Workspace project or Mobile scorecard. Select **[!UICONTROL OK]** to confirm. |
| ![Share](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Share_18_N.svg) Share | This action allows you to share your project. See [Share projects](../curate-share/share-projects.md).|
| ![Rename](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) Rename | Opens up a **[!UICONTROL Rename: *name*]** dialog to rename your project. Select **[!UICONTROL Save]** to save the new name for the project. |
| ![Copy](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) Copy | Immediately copies the selected project to a new project with name *original name* (Copy).  |
| ![Pin](https://spectrum.adobe.com/static/icons/workflow_18/Smock_PinOff_18_N.svg) Pin | Immediately pins the project to the top of the list. Adds the ![Pin](https://spectrum.adobe.com/static/icons/workflow_18/Smock_PinOff_18_N.svg) indicator. |
| ![Tag](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Label_18_N.svg) Tag | Opens up the **[!UICONTROL Tag Project]** dialog. You can select an existing tag or add new tags. Select **[!UICONTROL Save]** to save the tags for the project. |
| ![(Un-)Approve](https://spectrum.adobe.com/static/icons/workflow_18/Smock_CheckmarkCircle_18_N.svg) Approve or Unapprove |  Approves or unapproves the project.  |
| ![Export CSV](https://spectrum.adobe.com/static/icons/workflow_18/Smock_FileCSV_18_N.svg) Export CSV | Immediately downloads a file containing a comma-separated value list of the projects. |
| ![Move to](https://spectrum.adobe.com/static/icons/workflow_18/Smock_FolderAddTo_18_N.svg) Move to | This action allows you to move the project to a folder. In the **[!UICONTROL Select Folder]** dialog, select a folder from the **[!UICONTROL Folder]** list, and select **[!UICONTROL Move]**. | 


## Menu bar {#menu-bar}

Within a project, the menu provides options for managing your project, adding components, finding help, and more. You can also access each menu option by keyboard [shortcuts](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys).


|  Menu item  | Description  |
|---|---|
|  Project  | This menu includes common actions for project management, including New, Open, Save, Save as, and [Save as company report](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md). You can also refresh the entire project to retrieve the most recent data and definitions by clicking Refresh Project. [Download CSV and PDF](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/curate-share/download-send) options enable you to export data from Workspace. [Project Info & Settings](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/build-workspace-project/freeform-overview) offers many options for managing your project.  |
|  Edit  | Undo or redo your last action. Clear All resets your project to a blank starting point. |
|  Insert  | Insert new panels or visualizations from this menu. You can also insert new panels and visualizations from the left rail.  |
|  [Components](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/components/analysis-workspace-components)  | Create new segment, calculated metric, date range, or alert components from your project. You can also create new components from the left rail. If your component definitions have recently changed, Refresh Components retrieves the latest definitions. |
|  [Share](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/curate-share/send-schedule-files)  | Curate, share and schedule PDF/CSV projects to recipients in your organization.  |
|  Help  | Access help documentation, videos, and the Analytics [Experience League community](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community). Manage the visibility of Workspace tips as well as the [debugger](https://developer.adobe.com/analytics-apis/docs/2.0/). Find details about Workspace and factors that impact project [performance](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/workspace-faq/optimizing-performance).  |
|  Share button or Owner  | If you are in an Own or Edit for the project, the Share button in the top-right gives you one-click access to manage your project recipients. If you are in a Duplicate or View role for the project, you see the project owner's name. |

### Project Info & Settings {#info-settings}

>[!CONTEXTUALHELP]
>id="workspace_project_countrepeatinstances"
>title="Count repeat instances"
>abstract="Specifies whether repeat instances are counted in reports.<br/><br/>Note: this setting does not apply to Flow or Fallout visualizations."

>[!CONTEXTUALHELP]
>id="workspace_project_repeatinstances"
>title="Count repeat instances"
>abstract="Specifies whether repeat instances are counted in reports.<br/>Note: this setting does not apply to Flow or Fallout visualizations."


>[!CONTEXTUALHELP]
>id="workspace_project_commenting"
>title="Allow commenting"
>abstract="When enabled, a comments area is available in the right rail of the project in Analysis Workspace."



**[!UICONTROL Workspace]** > **[!UICONTROL Project]** > **[!UICONTROL Project Info & settings]** provides project-level information on the currently active project.

![Project Info](assets/projectinfo.png)

Settings include:

|  Setting  | Description  |
|---|---|
|  Project Name  | The name given to the project. You can double-click the name to edit it.  |
|  Owner  | Project owner name  |
|  Last Modified  | Date of last modification to the project.  |
|  Tags  |Lists any tags applied to a project for easier categorization.  |
|  Description  | A description is useful for clarifying the purpose of a project. You can double-click the description to edit it.  |
|  Count repeat instances  | Specifies whether repeat instances are counted in reports. For example, this setting (when activated) treats multiple consecutive pages views to the same page as multiple page views. With it off, they count as a single page view (this setting only affects certain metrics, such as Single Page Visits). **Note**: This setting does not apply to Flow or Fallout visualizations.  |
| [Show annotations](/help/analyze/analysis-workspace/components/annotations/overview.md) | Specify whether to show annotations in the project or not. |
|  [Project color palette](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/build-workspace-project/color-palettes)  | You can change the categorical color palette used in Workspace, by choosing from out-of-the-box palettes that have been optimized for color blindness, or by specifying your custom palette. This feature affects many things in Workspace, including most visualizations.  |
| [View Density](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/build-workspace-project/view-density) | Lets you see more data on the screen by reducing the vertical padding of the left rail, freeform tables and cohort tables. |

## Left rail {#left-rail}

Within a project, various icons are available in the left rail, and each represents important tools to build your project:

| Icon | Functionality |
|---|---|
| ![panels icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_WebPage_18_N.svg) | [Panels](/help/analyze/analysis-workspace/c-panels/panels.md) |
| ![visualizations icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_GraphBarVertical_18_N.svg) |[Visualizations](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) |
| ![components icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) | [Components](/help/analyze/analysis-workspace/components/analysis-workspace-components.md) |
| ![data dictionary icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Bookmark_18_N.svg) | [Data dictionary](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) |
| ![toc icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ViewList_18_N.svg) | [Table of contents](/help/analyze/analysis-workspace/build-workspace-project/project-table-of-contents.md) |

Components (dimensions, metrics, segments, date ranges) in the left rail relate to the active panel data view. A blue border identifies the active panel, and the active report suite is listed at the top of the component rail.


## Right-click menu

Here is a video on using the right-click menu in Analysis Workspace:


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Using the context menu](https://video.tv.adobe.com/v/23981?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

## Project canvas {#canvas}

The project canvas is where you bring together panels, tables, visualizations, and components to build your analysis. A project can contain many panels, and each panel can contain many tables and visualizations.

Panels are helpful when you want to organize your projects according to time periods, report suites, or analysis use case. The active panel has a colored border around it, and determines what components are available in the left rail.

Depending on the starting point you chose for your projects, you either have a [freeform table](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/freeform-table) or a [blank panel](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/panels/blank-panel) in the canvas to begin with. The quickest way to start analyzing is to select one or many components and simply drag & drop them into the project canvas. A table of data is rendered automatically for you. [Learn more](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/freeform-table) about the different options for building a table, or leverage the available [training tutorial](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/home) for more guidance on building your first project.

![](assets/canvas.png)

-->
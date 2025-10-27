---
title: Administrar conjuntos de clasificaciones
description: Administrar conjuntos de clasificaciones en Adobe Analytics.
exl-id: b1a6721b-8e5d-4ee6-af6b-cda31c9f8b00
feature: Classifications
source-git-commit: ec49a5fd5771e4ca0a35ead681b556336bbc7031
workflow-type: tm+mt
source-wordcount: '618'
ht-degree: 5%

---

# Administrar conjuntos de clasificación

Puede crear, cambiar el nombre, editar, consolidar, eliminar y etiquetar conjuntos de clasificaciones en la interfaz de administración de conjuntos de clasificaciones. También puede filtrar y buscar conjuntos de clasificaciones específicos.

Para administrar conjuntos de clasificaciones:

1. Seleccione **[!UICONTROL Componentes]** en la barra de menús superior de Adobe Analytics y, a continuación, seleccione **[!UICONTROL Conjuntos de clasificaciones]**.
1. En **[!UICONTROL Conjuntos de clasificaciones]**, seleccione la pestaña **[!UICONTROL Conjuntos de clasificaciones]**.

## Administrador de conjuntos de clasificaciones

El administrador de **[!UICONTROL conjuntos de clasificaciones]** tiene los siguientes elementos de interfaz:

![Administrador de conjuntos de clasificaciones](assets/classification-sets-manage.png)


### Lista de conjuntos de clasificaciones

La lista **[!UICONTROL Conjuntos de clasificaciones]** ➊ muestra todos los conjuntos de clasificaciones. La lista tiene las siguientes columnas:

| Columna | Descripción |
|---|---|
| **[!UICONTROL Conjunto de clasificaciones]** | Nombre del conjunto de clasificaciones. Seleccione el nombre para [editar el conjunto de clasificación](create.md#edit-a-classification-set). |
| **[!UICONTROL Suscripciones]** | El número de suscripciones a las que se aplica el conjunto de clasificaciones. |
| **[!UICONTROL Clasificaciones]** | Número de dimensiones de clasificación que contiene el conjunto de clasificaciones. |
| **[!UICONTROL Automatizado]** | ¿El conjunto de clasificaciones está configurado para importar datos automáticamente desde una ubicación de nube o no? Esta automatización se puede configurar como parte del esquema [conjuntos de clasificación](schema.md). |
| **[!UICONTROL Última modificación]** | La marca de tiempo de la última modificación del conjunto de clasificaciones. |

Para cambiar el tamaño de una columna en la lista de conjuntos de clasificaciones, puede:

* Pase el ratón sobre el separador de columnas y arrástrelo hasta el ancho de columna deseado.
* Seleccione ![ChevronDown](/help/assets/icons/ChevronDown.svg) y seleccione **[!UICONTROL Cambiar tamaño de columna]**. Una línea vertical con el botón de cambio de tamaño le permite cambiar el tamaño de la columna al deseado con.

Para ordenar una columna en la lista de conjuntos de clasificaciones

* Seleccione ![cheurón descendente](/help/assets/icons/ChevronDown.svg) y seleccione **[!UICONTROL Orden ascendente]** o **[!UICONTROL Orden descendente]**. Una flecha (↑↓) indica qué columna y cómo se ordena.

### Botones Buscar y

En el área ➋ de la parte superior de la lista de conjuntos de clasificaciones, puede:

* Busque conjuntos de clasificaciones en ![Search](/help/assets/icons/Search.svg). Los resultados se muestran en la lista de conjuntos de clasificaciones. Seleccione ![CrossSize200](/help/assets/icons/CrossSize200.svg) para borrar la búsqueda.
* Elimine cualquier filtro que se aplique a la lista de conjuntos de clasificaciones. Seleccione ![CrossSize100](/help/assets/icons/CrossSize100.svg) para quitar un filtro.
* Seleccione ![MoreCircle](/help/assets/icons/MoreCircle.svg) para cargar 1000 conjuntos de clasificación adicionales. Inicialmente, la lista de conjuntos de clasificaciones muestra hasta 1000 conjuntos.
* Seleccione ![AgregarCírculo](/help/assets/icons/AddCircle.svg) **[!UICONTROL Nuevo]** para [crear un nuevo conjunto de clasificación](create.md#create-a-classification-set).
* Defina las columnas de la lista de conjuntos de clasificaciones. Seleccione ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) y, en el cuadro de diálogo **[!UICONTROL Personalizar tabla]**, seleccione las columnas que se mostrarán debajo de **[!UICONTROL Seleccionar columnas que se mostrarán]**. Seleccione **[!UICONTROL Aplicar]** para aplicar la configuración de columna.


### Barra de acciones

Al seleccionar uno o más conjuntos de clasificaciones en la lista de conjuntos de clasificaciones, aparece una barra de acciones azul ➌. Las siguientes acciones están disponibles en la barra de acciones:

| Icono | Acción | Descripción |
|---|---|---|
| ![Editar](/help/assets/icons/Edit.svg) | **[!UICONTROL Editar]** | [Edite el conjunto de clasificaciones](create.md#edit-a-classification-set) en el generador de conjuntos de clasificaciones. |
| ![Cambiar el nombre](/help/assets/icons/Rename.svg) | **[!UICONTROL Cambiar el nombre]** | Cambie el nombre de un conjunto de clasificaciones.<br/>En el cuadro de diálogo **[!UICONTROL Cambiar nombre: _conjunto de clasificación_]**, escriba un nombre nuevo y seleccione **[!UICONTROL Cambiar nombre]**. |
| ![Combinar](/help/assets/icons/Merge.svg) | **[!UICONTROL Consolidar]** | [Consolidar conjuntos de clasificaciones](/help/components/classifications/sets/consolidations/manage.md). |
| ![Eliminar](/help/assets/icons/Delete.svg) | **[!UICONTROL Eliminar]** | Eliminar un conjunto de clasificaciones.<br/>El **[!UICONTROL Eliminar _conjunto de clasificación_?Aparecerá el cuadro de diálogo]**. No se puede deshacer la eliminación de un conjunto de clasificaciones. Todos los proyectos programados o consolidaciones que utilicen este conjunto de clasificaciones seguirán utilizando la definición de este conjunto de clasificaciones hasta que vuelva a guardar los proyectos programados o a validar las consolidaciones programadas. Seleccione **[!UICONTROL Eliminar]** para eliminar el conjunto de clasificaciones. |
| ![Etiqueta](/help/assets/icons/Label.svg) | **[!UICONTROL Etiqueta]** | Etiquete el conjunto de clasificaciones.<br/>En el cuadro de diálogo **[!UICONTROL Etiqueta: _conjunto de clasificación_]**, seleccione una o más etiquetas del menú desplegable **[!UICONTROL Etiquetas]**&#x200B;para agregar etiquetas. O introduzca una o más etiquetas nuevas. Use ![CrossSize100](/help/assets/icons/CrossSize100.svg) para quitar una etiqueta. <br/>Seleccione **[!UICONTROL Guardar]**&#x200B;para guardar las etiquetas. |


### Panel Filtro

Seleccione ![Filter](/help/assets/icons/Filter.svg) para mostrar el panel de filtro ➍ que le permite filtrar la lista de conjuntos de clasificaciones. Puede filtrar por:

* **[!UICONTROL Etiquetas]** Seleccione una o varias etiquetas para filtrar la lista de conjuntos de clasificaciones en etiquetas.
* **[!UICONTROL Grupo de informes]**. Seleccione uno o varios grupos de informes para filtrar la lista de conjuntos de clasificaciones en los grupos de informes.

Seleccione ![Filtro](/help/assets/icons/Filter.svg) **[!UICONTROL Ocultar filtros]** para ocultar el panel Filtros.

Tenga en cuenta que los filtros que se muestran en el panel Filtros reflejan las opciones de los conjuntos de clasificaciones que se cargan previamente.


<!-- old content

The Classification set manager allows you to create, edit, or delete classification sets.

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Sets]**

Classification sets consist of **Subscriptions** (report suite and dimension combinations) and **Classification names** (dimensions containing classification data). Subscriptions are configured under [Settings](settings.md), while classification names are configured under [Schema](schema.md).

## Filter classification sets

The left side of the Classification set manager provides filter settings to locate the desired classification set. Clicking the filter icon toggles the filter settings visibility. You can filter classification sets by **[!UICONTROL Tags]** or **[!UICONTROL Report suite]**.

![Classification set filters](../../assets/classification-set-filters.png)

Note that 1,000 classification sets are preloaded at a time. The filters shown in the left rail reflect the options for the sets that are preloaded.

## Classification set manager columns

The following columns are available in the Classification set manager:

* **[!UICONTROL Classification set]**: The classification set name. Clicking a classification set name edits its [settings](settings.md).
* **[!UICONTROL Subscriptions]**: The number of subscriptions that this classification set applies to.
* **[!UICONTROL Classifications]**: The number of classification dimensions that the classification set contains.
* **[!UICONTROL Automated]**: Determines if the classification set is configured to automatically import data from a cloud location. Automation can be configured in the classification set's [schema](schema.md).
* **[!UICONTROL Last Modified]**: The date and time that the classification set was last modified.

## Create or edit options

The following buttons are available in the Classification set manager:

* **[!UICONTROL Add]**: [Create](create.md) a classification set.
* **[!UICONTROL Search by title]**: Search for classification sets by name.
* **[!UICONTROL Load more]**: The Classification set manager initially displays up to 1000 classification sets. This button loads 1000 more classification sets.
* **Show/Hide columns**: Toggle visibility for any column besides [!UICONTROL Classification set].

Select one or more classification sets by clicking the checkbox next to the desired classification set. Selecting a classification set reveals the following options:

* **[!UICONTROL Tag]**: Add one or more tags to the selected classification sets, which allows you to organize or group classification sets to make them easier to locate in the future.
* **[!UICONTROL Delete]**: Deletes the classification set. Classification dimensions based on this classification set are no longer available. Scheduled projects using the deleted classification set continue using dependent dimensions until you resave the scheduled project.
* **[!UICONTROL Consolidate]**: Start a new [consolidation](../consolidations/process.md).
* **[!UICONTROL Rename]**: Rename the selected classification set.

-->
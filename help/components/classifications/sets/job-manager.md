---
title: Administrador de trabajos de clasificación
description: Obtenga información sobre cómo ver los trabajos de clasificación actuales y completados que se generan a partir de conjuntos de clasificaciones.
exl-id: 0470e131-79c6-4906-85f0-530d360ac227
feature: Classifications
source-git-commit: 2ced7cd61c4119347be2ef0fba9b8d60ee6c4df2
workflow-type: tm+mt
source-wordcount: '644'
ht-degree: 2%

---

# Ver y actuar sobre los trabajos de clasificación

El Administrador de trabajos de clasificación muestra los trabajos de clasificación actuales y completados que se generan para los conjuntos de clasificaciones. También puede utilizar el administrador para descargar datos de clasificación o plantillas para un trabajo en particular.

Para ver y actuar sobre los trabajos de clasificación:


1. Seleccione **[!UICONTROL Componentes]** en la barra de menús superior de Adobe Analytics y, a continuación, seleccione **[!UICONTROL Conjuntos de clasificaciones]**.
1. En **[!UICONTROL Conjuntos de clasificaciones]**, seleccione la ficha **[!UICONTROL Trabajos]**.

## Administrador de trabajos de clasificación

El administrador de **[!UICONTROL conjuntos de clasificaciones - trabajos]** tiene los siguientes elementos de interfaz:

![Conjuntos de clasificaciones - Administrador de trabajos](manage/assets/classifications-sets-jobs.png)



### Lista de trabajos de clasificación

La lista **[!UICONTROL Trabajos de clasificación]** ➊ muestra los trabajos de clasificación. La lista tiene las siguientes columnas:

| Columna | Descripción |
|---|---|
| **[!UICONTROL Id. de trabajo]** | El identificador del trabajo de clasificación. |
| **[!UICONTROL Conjunto de clasificaciones]** | El conjunto de clasificaciones asociado con el trabajo de clasificación. |
| **[!UICONTROL Tamaño]** | El tamaño del archivo que se exportó o importó como parte del trabajo de clasificación. |
| **[!UICONTROL Estado]** | El estado del trabajo de clasificación. Los valores posibles son: **[!UICONTROL Created]**, **[!UICONTROL Queued]**, **[!UICONTROL Validated]**, **[!UICONTROL Failed validation]**, **[!UICONTROL Processing]**, **[!UICONTROL Done processing]**, **[!UICONTROL Failed processing]**, **[!UICONTROL Completed]** o **[!UICONTROL Progress]**. Si se muestra, pase el ratón sobre la alerta ![Alerta](/help/assets/icons/Alert.svg) para ver información adicional. |
| **[!UICONTROL Nombre del archivo]** | Identifica el nombre o la funcionalidad utilizados para importar o exportar el archivo como parte del trabajo de clasificación. Entre los posibles valores están: <ul><li>*sin valor*</li><li>El nombre del archivo que se procesa como parte del trabajo de clasificación.</li><li>**[!UICONTROL Exportación de SAINT]**: el trabajo es una exportación desde la [interfaz de clasificaciones heredadas](/help/components/classifications/importer/c-working-with-saint.md).</li><li>**[!UICONTROL exportación para _conjunto de clasificación_ en _marca de tiempo_]**: el trabajo es una descarga desde la interfaz de [esquema](manage/schema.md#download).</li></ul> |
| **[!UICONTROL Tipo de trabajo]** | El tipo de trabajo de clasificación. Los valores posibles son: **[!UICONTROL Importar]** o **[!UICONTROL Exportar]**. |
| **[!UICONTROL Fuente]** | Origen del trabajo de clasificación. Los valores posibles son: **[!UICONTROL API web]**, **[!UICONTROL Carga directa de API]**, **[!UICONTROL Adobe]**, **[!UICONTROL SAINT]** o **[!UICONTROL Desconocido]**. |
| **[!UICONTROL Líneas modificadas]** | El número de líneas modificadas que modificó el trabajo de clasificación. |
| **[!UICONTROL Líneas totales]** | Número total de líneas que ha procesado el trabajo de clasificación. |
| **[!UICONTROL Hora de finalización]** | Hora de finalización del trabajo de clasificación. |
| **[!UICONTROL Descarga de archivos]** | Use ![Descargar](/help/assets/icons/Download.svg) para descargar el archivo (plantilla o datos) asociado con el trabajo de clasificación. |

Para cambiar el tamaño de una columna en la lista de trabajos de clasificación, puede:

* Pase el ratón sobre el separador de columnas y arrástrelo hasta el ancho de columna deseado.
* Seleccione ![ChevronDown](/help/assets/icons/ChevronDown.svg) y seleccione **[!UICONTROL Cambiar tamaño de columna]**. Una línea vertical con el botón de cambio de tamaño le permite cambiar el tamaño de la columna al deseado con.

Para ordenar una columna en la lista de trabajos de clasificación

* Seleccione ![cheurón descendente](/help/assets/icons/ChevronDown.svg) y seleccione **[!UICONTROL Orden ascendente]** o **[!UICONTROL Orden descendente]**. Una flecha (↑↓) indica qué columna y cómo se ordena.


### Botones Buscar y

En el área ➋ de la parte superior de la lista de trabajos de clasificación, puede:

* Busque ![Buscar](/help/assets/icons/Search.svg) trabajos de clasificación. Los resultados se muestran en la lista de trabajos de clasificación. Seleccione ![CrossSize200](/help/assets/icons/CrossSize200.svg) para borrar la búsqueda.
* Elimine cualquier filtro que se aplique a la lista de trabajos de clasificación. Seleccione ![CrossSize100](/help/assets/icons/CrossSize100.svg) para quitar un filtro.
* Seleccione ![MoreCircle](/help/assets/icons/MoreCircle.svg) para cargar otros 1000 trabajos de clasificación. Inicialmente, la lista de conjuntos de clasificaciones muestra hasta 1000 trabajos de clasificación.
* Defina las columnas de la lista de trabajos de conjuntos de clasificaciones. Seleccione ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) y, en el cuadro de diálogo **[!UICONTROL Personalizar tabla]**, seleccione las columnas que se mostrarán debajo de **[!UICONTROL Seleccionar columnas que se mostrarán]**. Seleccione **[!UICONTROL Aplicar]** para aplicar la configuración de columna.



### Panel Filtro

Seleccione ![Filter](/help/assets/icons/Filter.svg) para mostrar el panel de filtro ➌ que le permite filtrar la lista de trabajos de clasificación. Puede filtrar por:

* **[!UICONTROL Conjunto de clasificaciones]**. Seleccione uno o varios conjuntos de clasificaciones para filtrar la lista de trabajos de clasificación.
* **[!UICONTROL Hora de finalización]**. Seleccione uno de los posibles valores para filtrar la lista de trabajos de clasificación en el momento de finalización.
* **[!UICONTROL Estado]**. Seleccione uno de los posibles valores para filtrar la lista de trabajos de clasificación según su estado.
* **[!UICONTROL Tipo de trabajo]**. Seleccione uno de los posibles valores para filtrar la lista de trabajos de clasificación por tipo de trabajo.
* **[!UICONTROL Source]**. Seleccione uno de los posibles valores para filtrar la lista de trabajos de clasificación en el origen.


Seleccione ![Filtro](/help/assets/icons/Filter.svg) **[!UICONTROL Ocultar filtros]** para ocultar el panel Filtros.

Tenga en cuenta que los filtros que se muestran en el panel Filtros reflejan las opciones de los trabajos de clasificación que se cargan previamente.


<!--

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Jobs]**

You cannot create jobs from this interface. Create jobs by uploading data to a classification set (either manually or through a configured external location), requesting a download file, or requesting a template file.

## Filter classification sets

The left side of the Classification set job manager provides filter settings to locate the desired job. Clicking the filter icon toggles the filter settings visibility. You can filter Classification sets by **[!UICONTROL Classification set]**, **[!UICONTROL Completion time]**, **[!UICONTROL Status]**, **[!UICONTROL Job Type]**, or **[!UICONTROL Source]**.

![Classification set job filters](../assets/classification-set-job-filters.png)

Additional filter options are available above the Classification set job manager columns:

* **[!UICONTROL Search by title]**: Search for jobs by filename.
* **[!UICONTROL Load more]**: The Classification set job manager initially displays up to 1000 jobs. If more jobs exist, click this button to load 1000 more jobs.
* **Show/Hide columns**: Toggle visibility for any column besides [!UICONTROL Filename] and [!UICONTROL Completion time].

## Classification set job manager columns

The following columns are available in the Classification set job manager:

* **[!UICONTROL Filename]**: The name of the upload or download file.
* **[!UICONTROL Classification set]**: The name of the Classification set that the file applies to. You can click the Classification set name to reach the Classification set's [Settings](manage/settings.md).
* **[!UICONTROL Size]**: The size of the file.
* **[!UICONTROL Status]**: The status of the job processing the file.
  * **[!UICONTROL Created]**: The job was submitted.
  * **[!UICONTROL Queued]**: The file is ready to be processed, and is waiting for a classification server to process the file.
  * **[!UICONTROL Validated]**: The file is valid and is waiting to be processed.
  * **[!UICONTROL Failed validation]**: The file is formatted incorrectly or otherwise invalid. The file does not go through processing.
  * **[!UICONTROL Processing]**: The file is actively being processed by Adobe.
  * **[!UICONTROL Failed processing]**: The file failed processing.
  * **[!UICONTROL Complete]**: Processing is complete. Classification data is visible in reporting.
  * **[!UICONTROL Failed]**: Generic failure not related to validation or processing.
* **[!UICONTROL Job type]**: The type of job.
* **[!UICONTROL Source]**: The job source.
* **[!UICONTROL File download]**: Only applies to download jobs, such as downloading classification data or downloading templates. When a download is ready, this column provides a download link.
* **[!UICONTROL Modified lines]**: The number of modified lines.
* **[!UICONTROL Completed lines]**: The number of completed lines.
* **[!UICONTROL Completion time]**: The date and time that the job completed (or failed).
-->
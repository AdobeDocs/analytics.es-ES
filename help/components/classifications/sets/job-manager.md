---
title: Administrador de trabajos de clasificación
description: Obtenga información sobre cómo ver los trabajos de clasificación actuales y completados que se generan a partir de conjuntos de clasificaciones.
exl-id: 0470e131-79c6-4906-85f0-530d360ac227
feature: Classifications
TQID: https://experienceleague.adobe.com/KXJHotem9uyppKE-oZ4KsOn1c2BOVDY2jepu6GR3DK4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 644
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

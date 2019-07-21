---
description: Instrucciones sobre cómo eliminar o quitar datos de clasificación.
seo-description: Instrucciones sobre cómo eliminar o quitar datos de clasificación.
seo-title: Eliminar datos de clasificación
solution: Analytics
subtopic: Clasificaciones
title: Eliminar datos de clasificación
topic: Herramientas de administración
uuid: 5 b 1 b 0 ac 7-ee 52-4 fd 8-b 98 e -25283595 cf 0 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Eliminar datos de clasificación

Instrucciones sobre cómo eliminar o quitar datos de clasificación.

1. Click **[!UICONTROL Admin]** &gt; **[!UICONTROL Classification Importer]**.
1. Click **[!UICONTROL Browser Export]**.
1. Seleccione el grupo de informes y el conjunto de datos de los que deben eliminarse los datos de clasificación.
1. Adjust any optional settings to filter specific data you're looking for, then click **[!UICONTROL Export File]**.
1. Once the file has been downloaded, open the file and replace any classification values you wish to delete with [!DNL ~empty~].

   Alternatively, use [!DNL ~deletekey~]. Este comando trata la clasificación como si nunca se hubiera realizado para la clave especificada. Quita por completo la clasificación y todos los datos de columna de las tablas de búsqueda.

   **Advertencia**: Solo necesita una columna que contenga [!DNL ~la clave de eliminación~]. The [!DNL ~empty~] command works at the cell level (key and column combination), so you need [!DNL ~empty~] in the classification column you want to remove. However, [!DNL ~deletekey~] works at the row level (the key and all associated metadata), so it only needs to appear in one of the columns in the row. Este comando quita todos los metadatos de la fila. Adobe interpreta esta acción como si la clave nunca se hubiera clasificado y lo refleja en la categoría [Ninguno](../../../components/c-classifications2/c-classifications-importer/nonclassified-keys.md#concept_233E51DDF3084FF7B7EA89381C73C5FF).

1. Guarde el archivo y cárguelo mediante la ficha [!UICONTROL Importar archivo.]

   After you upload the file, the system recognizes [!DNL ~empty~] as a command to delete that classification value.

   **Propiedades de este comando**

* [!DNL ~empty~] debe estar en minúsculas sin espacios. No son válidas las entradas siguientes:

   * [!DNL ~EMPTY~]
   * [!DNL ~ empty ~]
   * [!DNL ~Empty~]

* No se pueden eliminar los valores de la columna clave. Estos datos se pasan directamente a los informes y son permanentes.
* Si se quita un valor de clasificación que contiene subclasificaciones, estas también se eliminarán. Las clasificaciones no pueden existir sin los valores clave, que constituyen las clasificaciones principales de las subclasificaciones.
* Existe la posibilidad de eliminar los datos de subclasificación sin modificar las clasificaciones principales.


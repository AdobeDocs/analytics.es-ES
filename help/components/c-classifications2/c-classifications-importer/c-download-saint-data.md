---
description: Opcional. Antes de importar las clasificaciones a informes de marketing, existe la posibilidad de descargar una plantilla para facilitar la creación del archivo de datos de clasificación. El archivo de datos utiliza las clasificaciones especificadas como encabezados de columna y, a continuación, organiza el conjunto de datos de informes con los encabezados de clasificación adecuados.
seo-description: Opcional. Antes de importar las clasificaciones a informes de marketing, existe la posibilidad de descargar una plantilla para facilitar la creación del archivo de datos de clasificación. El archivo de datos utiliza las clasificaciones especificadas como encabezados de columna y, a continuación, organiza el conjunto de datos de informes con los encabezados de clasificación adecuados.
seo-title: Plantilla de clasificación
solution: Analytics
subtopic: Clasificaciones
title: Plantilla de clasificación
topic: Herramientas de administración
uuid: 4edd411b-164c-4b4d-a872-b57a3163ca72
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Plantilla de clasificación

Opcional. Antes de importar las clasificaciones a informes de marketing, existe la posibilidad de descargar una plantilla para facilitar la creación del archivo de datos de clasificación. El archivo de datos utiliza las clasificaciones especificadas como encabezados de columna y, a continuación, organiza el conjunto de datos de informes con los encabezados de clasificación adecuados.

## Plantilla de clasificación {#concept_0F06847AD8D042F5BA818AE3C37E2417}

Opcional. Antes de importar las clasificaciones a informes de marketing, existe la posibilidad de descargar una plantilla para facilitar la creación del archivo de datos de clasificación. El archivo de datos utiliza las clasificaciones especificadas como encabezados de columna y, a continuación, organiza el conjunto de datos de informes con los encabezados de clasificación adecuados.

**[!UICONTROL Administración]** &gt; Importador **[!UICONTROL de clasificaciones]**.

| Elemento | Descripción |
|---|---|
| Seleccionar grupo de informes | Seleccione el grupo de informes que se usará en la plantilla. El grupo de informes y el conjunto de datos deben coincidir. |
| Conjunto de datos a clasificar | Seleccione el tipo de datos del archivo de datos. El menú incluye todos los informes de los grupos de informes que se han configurado para las clasificaciones. |
| Exportación numérica 2 | Puede importar al sistema clasificaciones numéricas 2 mediante el importador. Las clasificaciones numéricas 2 son variables útiles que puede cambiar con el tiempo para distintos elementos, tales como los valores de costo y presupuesto del informe [!UICONTROL Canal de mercadotecnia]. Consulte [Clasificaciones numéricas 2](../../../components/c-classifications2/c-numeric-2/c-numeric-2-classifications.md#concept_71024B7B91DF4E909076062AB1380D8B) para obtener información sobre cómo cargar datos a través de clasificaciones numéricas 2. |
| Codificación | Seleccione la codificación de caracteres del archivo de datos. El formato de codificación predeterminado es UTF-8. |
| Descargar | Descarga el archivo de plantilla. |

La plantilla incluye las clasificaciones definidas actualmente (encabezamientos de columna) de un conjunto de datos concreto sin incluir los datos asociados con cada clasificación.

> [!NOTE] El método Plantilla limita la descarga de datos de clasificación a un solo grupo de informes.

Para obtener más información sobre la estructura de archivos de datos, consulte [Acerca de los archivos](../../../components/c-classifications2/c-classifications-importer/c-saint-data-files.md#concept_EBA7669C546040BE8162ADACA3548735)de datos de clasificación.

## Descargar una plantilla de datos de clasificación (opcional) {#task_8DFCF309B6FD43ABB1D6FEE9AFAEC596}

La plantilla proporciona el formato de archivo que debe aplicarse a las clasificaciones.

> [!NOTE] El método Template limita la descarga de datos a un solo grupo de informes.

1. Click **[!UICONTROL Admin]** &gt; **[!UICONTROL Classification Importer]**.
1. On the **[!UICONTROL Download Template]** tab, specify the [data template configuration](../../../components/c-classifications2/c-classifications-importer/c-download-saint-data.md#concept_0F06847AD8D042F5BA818AE3C37E2417).
1. Haga clic en **[!UICONTROL Descargar]**.
1. Guarde el archivo de plantilla en el sistema local.

   The template file is a tab-delimited data file ( [!DNL .tab] filename extension) that most spreadsheet applications support.


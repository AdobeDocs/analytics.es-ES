---
description: (Opcional) Antes de importar las clasificaciones a los informes de marketing, puede descargar una plantilla que le ayudará a crear un archivo de datos de clasificación. El archivo de datos utiliza las clasificaciones especificadas como encabezados de columna y, a continuación, organiza el conjunto de datos de informes con los encabezados de clasificación adecuados.
title: Plantilla de clasificación
feature: Classifications
exl-id: e299509a-0c4f-4ba8-9e91-96356c386054
TQID: https://experienceleague.adobe.com/OR9THCLd93iUl58npPiinO4yAsK8KG3FU8qmBILHioY
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705cid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 355
ht-degree: 63%

---

# Plantilla de clasificación (heredada)

{{classification-importer-deprecation}}

Opcional. Antes de importar las clasificaciones a informes y proyectos, existe la posibilidad de descargar una plantilla para facilitar la creación del archivo de datos de clasificación. El archivo de datos utiliza las clasificaciones especificadas como encabezados de columna y, a continuación, organiza el conjunto de datos de informes con los encabezados de clasificación adecuados.

## Plantilla de clasificación {#concept_0F06847AD8D042F5BA818AE3C37E2417}

(Opcional) Antes de importar las clasificaciones a los informes de marketing, puede descargar una plantilla que le ayudará a crear un archivo de datos de clasificación. El archivo de datos utiliza las clasificaciones especificadas como encabezados de columna y, a continuación, organiza el conjunto de datos de informes con los encabezados de clasificación adecuados.

**[!UICONTROL Administración]** > **[!UICONTROL Importador de clasificaciones]**.

| Elemento | Descripción |
| --- | ---|
| Seleccionar grupo de informes | Seleccione el grupo de informes que se utilizará en la plantilla. El grupo de informes y el conjunto de datos deben coincidir. |
| Conjunto de datos a clasificar | Seleccione el tipo de datos del archivo de datos. El menú incluye todos los informes de los grupos de informes que se han configurado para las clasificaciones. |
| Exportación numérica 2 | **Importante**: Esta opción no está disponible para los grupos de informes habilitados para la nueva arquitectura de clasificación. |
| Codificación | Seleccione la codificación de caracteres del archivo de datos. El formato de codificación predeterminado es UTF-8.<br>**Importante**: Esta opción no está disponible para los grupos de informes habilitados para la nueva arquitectura de clasificación. |
| Descargar | Descarga el archivo de plantilla. |

La plantilla incluye las clasificaciones definidas actualmente (encabezados de columna) de un conjunto de datos específico sin incluir los datos asociados a cada clasificación.

>[!NOTE]
>
>El método de la plantilla limita la descarga de datos de clasificación a un solo grupo de informes.

Para obtener más información sobre la estructura de archivos de datos, consulte [Acerca de los archivosde datos de clasificación](/help/components/classifications/importer/c-saint-data-files.md).

## Descargar una plantilla de datos de clasificación (opcional) {#task_8DFCF309B6FD43ABB1D6FEE9AFAEC596}

La plantilla proporciona el formato de archivo que debe aplicarse a las clasificaciones.

>[!NOTE]
>
>El método de la plantilla limita su descarga de datos a un único grupo de informes.

1. Haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Importador de clasificaciones]**.
1. En la pestaña **[!UICONTROL Descargar plantilla]**, especifique la [configuración de la plantilla de datos](/help/components/classifications/importer/c-download-saint-data.md).
1. Haga clic en **[!UICONTROL Descargar]**.
1. Guarde el archivo de plantilla en el sistema local.

   El archivo de plantilla es un archivo de datos delimitado por tabuladores (con la extensión de nombre de archivo [!DNL .tab]) compatible con la mayoría de las aplicaciones de hojas de cálculo.

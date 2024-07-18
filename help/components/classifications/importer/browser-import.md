---
description: Los datos de clasificación pueden importarse (cargarse) a través del explorador web. Este método restringe la carga de datos de clasificación a un solo grupo de informes.
title: Importación del explorador
feature: Classifications
exl-id: 5bef1f6d-9b27-464d-8343-472f300a7437
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 100%

---

# Importación del explorador

Los datos de clasificación pueden importarse (cargarse) a través del explorador web. Este método restringe la carga de datos de clasificación a un solo grupo de informes.

## Importación del explorador {#concept_314FB3D5FD5A439B9CFEDE37A3337BA7}

Los datos de clasificación pueden importarse (cargarse) a través del explorador web. Este método restringe la carga de datos de clasificación a un solo grupo de informes.

**[!UICONTROL Administración]** > **[!UICONTROL Importador de clasificaciones]**

## Importación del explorador de clasificaciones: descripciones de los campos {#section_F628C47081DA4026A4D30E3D3454B1DA}

| Elemento | Descripción |
| --- | --- |
| Seleccionar grupo de informes | El grupo de informes donde deben importarse los datos de las clasificaciones. El archivo de datos de importación debe coincidir con el formato del conjunto de datos del grupo de informes. |
| Conjunto de datos a clasificar | El conjunto de datos que debe recibir las clasificaciones. La lista desplegable incluye todos los informes de los conjuntos de informes que se han configurado para las clasificaciones. |
| Seleccionar un archivo para importar | Permite explorar para buscar el archivo de datos de importación que debe cargarse.  Nota: El límite de tamaño del archivo de carga es de 1 MB. |
| Sobrescribir datos sobre conflictos | Sobrescribe automáticamente los datos existentes que entran en conflicto con los datos importados.<br>**Importante**: Esta opción no está disponible para los grupos de informes habilitados para la nueva arquitectura de clasificación. |
| Descargar automáticamente el archivo de clasificaciones una vez completada la importación | Descarga automáticamente un archivo delimitado por tabuladores que representa el conjunto de datos con los datos de las clasificaciones que se acaban de cargar. Adobe genera automáticamente este archivo si la importación crea algún ID único o si se produce algún error.<br>**Importante**: Esta opción no está disponible para los grupos de informes habilitados para la nueva arquitectura de clasificación. |


## Importar clasificaciones a través del explorador {#task_D7D51CB6FB35437AB68599B1B23FEAC1}

1. Haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Importador de clasificaciones]**.
1. Haga clic en **[!UICONTROL Importar archivo]**.
1. Configure los campos **[!UICONTROL Importación del explorador]**.
1. Haga clic en **[!UICONTROL Importar archivo]**.
1. Observe la ventana de estado para ver los mensajes de procesamiento.
1. (Condicional) Si activó **[!UICONTROL Descargar automáticamente el archivo de clasificación cuando se haya completado la carga]**, indique dónde desea almacenar el archivo resultante cuando termine el procesamiento. Tenga en cuenta que esta opción no está disponible para los grupos de informes habilitados para la nueva arquitectura de clasificación.

>Si la importación es correcta, se muestran inmediatamente los cambios correspondientes en una exportación. Pese a ello, los cambios de datos en los informes pueden tardar hasta cuatro horas si utiliza una importación mediante explorador y hasta 24 horas si utiliza una importación mediante FTP.

---
title: Administración de fuentes de datos
description: Vaya a la interfaz de administración de fuentes de datos.
exl-id: 315501fb-26e1-436a-938d-5957ca037cd0
feature: Data Sources
role: Admin
source-git-commit: 27bcbd638848650c842ad8d8aaa7ab59e27e900e
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 7%

---

# Administración de fuentes de datos

Utilice el administrador de fuente de datos para crear, editar o desactivar fuentes de datos. También puede utilizar esta interfaz para realizar un seguimiento del estado de los archivos cargados en las ubicaciones FTP de las fuentes de datos.

**[!UICONTROL Administrador]** > **[!UICONTROL Todos los administradores]** > **[!UICONTROL Fuentes de datos]**

Utilice el selector de grupos de informes en la parte superior derecha para cambiar entre grupos de informes de su organización.

Hay tres fichas principales en esta interfaz; **[!UICONTROL Administrar]**, **[!UICONTROL Crear]** y **[!UICONTROL Registro de archivos]**.

## Administrar

La pestaña **[!UICONTROL Administrar]** administra todas las fuentes de datos que su organización ha creado. Puede ver información de FTP, realizar modificaciones en las variables utilizadas en los archivos de plantilla o desactivar por completo las fuentes de datos.

![Administrar](assets/manage.png)

El origen de datos superior siempre es [!UICONTROL Web Beacon]. Esta fuente de datos es lo que se usa para la recopilación de datos típica mediante el AppMeasurement. No se puede editar ni desactivar.

Cada fuente de datos tiene las siguientes opciones:

* **[!UICONTROL Reiniciar procesamiento]**: reinicia el procesamiento de la fuente de datos cuando antes se detuvo debido a errores. El procesamiento continúa hasta que se encuentre el siguiente error. El procesamiento de un archivo de fuente de datos solamente se detiene si selecciona **[!UICONTROL Detener procesamiento si hay errores]**.
* **[!UICONTROL Procesamiento completo]**: ya no se usa. Este botón se usó solamente para [Procesamiento completo de fuentes de datos](full-processing-eol.md).
* **[!UICONTROL Detener procesamiento si hay errores]**: Casilla de verificación que indica al servidor de procesamiento que se detenga cuando encuentre un error. El procesamiento del origen de datos no se reanudará hasta que seleccione **[!UICONTROL Reiniciar procesamiento]**. Cuando una fuente de datos encuentra un error de archivo, se lo notifica. El Adobe mueve el archivo con el error a una carpeta llamada `files_with_errors` en el servidor FTP. Una vez resuelto el problema, vuelva a enviar el archivo para su procesamiento.
* **[!UICONTROL Configurar]**: vínculo que lo lleva a través del asistente para la creación de orígenes de datos para este origen de datos. Este asistente le permite cambiar el nombre del origen de datos o volver a configurar las variables incluidas automáticamente al descargar un archivo de plantilla.
* **[!UICONTROL Información de FTP]**: vínculo que le lleva al último paso del asistente para la creación de orígenes de datos donde se muestran las credenciales de FTP.

Una vez que una fuente de datos recibe los datos, se muestra una tabla que contiene varias columnas para los archivos cargados.

* **[!UICONTROL Archivos en cola de procesamiento]**: Nombre del archivo.
* **[!UICONTROL Filas]**: El número total de filas del archivo.
* **[!UICONTROL Errores]**: El número de filas que contenían errores y no se pudieron ingerir.
* **[!UICONTROL Advertencias]**: El número de filas que contenían advertencias.
* **[!UICONTROL Recibido]**: La marca de tiempo en la que se recibió el archivo en la zona horaria del grupo de informes.
* **[!UICONTROL Estado]**: El estado del archivo (`Success` o `Failed`).

## Crear

La pestaña **[!UICONTROL Create]** le proporciona un punto de partida para el asistente de creación de fuentes de datos.

![Crear](assets/create.png)

La categoría y el tipo de fuente de datos eran más valiosos en versiones anteriores de Adobe Analytics. Sin embargo, su uso sigue siendo limitado:

* El tipo de fuente de datos se muestra en la ficha [Administrar](#manage) para la propia fuente de datos y en la ficha [Registro de archivos](#file-log) para cada archivo individual.
* Algunos tipos de fuentes de datos incluyen automáticamente variables al descargar el archivo de plantilla. Sin embargo, puede incluir cualquier dimensión o métrica disponible siempre que se adhiera al [formato de archivo](file-format.md) establecido.

Más allá de estos motivos, todas las categorías y tipos de fuentes de datos que se pueden elegir son idénticos. Elija la categoría y el tipo que mejor represente su propósito para utilizar fuentes de datos.

Si se retiran [orígenes de datos de procesamiento completo](full-processing-eol.md), no se podrán seleccionar varias categorías y tipos. Si selecciona un tipo de origen de datos de procesamiento completo, el botón **[!UICONTROL Activar]** aparecerá atenuado.

## Registro de archivos

La ficha **[!UICONTROL Registro de archivos]** le proporciona una vista agregada de todos los archivos de fuente de datos cargados para el grupo de informes dado.

![Registro de archivos](assets/file-log.png)

Hay disponible una barra de búsqueda que le ayuda a localizar una fuente de datos específica. La tabla muestra las siguientes columnas:

* **[!UICONTROL Nombre de Data Source]**: El nombre del origen de datos.
* **[!UICONTROL Tipo]**: tipo de origen de datos.
* **[!UICONTROL Nombre de archivo]**: Nombre del archivo que se cargó.
* **[!UICONTROL Filas]**: El número total de filas del archivo.
* **[!UICONTROL Errores]**: El número de filas que contenían errores.
* **[!UICONTROL Advertencias]**: ya no se usa. El número de filas que contenían advertencias.
* **[!UICONTROL Recibido]**: La fecha y hora en que el Adobe comenzó a procesar el archivo.
* **[!UICONTROL Estado]**: El estado del archivo (`Success` o `Failed`).

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

Hay tres pestañas principales en esta interfaz; **[!UICONTROL Administrar]**, **[!UICONTROL Crear]**, y **[!UICONTROL Registro de archivos]**.

## Administrar

El **[!UICONTROL Administrar]** controla todas las fuentes de datos que ha creado su organización. Puede ver información de FTP, realizar modificaciones en las variables utilizadas en los archivos de plantilla o desactivar por completo las fuentes de datos.

![Administrar](assets/manage.png)

La fuente de datos superior siempre es [!UICONTROL Baliza web]. Esta fuente de datos es lo que se usa para la recopilación de datos típica mediante el AppMeasurement. No se puede editar ni desactivar.

Cada fuente de datos tiene las siguientes opciones:

* **[!UICONTROL Reiniciar procesamiento]**: reinicia el procesamiento de la fuente de datos cuando anteriormente se detuvo debido a errores. El procesamiento continúa hasta que se encuentre el siguiente error. El procesamiento de un archivo de fuente de datos solo se detiene si se selecciona **[!UICONTROL Detener procesamiento si hay errores]**.
* **[!UICONTROL Completar procesamiento]**: ya no se utiliza: este botón solo se utilizaba para [Fuentes de datos de procesamiento completo](full-processing-eol.md).
* **[!UICONTROL Detener procesamiento si hay errores]**: Casilla de verificación que indica al servidor de procesamiento que se detenga cuando encuentre un error. El procesamiento de la fuente de datos no se reanudará hasta que se seleccione **[!UICONTROL Reiniciar procesamiento]**. Cuando una fuente de datos encuentra un error de archivo, se lo notifica. El Adobe mueve el archivo con el error a una carpeta llamada `files_with_errors` en el servidor FTP. Una vez resuelto el problema, vuelva a enviar el archivo para su procesamiento.
* **[!UICONTROL Configurar]**: vínculo que le guía a través del Asistente para la creación de fuentes de datos para esta fuente de datos. Este asistente le permite cambiar el nombre del origen de datos o volver a configurar las variables incluidas automáticamente al descargar un archivo de plantilla.
* **[!UICONTROL Información de FTP]**: Un vínculo que le lleva al último paso del asistente para la creación de fuentes de datos, en el que se muestran las credenciales de FTP.

Una vez que una fuente de datos recibe los datos, se muestra una tabla que contiene varias columnas para los archivos cargados.

* **[!UICONTROL Archivos En Cola De Procesamiento]**: nombre del archivo.
* **[!UICONTROL Filas]**: El número total de filas del archivo.
* **[!UICONTROL Errores]**: el número de filas que contenían errores y que no se pudieron ingerir.
* **[!UICONTROL Advertencias]**: el número de filas que contenían advertencias.
* **[!UICONTROL Recibido]**: La marca de tiempo de recepción del archivo en el huso horario del grupo de informes.
* **[!UICONTROL Estado]**: el estado del archivo (`Success` o `Failed`).

## Crear

El **[!UICONTROL Crear]** proporciona un punto de partida para el asistente de creación de fuentes de datos.

![Crear](assets/create.png)

La categoría y el tipo de fuente de datos eran más valiosos en versiones anteriores de Adobe Analytics. Sin embargo, su uso sigue siendo limitado:

* El tipo de fuente de datos se muestra en la [Administrar](#manage) para el propio origen de datos y la variable [Registro de archivos](#file-log) para cada archivo individual.
* Algunos tipos de fuentes de datos incluyen automáticamente variables al descargar el archivo de plantilla. Sin embargo, puede incluir cualquier dimensión o métrica disponible siempre que se adhiera a la variable establecida [Formato de archivo](file-format.md).

Más allá de estos motivos, todas las categorías y tipos de fuentes de datos que se pueden elegir son idénticos. Elija la categoría y el tipo que mejor represente su propósito para utilizar fuentes de datos.

Con la retirada de [Fuentes de datos de procesamiento completo](full-processing-eol.md)No obstante, no se pueden seleccionar varias categorías y tipos. Si selecciona un tipo de fuente de datos de procesamiento completo, la variable **[!UICONTROL Activar]** El botón aparece atenuado.

## Registro de archivos

El **[!UICONTROL Registro de archivos]** le ofrece una vista acumulada de todos los archivos de fuente de datos cargados para el grupo de informes dado.

![Registro de archivos](assets/file-log.png)

Hay disponible una barra de búsqueda que le ayuda a localizar una fuente de datos específica. La tabla muestra las siguientes columnas:

* **[!UICONTROL Nombre de fuente de datos]**: nombre de la fuente de datos.
* **[!UICONTROL Tipo]**: tipo de fuente de datos.
* **[!UICONTROL Nombre de archivo]**: Nombre del archivo que se ha cargado.
* **[!UICONTROL Filas]**: El número total de filas del archivo.
* **[!UICONTROL Errores]**: El número de filas que contenían errores.
* **[!UICONTROL Advertencias]**: ya no se utiliza. El número de filas que contenían advertencias.
* **[!UICONTROL Recibido]**: la fecha y la hora en que el Adobe comenzó a procesar el archivo.
* **[!UICONTROL Estado]**: el estado del archivo (`Success` o `Failed`).

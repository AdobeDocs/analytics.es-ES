---
title: Esquema del conjunto de clasificaciones
description: Ver y editar el esquema de un conjunto de clasificaciones individual.
source-git-commit: d0e3b28590b24d630a192ee857a7d84c115dc8c1
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 46%

---

# Esquema

Ver las dimensiones de clasificación configuradas actualmente para este conjunto de clasificaciones.

**[!UICONTROL Componentes]** > **[!UICONTROL Conjuntos de clasificaciones]** > **[!UICONTROL Conjuntos]** > Haga clic en el nombre del conjunto de clasificaciones deseado > **[!UICONTROL Esquema]**

Están disponibles los siguientes botones:

<!--* **[!UICONTROL Add]**: Adds an empty row so that you can add a classification dimension to the schema.-->
* **[!UICONTROL Cargar]**: Cargue manualmente los datos de clasificación de una o varias dimensiones de clasificación. `JSON`, `CSV`, `TSV`, y `TAB` son compatibles. Al cargar un archivo válido, se muestra una previsualización de tabla de los datos que se van a clasificar.
   * **[!UICONTROL Codificación de archivos]**: Seleccione la codificación de archivo correcta mediante esta lista desplegable. Las opciones válidas incluyen [!UICONTROL UTF-8] y [!UICONTROL Latin1].
   * **[!UICONTROL Delimitador de lista]**: Seleccione el delimitador de lista correcto. Si utiliza un archivo de plantilla o archivo descargado, asegúrese de que el [!UICONTROL Delimitador de lista] aquí coincide el [!UICONTROL Delimitador de lista] cuando se descargó el archivo.
   * **[!UICONTROL Aplicar]**: guarde los datos de clasificación cargados en el conjunto de clasificaciones.

  ![Carga del conjunto de clasificaciones](../../assets/classification-set-upload.png)

* **[!UICONTROL Descargar]**: Descargue los valores clave y sus columnas de clasificación.
   * **[!UICONTROL Filas]**: Número máximo de filas que se incluirán en el archivo de descarga.
   * **[!UICONTROL Descargar filas recibidas entre]**: Selector de fecha de calendario que le permite filtrar valores clave por el momento en que aparecen en los informes. Si un valor clave no se recopiló en este intervalo de fechas, no aparece en el archivo descargado.
   * **[!UICONTROL Datos devueltos]**: Una lista desplegable que permite filtrar los valores clave incluidos en el archivo descargado en función de los datos de clasificación asociados.
      * **[!UICONTROL Todos los valores clasificados]**: Incluye filas donde los datos de clasificación se incluyen en al menos una columna.
      * **[!UICONTROL Todos los valores no clasificados]**: Incluye filas en las que faltan datos de clasificación en al menos una columna.
   * **[!UICONTROL Formato de archivo]**: Una lista desplegable que determina el formato de archivo en el que se encuentra el archivo de descarga. Las opciones incluyen [!UICONTROL JSON], [!UICONTROL Valores separados por comas] y [!UICONTROL Valores separados por tabulaciones de Excel].
   * **[!UICONTROL Codificación de archivos]**: una lista desplegable que determina la codificación del archivo. Las opciones incluyen [!UICONTROL UTF-8] y [!UICONTROL Latin1]. Se recomienda UTF-8.

  ![Descarga del conjunto de clasificaciones](../../assets/classification-set-download.png)

* **[!UICONTROL Plantilla]**: Descargue un archivo de plantilla. Este archivo es similar al botón de [!UICONTROL Descargar], excepto que no contiene datos de clasificación ni valores de clave.
   * **[!UICONTROL Formato de archivo]**: una lista desplegable que determina el formato de archivo en el que se encuentra el archivo de plantilla. Las opciones incluyen [!UICONTROL Valores separados por comas] y [!UICONTROL Valores separados por tabulaciones de Excel].
   * **[!UICONTROL Codificación de archivos]**: una lista desplegable que determina la codificación del archivo. Las opciones incluyen [!UICONTROL UTF-8] y [!UICONTROL Latin1]. Se recomienda UTF-8.
   * **[!UICONTROL Delimitadores de lista]**: una lista desplegable que determina el delimitador de lista que separa las columnas de clasificación de cada fila.

  ![Plantilla del conjunto de clasificaciones](../../assets/classification-set-template.png)

* **[!UICONTROL Historial de trabajos]**: Un vínculo de acceso directo que le lleva a la variable [Gestor de trabajo](../job-manager.md), mostrando trabajos solo para este conjunto de clasificaciones.
* **[!UICONTROL Automatizar]**: Introduzca automáticamente datos de ubicaciones de almacenamiento externas.
   * **[!UICONTROL Cuenta de ubicación]**: una lista desplegable que muestra las cuentas de ubicación existentes que su organización ha configurado. Hay un botón disponible para crear una cuenta de ubicación.
   * **[!UICONTROL Ubicación]**: una lista desplegable que muestra las ubicaciones existentes que su organización ha configurado. Hay un botón disponible para crear una ubicación.
   * **[!UICONTROL Delimitador]**: El delimitador de columna para los archivos cargados. Las opciones incluyen [!UICONTROL Coma], [!UICONTROL Punto y coma], [!UICONTROL Dos puntos], [!UICONTROL Barra vertical], [!UICONTROL Espacio], [!UICONTROL Barra oblicua], [!UICONTROL Barra invertida], [!UICONTROL Guión], o [!UICONTROL Subrayado].
   * **[!UICONTROL Codificación]**: una lista desplegable que determina la codificación del archivo. Las opciones incluyen [!UICONTROL UTF-8] y [!UICONTROL Latin1]. Se recomienda UTF-8.

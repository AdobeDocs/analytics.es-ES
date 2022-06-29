---
title: Configuración del conjunto de clasificaciones
description: Cree o edite un conjunto de clasificaciones.
exl-id: abf00508-5dde-4669-bf94-5eb4754888cc
source-git-commit: 3b0e2bbe531692f26ed118b1d2adc0b5ed28a9bf
workflow-type: tm+mt
source-wordcount: '594'
ht-degree: 0%

---

# Configuración del conjunto de clasificaciones

Configure un conjunto de clasificaciones, cargue datos o descargue datos.

>[!NOTE]
>
>Esta función se encuentra actualmente en una versión limitada. Si desea acceder a esta función, póngase en contacto con el servicio de atención al cliente de Adobe o con el administrador de cuentas, que podrán reenviar la solicitud al equipo de clasificaciones para que la solicite.

**[!UICONTROL Componentes]** > **[!UICONTROL Conjuntos de clasificaciones]** > **[!UICONTROL Conjuntos]** > Haga clic en el nombre del conjunto de clasificaciones que desee

Al editar un conjunto de clasificaciones, hay dos fichas disponibles; **[!UICONTROL Esquema]** y **[!UICONTROL Configuración]**.

## Configuración 

Los campos siguientes están disponibles en la [!UICONTROL Configuración] y se puede editar:

* **[!UICONTROL Nombre]**: El nombre del conjunto de clasificaciones.
* **[!UICONTROL Descripción]**: Descripción del conjunto de clasificaciones.
* **[!UICONTROL Nombre del propietario]**: El nombre del propietario.
* **[!UICONTROL Correo electrónico del propietario]**: La dirección de correo electrónico del propietario.
* **[!UICONTROL Notificar problemas]**: Lista de direcciones de correo electrónico delimitada por comas a las que se notifican los problemas con este conjunto de clasificaciones.
* **[!UICONTROL Etiquetas]**: Agregue una o más etiquetas a los conjuntos de clasificaciones seleccionados, lo que le permite organizar o agrupar conjuntos de clasificaciones para que sean más fáciles de localizar en el futuro.

Los campos adicionales están disponibles con fines informativos y no se pueden editar:

* **[!UICONTROL Tipo]**: El tipo de clasificación entre [!UICONTROL Principal] y [!UICONTROL Búsqueda]. Las clasificaciones principales generalmente se utilizan.
* **[!UICONTROL Suscripciones]**: Grupo de informes y variable a los que se aplica el conjunto de clasificaciones. Actualmente solo se admite un grupo de informes para un conjunto de clasificaciones determinado; se ha planificado la compatibilidad con varios grupos de informes.

## Esquema

Ver las dimensiones de clasificación configuradas actualmente para esta suscripción. Los botones disponibles son los siguientes:

* **[!UICONTROL Cargar]**: Cargue manualmente los datos de clasificación de una o varias dimensiones de clasificación. Los archivos JSON, CSV, TSV y TAB son compatibles. Al cargar un archivo válido, se muestra una vista previa de tabla de los datos que se van a clasificar.
   * **[!UICONTROL Codificación de archivos]**: Seleccione la codificación de archivo correcta mediante este menú desplegable. Las opciones válidas incluyen [!UICONTROL UTF-8] y [!UICONTROL Latin1].
   * **[!UICONTROL Delimitador de lista]**: Seleccione el delimitador de lista correcto. Si utiliza un archivo de plantilla o archivo descargado, asegúrese de que la variable [!UICONTROL Delimitador de lista] aquí coincide la variable [!UICONTROL Delimitador de lista] cuando se descargó el archivo.
   * **[!UICONTROL Aplicar]**: Guarde los datos de clasificación cargados en el conjunto de clasificaciones.

   ![Carga del conjunto de clasificaciones](../assets/classification-set-upload.png)

* **[!UICONTROL Descargar]**: Descargue los valores clave y sus columnas de clasificación.
   * **[!UICONTROL Filas]**: Número máximo de filas que se incluirán en el archivo de descarga.
   * **[!UICONTROL Descargar filas recibidas entre]**: Selector de fecha de calendario que le permite filtrar valores clave por el momento en que aparecen en los informes. Si un valor clave no se recopiló en este intervalo de fechas, no aparece en el archivo descargado.
   * **[!UICONTROL Datos devueltos]**: Un menú desplegable que permite filtrar los valores clave incluidos en el archivo descargado en función de los datos de clasificación asociados.
      * **[!UICONTROL Todos los valores clasificados]**: Incluye filas donde los datos de clasificación se incluyen en al menos una columna.
      * **[!UICONTROL Todos los valores no clasificados]**: Incluye filas en las que faltan datos de clasificación en al menos una columna.
   * **[!UICONTROL Formato del archivo]**: Menú desplegable que determina el formato de archivo en el que se encuentra el archivo de descarga. Las opciones incluyen [!UICONTROL JSON], [!UICONTROL Valores separados por comas]y [!UICONTROL Valores separados por tabulaciones de Excel].
   * **[!UICONTROL Codificación de archivos]**: Menú desplegable que determina la codificación del archivo. Las opciones incluyen [!UICONTROL UTF-8] y [!UICONTROL Latin1]. Se recomienda UTF-8.
   * **[!UICONTROL Delimitadores de lista]**: Menú desplegable que determina el delimitador de lista que separa las columnas de clasificación de cada fila.

   ![Descarga de conjunto de clasificaciones](../assets/classification-set-download.png)

* **[!UICONTROL Plantilla]**: Descargue un archivo de plantilla. Este archivo es similar al de [!UICONTROL Descargar] , excepto que no contiene datos de clasificación ni valores de clave.
   * **[!UICONTROL Formato del archivo]**: Menú desplegable que determina el formato de archivo en el que se encuentra el archivo de plantilla. Las opciones incluyen [!UICONTROL Valores separados por comas]y [!UICONTROL Valores separados por tabulaciones de Excel].
   * **[!UICONTROL Codificación de archivos]**: Menú desplegable que determina la codificación del archivo. Las opciones incluyen [!UICONTROL UTF-8] y [!UICONTROL Latin1]. Se recomienda UTF-8.
   * **[!UICONTROL Delimitadores de lista]**: Menú desplegable que determina el delimitador de lista que separa las columnas de clasificación de cada fila.
* **[!UICONTROL Historial de trabajos]**: Un vínculo de acceso directo que le lleva al [Gestor de trabajos](job-manager.md), mostrando los trabajos solo para este conjunto de clasificaciones.

   ![Plantilla de conjunto de clasificaciones](../assets/classification-set-template.png)

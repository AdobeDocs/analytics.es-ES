---
title: Tiempo de procesamiento del importador de clasificaciones
description: Comprenda el Adobe de intervalo de tiempo que procesa los archivos de clasificación y cómo minimizar el tiempo de procesamiento.
translation-type: tm+mt
source-git-commit: 0870ace3fea8e3ef650d2de2960006a0d655cf9f
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 0%

---


# Tiempo de procesamiento del importador de clasificaciones

El tiempo de procesamiento de un archivo de clasificación varía según el tamaño del archivo y la cantidad total de archivos que procesan los Adobes. Las clasificaciones no suelen tardar más de 72 horas. Sin embargo, los períodos de uso intensivo de las clasificaciones en las organizaciones que utilizan Adobe Analytics pueden hacer que los archivos tarden más de 72 horas. El Adobe ve un uso de clasificación muy importante en los meses previos a la temporada de fiestas.

Si desea ver si un archivo de clasificación ha finalizado, haga lo siguiente:

1. Inicie sesión en Adobe Analytics y, a continuación, vaya a **[!UICONTROL Administración]** > **[!UICONTROL Importador]** de clasificaciones.
2. Seleccione el grupo de informes y el conjunto de datos en cuestión.
3. Si el procesamiento aún no se ha completado, aparecerá uno de los siguientes mensajes:

   * ![Aviso](assets/icon_notice_notice.gif) El informe seleccionado tiene una importación de clasificación que se está procesando.
   * ![Aviso](assets/icon_notice_notice.gif) El informe seleccionado tiene datos de clasificación que aún no se han propagado a todos los servidores.

Si desea minimizar el tiempo de importación de la clasificación, Adobe recomienda cumplir las siguientes directrices:

* **Utilice el generador de reglas de clasificación cuando sea posible**: El creador de reglas de clasificación procesa los datos de forma diferente que el importador de clasificaciones tradicional. Si los datos de clasificación siguen patrones específicos, se recomienda utilizar esta capacidad.
* **Cargar solo las filas** cambiadas: Esta práctica reduce en gran medida la cantidad de tiempo que se tarda en procesar los archivos de clasificación, ya que no se ordenan mediante filas sin modificar. Adobe recomienda encarecidamente cargar solo las filas cambiadas.
* **Planee con anticipación**: Inicio cargando datos de clasificación lo antes posible, especialmente si estos datos se utilizan durante la temporada de fiestas.
* **Combinar archivos de clasificación siempre que sea posible**: Si una sola variable tiene varias clasificaciones, cargue un solo archivo con todas las clasificaciones aplicables. Evite cargar varias clasificaciones para la misma variable.
* **Evite cargar archivos de más de 500 MB**: Si se trata de grandes cantidades de datos de clasificación, Adobe recomienda dividir los archivos en archivos de 100 MB a 500 MB.
* **Evite cargar grandes cantidades de archivos en FTP**: Si planea cargar los mismos archivos en muchos grupos de informes a través de FTP, limite el número de archivos cargados a la vez. Adobe recomienda que el número de archivos multiplicado por el número de grupos de informes aplicables sea inferior a 1000. Si se requiere cargar 100 archivos en 100 grupos de informes, el número total de archivos es de 10.000. En lugar de cargar los 100 archivos a la vez, divida en 10 grupos de 10 archivos a la vez.
* **Cargue archivos pequeños mediante el importador** del explorador: Si tiene un archivo de menos de 1 MB (menos de 50.000 filas), Adobe recomienda utilizar el importador del explorador. Las importaciones de exploradores son casi siempre más rápidas que las importaciones de FTP.

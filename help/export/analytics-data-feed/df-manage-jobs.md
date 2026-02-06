---
title: Administrar trabajos de fuentes de datos
description: Obtenga información sobre cómo administrar trabajos individuales en fuentes de datos. Navegue por la interfaz, utilice filtros y búsquedas, y busque definiciones de columnas.
feature: Data Feeds
exl-id: b17e333e-290f-42e4-b304-1e34282237a7
source-git-commit: 728e807764901ad2bd6834339e5e75348dd5a988
workflow-type: tm+mt
source-wordcount: '822'
ht-degree: 30%

---

# Administración de trabajos de fuentes de datos

Los trabajos son tareas individuales que generan un archivo comprimido. Se crean y se rigen por fuentes.

Para administrar los trabajos de fuentes de datos:

1. Inicie sesión en [experiencecloud.adobe.com](https://experiencecloud.adobe.com) con sus credenciales de Adobe ID.

1. Seleccione el icono de 9 cuadrados en la esquina superior derecha, luego seleccione [!UICONTROL **Analytics**].

1. En la barra de navegación superior, vaya a [!UICONTROL **Administrador**] > [!UICONTROL **Fuentes de datos**].

   Se muestran las fuentes de datos de todos los grupos de informes a los que tiene acceso. O bien, si no se han configurado fuentes, la página mostrará el botón [!UICONTROL Crear nueva fuente de datos].

   ![Administrador de fuentes de datos](assets/data-feed-manager.png)

1. (Opcional) Seleccione la casilla de verificación situada junto a la fuente de datos que contiene los trabajos que desea ver y, a continuación, seleccione [!UICONTROL **Historial de trabajos**].

   Para obtener más información, consulte [Ver el historial de trabajos de una fuente de datos](#view-job-history-for-a-data-feed).

## Filtrar y buscar

Puede filtrar y buscar para localizar el trabajo exacto que está buscando.

En el extremo izquierdo, haga clic en el icono de filtro para mostrar u ocultar las opciones de filtrado. Los filtros están organizados por categoría. Haga clic en el botón de contenido adicional para contraer o expandir las categorías de filtrado. Haga clic en la casilla de verificación para aplicar un filtro.

![Filtro](assets/jobs-filter.png)

Utilice la búsqueda para encontrar un trabajo por su nombre.

![Buscar](assets/search.png)

## Ordenar y personalizar columnas

Cada trabajo muestra varias columnas que proporcionan información sobre el trabajo. Puede ordenar la información de cada columna y personalizar las columnas que se muestran.

### Ordenar columnas

Seleccione un encabezado de columna para ordenarlo en orden ascendente. Vuelva a seleccionar un encabezado de columna para ordenarlo en orden descendente.

### Personalizar columnas

Para ajustar las columnas visibles en la tabla:

1. Seleccione el icono de columna ![Icono de columna](assets/customize-columns-icon.png) en la parte superior derecha.

1. En el cuadro de diálogo Personalizar tabla, seleccione cada columna que desee ver y anule la selección de cada columna que desee ocultar.

   Las columnas disponibles son las siguientes:

* **Nombre de fuente**: Columna requerida. Muestra el nombre de la fuente. Los trabajos creados por la misma fuente tienen el mismo nombre de fuente.
* **ID de fuente**: muestra el ID de fuente, un identificador único. Los trabajos creados por la misma fuente tienen el mismo ID de fuente.
* **Grupo de informes**: Grupo de informes desde el que el trabajo hace referencia a los datos.
* **ID del grupo de informes**: El identificador único del grupo de informes.
* **Intervalo**: El intervalo de la fuente.
* **Tipo de destino**: El tipo de destino de la fuente.
* **Destino**: El destino de la fuente.
* **Propietario**: El propietario de la fuente.
* **Estado**: el estado de la fuente.
   * Esperando datos: el trabajo está en funcionamiento y se están recopilando datos para la ventana de informes.
   * Procesando: el trabajo está creando los archivos de datos y preparándolos para su envío.
   * Finalizado: el trabajo se completó sin problemas.
   * Error: el trabajo no se completó. Consulte [Solución de problemas de fuentes de datos](troubleshooting.md) para determinar la causa del error.
   * Esperando exportación: los datos de la ventana de informes aún no se han procesado por completo.
   * Sin datos: no hay datos en el grupo de informes para la ventana de informes solicitada.
* **Última modificación**: Hora a la que se modificó la fuente por última vez.
* **Fecha de inicio**: Hora a la que comenzó el trabajo. La fecha y la hora se muestran en la zona horaria del grupo de informes con horario GMT. Las fuentes diarias suelen comenzar cerca de la medianoche en el huso horario del grupo de informes.
* **Fecha de finalización**: La hora en que finalizó el trabajo. La fecha y la hora se muestran en la zona horaria del grupo de informes con horario GMT.

## Ver el historial de trabajos de una fuente de datos

Puede ver una lista de los trabajos de fuentes de datos anteriores de una fuente de datos determinada, junto con información sobre cada trabajo.

Para ver el historial de trabajos de una fuente de datos:

1. En Adobe Analytics, seleccione [!UICONTROL **Administración**] > [!UICONTROL **Fuentes de datos**].

   ![Administrador de fuentes de datos](assets/data-feed-manager.png)

1. Seleccione la casilla que está junto a la fuente de datos cuyo historial de trabajos desea ver y, a continuación, seleccione [!UICONTROL **Historial de trabajos**].

   Se muestra el historial del trabajo de fuentes de datos con la siguiente información disponible sobre cada trabajo (seleccione el icono de columna para agregar columnas que no estén visibles de forma predeterminada):

   * **[!UICONTROL Comienzo del período de solicitud]**

   * **[!UICONTROL Fin de período de solicitud]**

   * **[!UICONTROL Programado]**

   * **[!UICONTROL Iniciado]**

   * **[!UICONTROL Finalizado]**

   * **[!UICONTROL Ejecutar #]**

   * **[!UICONTROL Estado]**

   * **[!UICONTROL Código de error]**

   * **[!UICONTROL Mensaje de error]**

## Reenviar trabajos de fuentes de datos

Puede volver a enviar un trabajo de fuente de datos si desea volver a enviar el archivo de fuente de datos con los mismos datos y el mismo procesamiento que cuando se envió originalmente. También puede [volver a procesar un trabajo de fuente de datos](#reprocess-data-feed-jobs).

Para reenviar uno o varios trabajos de fuentes de datos:

1. En Adobe Analytics, seleccione [!UICONTROL **Administración**] > [!UICONTROL **Fuentes de datos**].

1. Seleccione la casilla que está junto a la fuente de datos que contiene los trabajos que desea reenviar y, a continuación, seleccione [!UICONTROL **Historial de trabajos**].

1. Seleccione la casilla de verificación que está junto a uno o más trabajos de fuente de datos y, a continuación, seleccione **[!UICONTROL Reenviar]**. <!-- What does the status need to be? Error, ... -->

   ![Volver a procesar trabajo de fuente de datos](assets/data-feed-job-resend.png)

## Volver a procesar trabajos de fuentes de datos

Puede volver a procesar los datos de origen de un trabajo de fuente de datos y enviarlos de nuevo con los datos procesados de nuevo. También puede [reenviar un trabajo de fuente de datos](#resend-data-feed-jobs).

Para volver a procesar uno o varios trabajos de fuentes de datos:

1. En Adobe Analytics, seleccione [!UICONTROL **Administración**] > [!UICONTROL **Fuentes de datos**].

1. Seleccione la casilla que está junto a la fuente de datos que contiene los trabajos que desea volver a procesar y, a continuación, seleccione [!UICONTROL **Historial de trabajos**].

1. Seleccione la casilla de verificación que está junto a uno o más trabajos de fuente de datos y, a continuación, seleccione **[!UICONTROL Volver a procesar]**. <!-- What does the status need to be? Error, ... -->

   ![Volver a procesar trabajo de fuente de datos](assets/data-feed-job-reprocess.png)

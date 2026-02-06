---
title: Administrar trabajos de fuentes de datos
description: Obtenga información sobre cómo administrar trabajos individuales en fuentes de datos. Navegue por la interfaz, utilice filtros y búsquedas, y busque definiciones de columnas.
feature: Data Feeds
exl-id: b17e333e-290f-42e4-b304-1e34282237a7
source-git-commit: d042bdb680504fdbf0ba346e5829713e529bd543
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 11%

---

# Administración de trabajos de fuentes de datos

Los trabajos son tareas individuales que generan un archivo comprimido. Se crean y se rigen por fuentes.

Puede ver el historial de trabajos de cada fuente de datos, reenviar trabajos o volver a procesar trabajos.

## Ver el historial de trabajos de una fuente de datos

Puede ver una lista de trabajos de fuentes de datos para una fuente de datos determinada, junto con información sobre cada trabajo.

Para ver el historial de trabajos de una fuente de datos:

1. Inicie sesión en [experiencecloud.adobe.com](https://experiencecloud.adobe.com) con sus credenciales de Adobe ID.

1. Seleccione el icono de 9 cuadrados en la esquina superior derecha, luego seleccione [!UICONTROL **Analytics**].

1. En la barra de navegación superior, vaya a [!UICONTROL **Administrador**] > [!UICONTROL **Fuentes de datos**].

   Se muestran las fuentes de datos de todos los grupos de informes a los que tiene acceso. O bien, si no se configuraron fuentes, la página mostrará el botón **[!UICONTROL Crear fuente de datos]**.

   ![Administrador de fuentes de datos](assets/data-feed-manager.png)

1. Seleccione la casilla que está junto a la fuente de datos que contiene los trabajos que desea ver y, a continuación, seleccione [!UICONTROL **Historial de trabajos**].

   Se muestra el historial de trabajos de fuentes de datos, con información sobre cada trabajo en las columnas disponibles.

1. (Opcional) Para ajustar las columnas visibles en la tabla, seleccione el icono de columna ![Icono de columna](assets/customize-columns-icon.png) en la parte superior derecha y, a continuación, en el cuadro de diálogo Personalizar tabla, seleccione cada columna que desee ver y anule la selección de cada columna que desee ocultar.

   Las columnas disponibles son las siguientes:

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

Cuando vuelve a enviar un trabajo de fuente de datos, vuelve a enviar el archivo de fuente de datos con los mismos datos y el mismo procesamiento que cuando se envió originalmente el archivo. También puede [volver a procesar un trabajo de fuente de datos](#reprocess-data-feed-jobs).

Para reenviar uno o varios trabajos de fuentes de datos:

1. En Adobe Analytics, seleccione [!UICONTROL **Administración**] > [!UICONTROL **Fuentes de datos**].

1. Seleccione la casilla que está junto a la fuente de datos que contiene los trabajos que desea reenviar y, a continuación, seleccione [!UICONTROL **Historial de trabajos**].

1. Seleccione la casilla de verificación que está junto a uno o más trabajos de fuente de datos y, a continuación, seleccione **[!UICONTROL Reenviar]**. <!-- What does the status need to be? Error, ... -->

   ![Volver a procesar trabajo de fuente de datos](assets/data-feed-job-resend.png)

## Volver a procesar trabajos de fuentes de datos

Cuando vuelve a procesar un trabajo de fuente de datos, vuelve a procesar los datos de origen de un trabajo de fuente de datos y los envía de nuevo con los datos procesados de nuevo. También puede [reenviar un trabajo de fuente de datos](#resend-data-feed-jobs).

Para volver a procesar uno o varios trabajos de fuentes de datos:

1. En Adobe Analytics, seleccione [!UICONTROL **Administración**] > [!UICONTROL **Fuentes de datos**].

1. Seleccione la casilla que está junto a la fuente de datos que contiene los trabajos que desea volver a procesar y, a continuación, seleccione [!UICONTROL **Historial de trabajos**].

1. Seleccione la casilla de verificación que está junto a uno o más trabajos de fuente de datos y, a continuación, seleccione **[!UICONTROL Volver a procesar]**. <!-- What does the status need to be? Error, ... -->

   ![Volver a procesar trabajo de fuente de datos](assets/data-feed-job-reprocess.png)

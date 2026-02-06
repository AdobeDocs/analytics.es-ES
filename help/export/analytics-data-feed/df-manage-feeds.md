---
title: Administrar fuentes de datos
description: Obtenga información sobre cómo navegar por la interfaz de fuentes de datos. Descubra cómo crear, editar y ver una fuente de datos.
feature: Data Feeds
exl-id: 4d4f0062-e079-48ff-9464-940c6425ad54
source-git-commit: d042bdb680504fdbf0ba346e5829713e529bd543
workflow-type: tm+mt
source-wordcount: '1277'
ht-degree: 15%

---

# Administración de fuentes de datos

El administrador de fuentes de datos le permite crear, editar y eliminar fuentes de datos para su organización. Si tiene permisos para acceder al administrador de fuentes de datos, puede administrar las fuentes de datos de todos los grupos de informes visibles para usted.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Administración de fuentes de datos](https://video.tv.adobe.com/v/25452?quality=12&learn=on){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]


## Ver fuentes de datos

1. Inicie sesión en [experiencecloud.adobe.com](https://experiencecloud.adobe.com) con sus credenciales de Adobe ID.
1. Seleccione el icono de 9 cuadrados en la esquina superior derecha, luego seleccione [!UICONTROL **Analytics**].
1. En la barra de navegación superior, vaya a [!UICONTROL **Administrador**] > [!UICONTROL **Fuentes de datos**].

   Se muestran las fuentes de datos de todos los grupos de informes a los que tiene acceso. O bien, si no se configuraron fuentes, la página mostrará el botón **[!UICONTROL Crear fuente de datos]**.

   ![Administrador de fuentes de datos](assets/data-feed-manager.png)

## Creación de una fuente de datos

El botón **[!UICONTROL Crear fuente de datos]** le permite crear una nueva fuente. Consulte [Crear una fuente de datos](create-feed.md) para obtener más información.

## Edición de una fuente de datos

1. En Adobe Analytics, seleccione [!UICONTROL **Administración**] > [!UICONTROL **Fuentes de datos**].

1. Busque la fuente de datos que desea editar. Para localizar una fuente de datos, puede [filtrar y buscar en la lista de fuentes de datos](#filter-and-search-the-list-of-data-feeds).

1. Seleccione la fuente de datos en la columna [!UICONTROL **Nombre de fuente**].

1. Realice los cambios que desee en la fuente de datos.

   Para obtener información acerca de las opciones de fuentes de datos, consulte [Crear y configurar una fuente de datos](/help/export/analytics-data-feed/create-feed.md#create-and-configure-a-data-feed) en [Crear una fuente de datos](/help/export/analytics-data-feed/create-feed.md).

   Al actualizar la sección [!UICONTROL **Destino**] de una fuente de datos que está editando, puede elegir una cuenta y una ubicación diferentes para la nueva fuente de datos en los campos desplegables [!UICONTROL **Cuenta**] y [!UICONTROL **Ubicación**].

   Las cuentas y ubicaciones se pueden editar tal como se describe en [Configurar cuentas de importación y exportación en la nube](/help/components/locations/configure-import-accounts.md) y [Configurar ubicaciones de importación y exportación en la nube](/help/components/locations/configure-import-locations.md). La edición de una cuenta o ubicación afecta a todos los elementos asociados con esa cuenta o ubicación.

   Las versiones anteriores del administrador de fuentes de datos le permitían crear destinos de FTP, SFTP, S3 y blob de Azure. Los destinos creados en estas versiones anteriores del administrador de fuentes de datos no se pueden editar ni copiar.

1. Seleccione [!UICONTROL **Guardar**].

## Filtrar y buscar la lista de fuentes de datos

1. En Adobe Analytics, seleccione [!UICONTROL **Administración**] > [!UICONTROL **Fuentes de datos**].

1. Utilice la búsqueda o los filtros para localizar una fuente específica.

   * En el campo de búsqueda, empiece a escribir el nombre de una fuente. En la lista de fuentes disponibles solo se muestran las fuentes que coinciden con.

     ![Buscar](assets/search.png)

   * En el extremo izquierdo, seleccione el icono de filtro para mostrar u ocultar las opciones de filtrado. Los filtros están organizados por categoría, incluidos **[!UICONTROL Grupos de informes]**, **[!UICONTROL Propietario]**, **[!UICONTROL Estado]** y **[!UICONTROL Etiquetas]**. Puede contraer o expandir las categorías de filtrado. Seleccione la casilla de verificación situada junto a cualquier filtro que desee aplicar.

     ![Filtro](assets/jobs-filter.png)

## Ver trabajos de fuentes de datos

1. En Adobe Analytics, seleccione [!UICONTROL **Administración**] > [!UICONTROL **Fuentes de datos**].

1. Seleccione la ficha [!UICONTROL **Trabajos**] para ver los trabajos individuales que cada una de las fuentes crea.

1. (Opcional) Para ver el historial de trabajos de fuentes de datos específicas, seleccione la casilla de verificación que hay junto a una fuente de datos y, a continuación, seleccione [!UICONTROL **Historial de trabajos**].

   Para obtener más información, consulte [Administrar trabajos de fuentes de datos](df-manage-jobs.md).

## Copiar una fuente de datos

1. En Adobe Analytics, seleccione [!UICONTROL **Administración**] > [!UICONTROL **Fuentes de datos**].

1. Seleccione la casilla que está junto a la fuente de datos que desea copiar y, a continuación, seleccione [!UICONTROL **Copiar**].

   Esto le llevará a [crear una nueva fuente](create-feed.md) con toda la configuración de la fuente actual. La opción para copiar no está visible si se selecciona más de una fuente de datos.

   Al actualizar la sección [!UICONTROL **Destino**] de una fuente de datos que está copiando, puede elegir una cuenta y una ubicación diferentes para la nueva fuente de datos en los campos desplegables [!UICONTROL **Cuenta**] y [!UICONTROL **Ubicación**].

   Las cuentas y ubicaciones se pueden editar tal como se describe en [Configurar cuentas de importación y exportación en la nube](/help/components/locations/configure-import-accounts.md) y [Configurar ubicaciones de importación y exportación en la nube](/help/components/locations/configure-import-locations.md). La edición de una cuenta o ubicación afecta a todos los elementos asociados con esa cuenta o ubicación.

   Las versiones anteriores del administrador de fuentes de datos le permitían crear destinos de FTP, SFTP, S3 y blob de Azure. Los destinos creados en estas versiones anteriores del administrador de fuentes de datos no se pueden editar ni copiar.

## Pausar una fuente de datos

Al pausar una fuente de datos, esta deja de procesarla y establece su estado en **[!UICONTROL Inactiva]**.

Cuando reactiva la fuente después de pausarla, los datos durante el tiempo que la fuente estuvo en pausa se procesan para fuentes de relleno, pero no para fuentes activas. Para obtener más información, consulte [Activar una fuente de datos](#activate-a-data-feed).

Para pausar una fuente de datos:

1. En Adobe Analytics, seleccione [!UICONTROL **Administración**] > [!UICONTROL **Fuentes de datos**].

1. Seleccione la casilla que está junto a la fuente de datos que desea pausar y, a continuación, seleccione [!UICONTROL **Pausar**].

## Activar una fuente de datos

Puede activar fuentes inactivas.

Cuando se reactiva una fuente, es posible que los datos no se procesen automáticamente durante el tiempo en que la fuente esté inactiva. El procesamiento de los datos depende de si son fuentes de relleno o activas:

* **Las fuentes de relleno** (fuentes que solo procesan datos históricos) reanudan el procesamiento de datos desde donde se detuvieron y rellenan las fechas si es necesario.

* **Las fuentes en directo** reanudan el procesamiento de datos desde el momento en que se activan. Esto significa que los datos no se procesan durante el tiempo en que la fuente se pausó en el momento en que se activó. Si necesita los datos durante este período de tiempo, debe configurar un relleno.

Para activar una fuente de datos:

1. En Adobe Analytics, seleccione [!UICONTROL **Administración**] > [!UICONTROL **Fuentes de datos**].

1. Seleccione la casilla que está junto a la fuente de datos inactiva que desea activar y, a continuación, seleccione [!UICONTROL **Activar**].

## Eliminar una fuente de datos

Al eliminar una fuente de datos, su estado se establece en [!UICONTROL Eliminada]. Las fuentes de datos deben tener el estado [!UICONTROL Activo] para poder eliminarse.

Para eliminar una fuente de datos:

1. En Adobe Analytics, seleccione [!UICONTROL **Administración**] > [!UICONTROL **Fuentes de datos**].

1. Seleccione la casilla que está junto a la fuente de datos que desea eliminar y, a continuación, seleccione [!UICONTROL **Eliminar**].

## Ordenar y personalizar columnas en el administrador de fuentes de datos

Cada fuente de datos muestra varias columnas que proporcionan información sobre la fuente. Puede ordenar la información de cada columna y personalizar las columnas que se muestran.

### Ordenar columnas

Seleccione un encabezado de columna para ordenarlo en orden ascendente. Vuelva a seleccionar un encabezado de columna para ordenarlo en orden descendente.

### Personalizar columnas

Para ajustar las columnas visibles en la tabla:

1. Seleccione el icono de columna ![Icono de columna](assets/customize-columns-icon.png) en la parte superior derecha.

1. En el cuadro de diálogo Personalizar tabla, seleccione cada columna que desee ver y anule la selección de cada columna que desee ocultar.

   Las columnas disponibles son las siguientes:

   * **Nombre de fuente**: Columna requerida. Muestra el nombre de la fuente.
   * **ID de fuente**: muestra el ID de fuente, un identificador único.
   * **Grupo de informes**: grupo de informes desde el que la fuente hace referencia a los datos.
   * **ID del grupo de informes**: El identificador único del grupo de informes.
   * **Intervalo**: indicador de si la fuente es por hora o por día.
   * **Tipo de destino**: el tipo de destino de la fuente. Por ejemplo, Amazon S3, GCP o Azure.
   * **Destino**: La ubicación en la que se coloca el archivo.
   * **Propietario**: cuenta de usuario que creó la fuente.
   * **Estado**: el estado de la fuente.
      * Activa: la fuente se está ejecutando.
      * Aprobación pendiente: en algunas circunstancias, una fuente requiere la aprobación de Adobe para poder empezar a generar trabajos.
      * Eliminada: se elimina la fuente.
      * Completada: la fuente ha finalizado el procesamiento. Una fuente completada puede editarse, pausarse y cancelarse.
      * Pendiente: la fuente se crea pero aún no está activa. Las fuentes permanecen en este estado durante un corto periodo de transición.
      * Inactiva: equivalente a un estado “pausado” o “en espera”. Para obtener información sobre lo que sucede con las fuentes de relleno y las fuentes activas cuando se reactiva una fuente inactiva, consulte [Activar una fuente de datos](#activate-a-data-feed).
   * **Última modificación**: Fecha en la que se modificó la fuente por última vez. La fecha y la hora se muestran en la zona horaria del grupo de informes con horario GMT.
   * **Fecha de inicio**: La fecha del primer trabajo de esta fuente. La fecha y la hora se muestran en la zona horaria del grupo de informes con horario GMT.
   * **Fecha de finalización**: La fecha del último trabajo de esta fuente. Las fuentes de datos en curso no tienen una fecha de finalización.


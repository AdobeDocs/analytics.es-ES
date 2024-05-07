---
title: Interfaz de usuario de fuentes de datos
description: Obtenga información sobre cómo navegar por la interfaz de fuentes de datos.
feature: Data Feeds
exl-id: 4d4f0062-e079-48ff-9464-940c6425ad54
source-git-commit: 6b8366b451be1612331f517ee80fd57744deafdc
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 68%

---

# Administración de fuentes de datos

El administrador de fuentes de datos le permite crear, editar y eliminar fuentes de datos para su organización. Si tiene permisos para acceder al administrador de fuentes de datos, puede administrar las fuentes de datos de todos los grupos de informes visibles para usted.

Aquí tiene un vídeo sobre la IU de administración de fuentes de datos:

>[!VIDEO](https://video.tv.adobe.com/v/25452/?quality=12)

Para acceder a la administración de fuentes de datos, siga estos pasos:

1. Inicie sesión en [experiencecloud.adobe.com](https://experiencecloud.adobe.com) con sus credenciales de Adobe ID.
1. Seleccione el icono de 9 cuadrados en la esquina superior derecha y, a continuación, seleccione [!UICONTROL **Analytics**].
1. En la barra de navegación superior, vaya a [!UICONTROL **Administrador**] > [!UICONTROL **Fuentes de datos**].

## Navegación por la interfaz

Al llegar a la página del administrador de fuentes de datos, la interfaz tiene un aspecto similar al siguiente:

![Fuentes de datos](assets/feeds.png)

Si no se han definido fuentes, la página mostrará el botón [!UICONTROL Crear nueva fuente de datos].

### Filtros y búsqueda

Utilice la búsqueda o los filtros para localizar una fuente específica.

* En el campo de búsqueda, empiece a escribir el nombre de una fuente. En la lista de fuentes disponibles solo se muestran las fuentes que coinciden con.

* En el extremo izquierdo, haga clic en el icono de filtro para mostrar u ocultar las opciones de filtrado. Los filtros están organizados por categoría. Puede contraer o expandir las categorías de filtrado. Seleccione la casilla de verificación situada junto a cualquier filtro que desee aplicar.

  ![Filtro](assets/filters.png)

### Fuentes y trabajos

Seleccione el [!UICONTROL **Trabajos**] para ver los trabajos individuales que cada una de las fuentes crea. Consulte [Administración de trabajos de fuentes de datos](df-manage-jobs.md).

### Agregar

El [!UICONTROL Añadir] permite crear una fuente nueva. Consulte [Crear una fuente de datos](create-feed.md) para obtener más información.

### Columnas

Cada fuente creada muestra varias columnas que proporcionan información al respecto. Seleccione un encabezado de columna para ordenarlo en orden ascendente. Vuelva a seleccionar un encabezado de columna para ordenarlo en orden descendente. Si no puede ver una columna específica, haga clic en el icono de columna en la parte superior derecha.

![Icono de columna](assets/cols.jpg)

* **Nombre de fuente**: columna requerida. Muestra el nombre de la fuente.
* **ID de fuente**: muestra el ID de fuente, un identificador único.
* **Grupo de informes**: grupo de informes desde el que la fuente hace referencia a los datos.
* **ID del grupo de informes**: el identificador único del grupo de informes.
* **Columnas de datos**: qué columnas de datos están activas para la fuente. En la mayoría de los casos, hay demasiadas columnas para mostrar en este formato.
* **Intervalo**: indicador de si la fuente es por hora o por día.
* **Tipo de destino**: el tipo de destino de la fuente. Por ejemplo, Amazon S3, GCP o Azure.
* **Host de destino**: Ubicación en la que se coloca el archivo.
* **Propietario**: cuenta de usuario que creó la fuente.
* **Estado**: el estado de la fuente.
   * Activa: la fuente se está ejecutando.
   * Aprobación pendiente: en algunas circunstancias, una fuente requiere la aprobación de Adobe para poder empezar a generar trabajos.
   * Eliminada: se elimina la fuente.
   * Completada: la fuente ha finalizado el procesamiento. Una fuente completada puede editarse, pausarse y cancelarse.
   * Pendiente: la fuente se crea pero aún no está activa. Las fuentes permanecen en este estado durante un corto periodo de transición.
   * Inactiva: equivalente a un estado “pausado” o “en espera”. Si se reactiva una fuente de relleno (una fuente que solo procesa datos históricos), se reanuda la entrega de trabajos desde el momento en que se detuvo. Si se reactiva una fuente activa, se reanuda la entrega de trabajos desde el momento en que se detuvo.
* **Última modificación**: fecha en la que se modificó la fuente por última vez. La fecha y la hora se muestran en la zona horaria del grupo de informes con horario GMT.
* **Fecha de inicio**: la fecha del primer trabajo de esta fuente. La fecha y la hora se muestran en la zona horaria del grupo de informes con horario GMT.
* **Fecha de finalización**: la fecha del último trabajo de esta fuente. Las fuentes de datos en curso no tienen una fecha de finalización.

## Acciones de la fuente de datos

Haga clic en la casilla de verificación situada junto a una fuente de datos para mostrar las acciones disponibles.

* **Historial de trabajos**: muestra todos los trabajos relacionados con estas fuentes de datos. Conduce automáticamente a la [interfaz de administración de trabajos](df-manage-jobs.md).
* **Eliminar**: elimina la fuente de datos y establece su estado en [!UICONTROL Eliminada].
* **Copiar**: conduce a [crear una fuente nueva](create-feed.md) con todos los ajustes de la fuente actual. No puede copiar una fuente de datos si hay más de una seleccionada.
* **Pausar**: detiene el procesamiento de la fuente y establece su estado en [!UICONTROL Inactiva].
* **Activar**: solo disponible para fuentes inactivas. Las fuentes de relleno (fuentes que solo procesan datos históricos) reanudan el procesamiento de datos desde donde se detuvieron y rellenan las fechas si es necesario. Las fuentes activas reanudan el procesamiento de datos desde el momento actual.

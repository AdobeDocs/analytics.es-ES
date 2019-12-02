---
title: UI de fuente de datos
description: Obtenga información sobre cómo navegar por la interfaz de fuentes de datos.
translation-type: tm+mt
source-git-commit: c9b3471b138c2e056a5abadb4ace6bb4eccd1d72

---


# Administrar fuentes de datos

El administrador de fuentes de datos le permite crear, editar y eliminar fuentes de datos para su organización. Si tiene permisos para acceder al administrador de fuentes de datos, puede administrar las fuentes de datos de todos los grupos de informes visibles para usted.

Para acceder a la administración de fuentes de datos, siga estos pasos:

1. Log in to [experiencecloud.adobe.com](https://experiencecloud.adobe.com).
2. Haga clic en el menú de 9 cuadrícula en la parte superior derecha y, a continuación, haga clic en [!UICONTROL Analytics].
3. En el menú superior, haga clic en [!UICONTROL Administración] &gt; Fuentes [!UICONTROL de datos].

![Menú de fuente de datos](assets/AdminMenu.png)

## Navegación por la interfaz

Al llegar a la página del administrador de fuentes de datos, la interfaz tiene un aspecto similar al siguiente:

![Fuentes de datos](assets/feeds.png)

Si no se han definido fuentes, la página mostrará el botón [!UICONTROL Crear nueva fuente de datos].

### Filtros y búsqueda

Utilice filtros y busque la fuente exacta que busca.

En el extremo izquierdo, haga clic en el icono de filtro para mostrar u ocultar las opciones de filtrado. Los filtros están organizados por categoría. Haga clic en el protector para contraer o expandir las categorías de filtrado. Haga clic en la casilla de verificación para aplicar ese filtro.

![Filtro](assets/filters.jpg)

Utilice la búsqueda para buscar una fuente por nombre.

![Buscar](assets/search.jpg)

### Fuentes y trabajos

Haga clic en la ficha Trabajos para ver los trabajos individuales que cada una de las fuentes crea. Consulte [Administración de trabajos](df-manage-jobs.md)de fuentes de datos.

### Agregue

Cerca de las fichas de fuentes y trabajos, haga clic en el botón + [!UICONTROL Agregar] para crear una nueva fuente. Consulte [Agregar una fuente](create-feed.md) para obtener más información.

### Columnas

Cada fuente creada muestra varias columnas que proporcionan información al respecto. Haga clic en el encabezado de una columna para ordenarla en orden ascendente. Vuelva a hacer clic en el encabezado de una columna para ordenarla en orden descendente. Si no puede ver una columna específica, haga clic en el icono de columna en la parte superior derecha.

![Icono de columna](assets/cols.jpg)

* **Nombre** de fuente: Columna requerida. Muestra el nombre de la fuente.
* **ID** de fuente: Muestra el ID de fuente, un identificador único.
* **Grupo** de informes: Grupo de informes desde el que la fuente hace referencia a los datos.
* **ID** del grupo de informes: El identificador único del grupo de informes.
* **Columnas** de datos: Qué columnas de datos están activas para la fuente. En la mayoría de los casos, hay demasiadas columnas para mostrar en este formato.
* **Intervalo**: Indicador de si la fuente es por hora o por día.
* **Tipo** de destino: El tipo de destino de la fuente. Por ejemplo, FTP, Amazon S3 o Azure.
* **Host** de destino: Ubicación en la que se coloca el archivo. Por ejemplo, `ftp.example.com`.
* **Propietario**: Cuenta de usuario que creó la fuente.
* **Estado**: Estado de la fuente.
   * Activo: La fuente está operativa.
   * Aprobación pendiente: En algunas circunstancias, una fuente requiere la aprobación de Adobe para poder empezar a generar trabajos.
   * Eliminado: Se elimina la fuente.
   * Completado: La fuente ha finalizado el procesamiento. Una fuente completada se puede editar, poner en espera o cancelar.
   * Pendiente: La fuente se crea pero aún no está activa. Las fuentes permanecen en este estado durante un corto período de transición.
   * Inactivo: Equivalente a un estado 'pausado' o 'en espera'. Cuando se reactiva la fuente, se reanuda la entrega de trabajos desde el momento en que se detuvo.
* **Última modificación**: Fecha en la que se modificó la fuente por última vez. La fecha y la hora se muestran en la zona horaria del grupo de informes con desplazamiento GMT.
* **Fecha** inicial: La fecha del primer trabajo de esta fuente. La fecha y la hora se muestran en la zona horaria del grupo de informes con desplazamiento GMT.
* **Fecha** final: La fecha del último trabajo de esta fuente. Las fuentes de datos en curso no tienen una fecha de finalización.

## Acciones de fuentes de datos

Haga clic en la casilla de verificación situada junto a una fuente de datos para mostrar las acciones disponibles.

* **Historial** de trabajos: Ver todos los trabajos relacionados con estas fuentes de datos. Le lleva automáticamente a la interfaz [de](df-manage-jobs.md)gestión de trabajos.
* **Eliminar**: Elimina la fuente de datos, estableciendo su estado en [!UICONTROL Eliminado].
* **Copiar**: Le lleva a [crear una fuente](create-feed.md) nueva con todos los ajustes de la fuente actual. No puede copiar una fuente de datos si hay más de una seleccionada.
* **Pausar**: Detiene el procesamiento de la fuente y establece su estado en [!UICONTROL Inactivo].
* **Activar**: Solo disponible para fuentes inactivas. Recopila datos de procesamiento justo donde los dejó, rellenando las fechas si es necesario.

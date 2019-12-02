---
title: Administrar trabajos de fuentes de datos
description: Obtenga información sobre cómo administrar trabajos individuales en fuentes de datos.
translation-type: tm+mt
source-git-commit: 7db88bce7b3d0f90fa5b50664d7c0c23904348c0

---


# Administrar trabajos de fuentes de datos

Los trabajos son tareas individuales que generan un archivo comprimido. Se crean y se rigen por fuentes.

Para acceder a la administración de trabajos de fuente de datos, siga estos pasos:

1. Log in to [experiencecloud.adobe.com](https://experiencecloud.adobe.com).
2. Haga clic en el menú de 9 cuadrícula en la parte superior derecha y, a continuación, haga clic en [!UICONTROL Analytics].
3. En el menú superior, haga clic en [!UICONTROL Administración] &gt; Fuentes [!UICONTROL de datos].
4. Haga clic en la ficha Trabajos cerca de la parte superior.

![Menú de fuente de datos](assets/AdminMenu.png)

## Navegación por la interfaz

Un trabajo de fuente de datos es una instancia única en la que Adobe procesa y genera un archivo comprimido para una ventana de informes determinada. El administrador de trabajos proporciona una vista refinada para ver el estado de los trabajos individuales.

![Trabajos](assets/jobs.jpg)

### Filtros y búsqueda

Utilice filtros y busque el trabajo exacto que busca.

En el extremo izquierdo, haga clic en el icono de filtro para mostrar u ocultar las opciones de filtrado. Los filtros están organizados por categoría. Haga clic en el protector para contraer o expandir las categorías de filtrado. Haga clic en la casilla de verificación para aplicar ese filtro.

![Filtro](assets/jobs-filter.jpg)

Utilice la búsqueda para buscar un trabajo por nombre.

![Buscar](assets/search.jpg)

### Fuentes y trabajos

Haga clic en la ficha Fuentes para ver las fuentes globales que crean estos trabajos. See [Manage data feeds](df-manage-feeds.md).

### Columnas

Cada trabajo muestra varias columnas que proporcionan información al respecto. Haga clic en el encabezado de una columna para ordenarla en orden ascendente. Vuelva a hacer clic en el encabezado de una columna para ordenarla en orden descendente. Si no puede ver una columna específica, haga clic en el icono de columna en la parte superior derecha.

![Icono de columna](assets/job-cols.jpg)

* **ID** de fuente: Muestra el ID de fuente, un identificador único. Los trabajos creados por la misma fuente tienen el mismo ID de fuente.
* **ID** del trabajo: Identificador único del trabajo. Todos los trabajos tienen un ID de trabajo diferente.
* **Nombre** de fuente: Columna requerida. Muestra el nombre de la fuente. Los trabajos creados por la misma fuente tienen el mismo nombre de fuente.
* **Grupo** de informes: Grupo de informes desde el que el trabajo hace referencia a los datos.
* **ID** del grupo de informes: El identificador único del grupo de informes.
* **Hora** de inicio: Hora a la que comenzó el trabajo. La fecha y la hora se muestran en la zona horaria del grupo de informes con desplazamiento GMT. Las fuentes diarias suelen comenzar cerca de la medianoche en el huso horario del grupo de informes.
* **Estado**: Estado de la fuente.
   * Esperando datos: El trabajo está en funcionamiento y se están recopilando datos para la ventana de informes.
   * Procesamiento: El trabajo está creando los archivos de datos y preparándose para enviarlos.
   * Finalizado: El trabajo se completó sin problemas.
   * Error: El trabajo no se completó. Consulte [Solucionar problemas de trabajos](jobs-troubleshooting.md) para determinar la causa del error.
   * Esperando exportación: Los datos de la ventana de informes aún no se han procesado por completo.
   * Sin datos: No hay datos en el grupo de informes para la ventana de informes solicitada.
* **Tiempo** de finalización: La hora en que terminó el trabajo. La fecha y la hora se muestran en la zona horaria del grupo de informes con desplazamiento GMT.
* **Fecha** solicitada: Ventana de informes del archivo. Las fuentes diarias suelen mostrar 00:00 - 23:59 con un desplazamiento GMT, lo que indica un día completo según la zona horaria del grupo de informes. Las fuentes por hora muestran la hora individual para la que está el trabajo.

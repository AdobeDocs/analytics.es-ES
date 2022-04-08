---
title: Exportación de datos de clasificación mediante FTP
description: La exportación a FTP ofrece más flexibilidad con las descargas de conjuntos de datos, incluida la descarga de datos de varios grupos de informes y la descarga de archivos de conjuntos de datos que superen las 50 000 filas de datos
feature: Classifications
exl-id: 6f97f0b2-1a04-407f-9df9-8715da52037d
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: ht
source-wordcount: '612'
ht-degree: 100%

---

# Exportación de datos de clasificación mediante FTP

La opción de FTP ofrece más flexibilidad a la hora de descargar conjuntos de datos: permite descargar datos de varios grupos de informes y descargar archivos de conjuntos de datos de más de 50 000 filas de datos. Antes de descargar datos de clasificación mediante FTP, cree una cuenta de FTP.

Al aplicar filtros de datos deben tenerse en cuenta las siguientes circunstancias:

* Pueden utilizarse comodines para definir el filtro de datos. Utilice un asterisco `*` para que coincida con cero o más caracteres y un signo de interrogación `?` para que coincida exactamente con un carácter. Utilice `?*` para que coincida con uno o más caracteres.
* Por lo general, si se aplican ambos tipos de filtros de datos a una descarga, solo se descargan las filas que coinciden con ambas reglas. Pese a ello, se aplican las siguientes excepciones:
   * Si Filas con columna vacía = Todas las columnas, se comprueba si todas las columnas, a excepción de la indicada en la primera regla, están vacías. Con esta excepción, nos aseguramos de que la herramienta descargue todas las filas con una columna que coincida con la primera regla y que tenga también todas las demás columnas vacías.
   * Al descargar filas de datos basadas en columnas vacías, se comprueba si todas las columnas, a excepción de las indicadas en la primera regla, están vacías.
   * Si se especifica la misma columna en ambas reglas de filtro (es prácticamente imposible cumplir ambos criterios), se descargarán sólo las filas que coincidan con la primera regla.
   * Las exportaciones de FTP tienen un límite de 30 columnas.

## Exportar clasificaciones a través del FTP

Estos pasos describen cómo exportar (descargar) clasificaciones desde Adobe Analytics a través del FTP.

1. Crear una cuenta de FTP.
1. Vaya a [!UICONTROL Administración] > [!UICONTROL Importador de clasificaciones].
1. Haga clic en la pestaña **[!UICONTROL Importación de FTP]**.
1. Configure los campos de la exportación de FTP.
1. Haga clic en **[!UICONTROL Exportar archivo]**.
1. Guarde el conjunto de datos en el sistema local.

## Descripciones de los campos

| Elemento | Descripciones |
| --- | --- |
| [!UICONTROL Seleccionar grupo de informes] | Seleccione el grupo de informes desde el que desea exportar los datos del informe. |
| [!UICONTROL Conjunto de datos a clasificar] | Desde el menú desplegable, seleccione el conjunto de datos que se debe clasificar. |
| [!UICONTROL Seleccionar cantidad de filas] | Especifica el número de filas de datos que debe exportarse.<ul><li>Seleccione **[!UICONTROL Todos]** para descargar todos los datos de informe.</li><li>Seleccione **[!UICONTROL Limitar filas de datos a]** si desea indicar un número concreto de filas a descargar.</li></ul> |
| [!UICONTROL Filtrar por fecha de recepción] | Opcional. Filtra los datos por fecha de recepción. Debe especificarse el intervalo de fecha cuyos datos van a descargarse. |
| [!UICONTROL Aplicar filtro de datos] | Opcional. Filtra el conjunto de datos por criterios de datos. Puede filtrarse la descarga para que incluya filas de datos que contienen un valor específico o valores de columna (clasificación) no asignados. |
| [!UICONTROL Filtro de fecha] | Opcional. Filtrar los datos por datos de campaña. Únicamente pueden descargarse datos de campañas activas o seleccionar campañas que comenzarán (o finalizarán) en un intervalo de fecha específico. |
| [!UICONTROL Exportación numérica 2] | Puede importar al sistema clasificaciones numéricas 2 mediante el importador. Las clasificaciones numéricas 2 son variables útiles que puede cambiar con el tiempo para distintos elementos, tales como los valores de costo y presupuesto del informe Canal de marketing. |
| [!UICONTROL Cuenta de FTP] | Especifique la información del servidor FTP donde desea que Adobe descargue el archivo de datos, incluidos el nombre de host y el puerto, la ruta de acceso al directorio de destino, el nombre de usuario y la contraseña. |
| [!UICONTROL Notificación] | Especifica la dirección de correo electrónico donde se recibirán las notificaciones sobre esta descarga de FTP. |
| [!UICONTROL Codificación] | Seleccione la codificación de caracteres del archivo de datos. El formato de codificación predeterminado es UTF-8 o ISO-8859-1, según la codificación cargada para la clasificación. UTF-8 a UTF-16 convierte sus clasificaciones con codificación UTF-8 en clasificaciones UTF-16. ISO-8859-1 a UTF-16 convierte sus clasificaciones con codificación ISO-8859-1 en clasificaciones UTF-16.<br>**Nota:** Si selecciona la conversión a UTF-16, la codificación de origen debe coincidir con la codificación de la carga original u obtendrá resultados inesperados. Se recomienda la codificación de todos los archivos cargados en UTF-8 sin BOM. |

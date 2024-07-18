---
title: Exportación del explorador
description: La exportación del explorador permite exportar los datos de clasificación a un archivo delimitado por tabuladores.
feature: Classifications
exl-id: f4c709b2-f707-4e3c-82ba-6b43def3e698
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '651'
ht-degree: 100%

---

# Exportación del explorador

La exportación del explorador permite exportar los datos de clasificación a un archivo delimitado por tabuladores.

[!UICONTROL Administración] > [!UICONTROL Importador de clasificaciones]

El archivo del conjunto de datos es un archivo de datos delimitado por tabuladores (con la extensión de nombre de archivo.tab) compatible con la mayoría de las aplicaciones de hojas de cálculo.

>[!NOTE]
>Las exportaciones del explorador tienen un límite de 30 columnas.

## Descripciones de los campos

| Elemento | Descripciones |
| --- | --- |
| Seleccionar grupo de informes | Seleccione el grupo de informes desde el que desea exportar los datos del informe. |
| Conjunto de datos a clasificar | Desde el menú desplegable, seleccione el conjunto de datos que se debe clasificar. |
| Seleccionar cantidad de filas | Especifica el número de filas de datos que debe exportarse.<ul><li>Seleccione **[!UICONTROL Todo]** para exportar todos los datos del informe (máximo 50 000 filas).</li><li>Seleccione **[!UICONTROL Limitar filas de datos a]** si desea indicar un número concreto de filas a descargar.</li></ul>Si desea descargar más de 50 000 filas de datos, utilice la opción de descarga mediante FTP. |
| Filtrar por fecha de recepción | Opcional. Filtra los datos por fecha de recepción. Debe especificarse el intervalo de fecha cuyos datos van a descargarse. |
| Aplicar filtro de datos | Opcional. Filtra el conjunto de datos por criterios de datos. Puede filtrarse la descarga para que incluya filas de datos que contienen un valor específico o valores de columna (clasificación) no asignados. Al aplicar filtros de datos deben tenerse en cuenta las siguientes circunstancias:<ul><li>Pueden utilizarse comodines para definir el filtro de datos. Utilice un asterisco para que coincida con cero o más caracteres y un signo de interrogación `?` para que coincida exactamente con un carácter. Utilice `?*` para que coincida con uno o más caracteres.</li><li>Por lo general, si se aplican ambos tipos de filtros de datos a una descarga, solo se descargan las filas que coinciden con ambas reglas. Pese a ello, se aplican las siguientes excepciones:<ul><li>Si Filas con columna vacía = Todas las columnas, se comprueba si todas las columnas, a excepción de la indicada en la primera regla, están vacías. Con esta excepción, nos aseguramos de que el sistema descargue todas las filas con una columna que coincida con la primera regla y que tenga también todas las demás columnas vacías.</li><li>Al descargar filas de datos basadas en columnas vacías, se comprueba si todas las columnas, a excepción de las indicadas en la primera regla, están vacías.</li><li>Si se especifica la misma columna en ambas reglas de filtro (es prácticamente imposible cumplir ambos criterios), se descargarán sólo las filas que coincidan con la primera regla.</li></ul></ul> |
| Filtro de datos | Opcional. Filtra los datos por datos de campaña. Únicamente pueden descargarse datos de campañas activas o seleccionar campañas que comenzarán (o finalizarán) en un intervalo de fecha específico.<br>**Importante**: Esta opción no está disponible para los grupos de informes habilitados para la nueva arquitectura de clasificación. |
| Exportación numérica 2 | Puede importar al sistema clasificaciones numéricas 2 mediante el importador. Las clasificaciones numéricas 2 son variables útiles que puede cambiar con el tiempo para distintos elementos, tales como los valores de costo y presupuesto del informe Canal de marketing. Consulte Clasificaciones numéricas 2 para obtener información sobre cómo cargar datos a través de las clasificaciones numéricas 2. |
| Codificación | Seleccione la codificación de caracteres del archivo de datos. El formato de codificación predeterminado es UTF-8 o ISO-8859-1, según la codificación cargada para la clasificación. UTF-8 a UTF-16 convierte sus clasificaciones con codificación UTF-8 en clasificaciones UTF-16. ISO-8859-1 a UTF-16 convierte sus clasificaciones con codificación ISO-8859-1 en clasificaciones UTF-16.<br>**Nota:** Si selecciona la conversión a UTF-16, la codificación de origen debe coincidir con la codificación de la carga original u obtendrá resultados inesperados. Se recomienda la codificación de todos los archivos cargados en UTF-8 sin BOM. |
| Salida de cita | Especifica la versión 2.1 del archivo de clasificación. Esta configuración inserta comillas antes y después de los caracteres especiales para que la exportación funcione correctamente en Excel cuando haya un salto de línea en los valores eVar. Puede identificar si un archivo de clasificación es de la versión 2.1 abriendo el archivo descargado. Verá v2.1 en el encabezado. Por ejemplo: `## SC SiteCatalyst SAINT Import File v:2.1` |

## Exportar los datos de clasificación a través del explorador

1. Haga clic en [!UICONTROL Administración] > [!UICONTROL Importador de clasificaciones].
1. Haga clic en la ficha [!UICONTROL Exportación del explorador.]
1. Especifique los detalles del conjunto de datos:
1. Haga clic en [!UICONTROL Exportar archivo].
1. Guarde el conjunto de datos en el sistema local.

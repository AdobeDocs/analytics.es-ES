---
title: Exportación del explorador
description: La exportación del explorador permite exportar los datos de clasificación a un archivo delimitado por tabuladores.
feature: Classifications
exl-id: f4c709b2-f707-4e3c-82ba-6b43def3e698
source-git-commit: ca84a5f807545d7196e2e0e90d3209c32d3fd789
workflow-type: tm+mt
source-wordcount: '652'
ht-degree: 60%

---

# Exportación del explorador (heredada)

{{classification-importer-deprecation}}

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
| Filtrar por fecha de recepción | (Opcional) Filtre los datos por la fecha en que se recibieron. Especifique el intervalo de fechas para el que desea descargar datos. |
| Aplicar filtro de datos | (Opcional) Filtre el conjunto de datos por criterios de datos. Puede filtrarse la descarga para que incluya filas de datos que contienen un valor específico o valores de columna (clasificación) no asignados. Tenga en cuenta los siguientes problemas al aplicar filtros de datos:<ul><li>Puede utilizar comodines al definir el filtro de datos. Utilice un asterisco para que coincida con cero o más caracteres y un signo de interrogación `?` para que coincida exactamente con un carácter. Utilice `?*` para que coincida con uno o más caracteres.</li><li>Normalmente, al aplicar ambos tipos de filtros de datos a una descarga, solo se descargan las filas que coinciden con ambas reglas. Sin embargo, se aplican las siguientes excepciones:<ul><li>Si Filas con columna vacía = Todas las columnas, se comprueba si todas las columnas, a excepción de la indicada en la primera regla, están vacías. Esta excepción garantiza que el sistema descargue cualquier fila con una columna que coincida con la primera regla que también tenga todas las demás columnas vacías.</li><li>Al descargar filas de datos basadas en columnas vacías, se comprueba si todas las columnas, excepto las especificadas en la primera regla, están vacías.</li><li>Si se especifica la misma columna para ambas reglas de filtro (es casi imposible cumplir ambos criterios), solo se descargan las filas que coincidan con la primera regla.</li></ul></ul> |
| Filtro de datos | (Opcional) Filtrar los datos por datos de campaña. Solo puede descargar datos de campañas activas, o bien puede seleccionar campañas que comenzaron (o finalizaron) en un intervalo de fechas específico.<br>**Importante**: Esta opción no está disponible para los grupos de informes habilitados para la nueva arquitectura de clasificación. |
| Exportación numérica 2 | Puede importar al sistema clasificaciones numéricas 2 mediante el importador. Las clasificaciones numéricas 2 son variables útiles que puede cambiar con el tiempo para distintos elementos, tales como los valores de costo y presupuesto del informe Canal de marketing. Consulte Clasificaciones numéricas 2 para obtener información sobre cómo cargar datos a través de las clasificaciones numéricas 2. |
| Codificación | Seleccione la codificación de caracteres del archivo de datos. El formato de codificación predeterminado es UTF-8 o ISO-8859-1, según la codificación cargada para la clasificación. UTF-8 a UTF-16 convierte sus clasificaciones con codificación UTF-8 en clasificaciones UTF-16. Las clasificaciones con codificación ISO-8859-1 a UTF-16 convierten sus clasificaciones con codificación ISO-8859-1 a la codificación UTF-16.<br>**Nota:** Si selecciona convertir a UTF-16, la codificación de origen debe coincidir con la codificación de la carga original o puede obtener resultados inesperados. Recomendamos codificar todos los archivos cargados en UTF-8 sin BOM. |
| Salida de presupuesto | Especifica la versión 2.1 del archivo de clasificación. Esta configuración inserta comillas antes y después de los caracteres especiales para que la exportación funcione correctamente en Excel cuando haya un salto de línea en los valores eVar. Puede identificar si un archivo de clasificación es de la versión 2.1 abriendo el archivo descargado. Verá la versión 2.1 en el encabezado. Por ejemplo: `## SC SiteCatalyst SAINT Import File v:2.1` |

## Exportar los datos de clasificación a través del explorador

1. Haga clic en [!UICONTROL Administración] > [!UICONTROL Importador de clasificaciones].
1. Haga clic en la ficha [!UICONTROL Exportación del explorador.]
1. Especifique los detalles del conjunto de datos:
1. Haga clic en [!UICONTROL Exportar archivo].
1. Guarde el conjunto de datos en el sistema local.

---
title: Exportación del explorador
description: La exportación del explorador permite exportar los datos de clasificación a un archivo delimitado por tabuladores.
source-git-commit: 8a5c7309b5d4061b2e3241219d9bdb1521294535
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 74%

---


# Exportación del explorador

La exportación del explorador permite exportar los datos de clasificación a un archivo delimitado por tabuladores.

Administración > Importador de clasificaciones

El archivo del conjunto de datos es un archivo de datos delimitado por tabuladores (con la extensión de nombre de archivo .tab) compatible con la mayoría de las aplicaciones de hojas de cálculo.

>[!NOTE]
>Las exportaciones del explorador tienen un límite de 30 columnas.

## Descripciones de campos

| Elemento | Descripciones |
| --- | --- |
| Seleccionar grupo de informes | Selecciona el grupo de informes desde el que se desea exportar los datos del informe. |
| Conjunto de datos a clasificar | En el menú desplegable, seleccione el conjunto de datos que desea clasificar. |
| Seleccionar cantidad de filas | Especifica el número de filas de datos que debe exportarse.<ul><li>Seleccione **[!UICONTROL Todo]** para exportar todos los datos del informe (máximo 50 000 filas).</li><li>Seleccione **[!UICONTROL Limitar filas de datos a]** si desea indicar un número concreto de filas a descargar.</li></ul>Si desea descargar más de 50 000 filas de datos, utilice la opción de descarga mediante FTP. |
| Filtrar por fecha de recepción | Opcional. Filtra los datos por fecha de recepción. Debe especificarse el intervalo de fecha cuyos datos van a descargarse. |
| Aplicar filtro de datos | Opcional. Filtra el conjunto de datos por criterios de datos. Puede filtrarse la descarga para que incluya filas de datos que contienen un valor específico o valores de columna (clasificación) no asignados. Al aplicar filtros de datos deben tenerse en cuenta las siguientes circunstancias:<ul><li>Pueden utilizarse comodines para definir el filtro de datos. Utilice un asterisco para que coincida con cero o más caracteres y un signo de interrogación `?` para que coincida exactamente con un carácter. Utilice `?*` para hacer coincidir uno o más caracteres.</li><li>Por lo general, si se aplican ambos tipos de filtros de datos a una descarga, solo se descargan las filas que coinciden con ambas reglas. Pese a ello, se aplican las siguientes excepciones:<ul><li>Si Filas con columna vacía = Todas las columnas, se comprueba si todas las columnas, a excepción de la indicada en la primera regla, están vacías. Con esta excepción, nos aseguramos de que el sistema descargue todas las filas con una columna que coincida con la primera regla y que tenga también todas las demás columnas vacías.</li><li>Al descargar filas de datos basadas en columnas vacías, se comprueba si todas las columnas, a excepción de las indicadas en la primera regla, están vacías.</li><li>Si se especifica la misma columna en ambas reglas de filtro (es prácticamente imposible cumplir ambos criterios), se descargarán sólo las filas que coincidan con la primera regla.</li></ul></ul> |
| Filtro de datos | Opcional. Filtra los datos por datos de campaña. Únicamente pueden descargarse datos de campañas activas o seleccionar campañas que comenzarán (o finalizarán) en un intervalo de fecha específico.<br>**Importante**: Esta opción no está disponible para los grupos de informes habilitados para la nueva arquitectura de clasificación. |


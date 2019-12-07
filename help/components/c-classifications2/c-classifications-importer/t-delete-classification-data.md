---
description: Instrucciones sobre cómo eliminar o quitar datos de clasificación.
subtopic: Classifications
title: Eliminar datos de clasificación
topic: Admin tools
uuid: 5b1b0ac7-ee52-4fd8-b98e-25283595cf0c
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Eliminar datos de clasificación

A veces es necesario eliminar los datos de clasificación después de cargarlos. Utilice `~empty~` o `~deletekey~`, según lo que desee eliminar.

## Pasos para eliminar datos de clasificación

La eliminación de datos de clasificación implica la carga de un archivo de clasificación que contenga `~empty~` o `~deletekey~` en las celdas correspondientes.

1. Haga clic en **[!UICONTROL Administración]** &gt; **[!UICONTROL Importador de clasificaciones]**.
1. Haga clic en **[!UICONTROL Exportación del navegador]**.
1. Seleccione el grupo de informes y el conjunto de datos de los que deben eliminarse los datos de clasificación.
1. Ajuste la configuración opcional para filtrar los datos específicos que está buscando y haga clic en **[!UICONTROL Exportar archivo]**.
1. Una vez descargado el archivo, ábralo y reemplace los valores de clasificación por `~empty~` o `~deletekey~`.
1. Guarde el archivo como archivo de texto delimitado por tabuladores.
1. Haga clic en **[!UICONTROL Importar archivo]** y vuelva a cargar el archivo de clasificación guardado en Adobe Analytics.

## Eliminación de un valor de clasificación individual

Varias clasificaciones pueden pertenecer a la misma variable. Por ejemplo: puede tener dos clasificaciones diferentes de eVar1. Si solo desea eliminar un valor clasificado único, reemplace el valor de clasificación por `~empty~`. Por ejemplo:

| SKU de inventario (eVar8) | Nombre del inventario | Categoría de inventario |
| --- | --- | --- |
| 857467 | Suéter de cuello V | Ropa de mujer |
| 948203 | Pulsera de ángulo | Joyería |
| 174391 | Pantalones de cordoba blanca | `~empty~` |

El uso `~empty~` de la clasificación Categoría de inventario conserva los datos de la clasificación Nombre de inventario. El `~empty~` valor sólo elimina los datos de clasificación de esa celda.

## Eliminación de toda una fila de clasificación

Se utiliza `~deletekey~` en cualquier columna para eliminar toda la fila de clasificación. Por ejemplo:

| SKU de inventario (eVar8) | Nombre del inventario | Categoría de inventario |
| --- | --- | --- |
| 857467 | Suéter de cuello V | Ropa de mujer |
| 948203 | Pulsera de ángulo | Joyería |
| 174391 | Pantalones de cordoba blanca | `~deletekey~` |

El uso `~deletekey~` de la clasificación Categoría de inventario elimina todos los datos de clasificación para el valor clave `174391`. Es como si la fila nunca se hubiera clasificado.

## Problemas y sugerencias

* Si utiliza `~deletekey~`, sólo necesita uno por fila en un archivo de clasificación.
* `~empty~` y `~deletekey~` deben ser coincidencias *exactas* . No se permiten espacios ni mayúsculas.
* No puede eliminar valores dentro de la columna clave. Estos valores se pasan directamente a la variable y son permanentes.
* Si está eliminando un valor de clasificación que tiene subclasificaciones, estas subclasificaciones también se eliminan. Las clasificaciones no pueden existir sin los valores clave, que constituyen las clasificaciones principales de las subclasificaciones.
* Existe la posibilidad de eliminar los datos de subclasificación sin modificar las clasificaciones principales.

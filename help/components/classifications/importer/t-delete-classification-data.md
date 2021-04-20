---
description: Instrucciones sobre cómo eliminar o quitar datos de clasificación.
subtopic: Classifications
title: Eliminar datos de clasificación
feature: Admin Tools
uuid: 5b1b0ac7-ee52-4fd8-b98e-25283595cf0c
exl-id: 2b156e66-3090-4048-8192-a412320e3be3
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 100%

---

# Eliminar datos de clasificación

A veces es necesario eliminar los datos de clasificación después de cargarlos. Utilice `~empty~` o `~deletekey~`, según lo que desee eliminar.

## Pasos para eliminar los datos de clasificación

La eliminación de datos de clasificación implica la carga de un archivo de clasificación que contenga `~empty~` o `~deletekey~` en las celdas correspondientes.

1. Haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Importador de clasificaciones]**.
1. Haga clic en **[!UICONTROL Exportación del navegador]**.
1. Seleccione el grupo de informes y el conjunto de datos de los que deben eliminarse los datos de clasificación.
1. Ajuste la configuración opcional para filtrar los datos específicos que está buscando y haga clic en **[!UICONTROL Exportar archivo]**.
1. Una vez descargado el archivo, ábralo y reemplace los valores de clasificación por `~empty~` o `~deletekey~`.
1. Guarde el archivo como archivo de texto delimitado por tabuladores.
1. Haga clic en **[!UICONTROL Importar archivo]** y vuelva a cargar el archivo de clasificación guardado en Adobe Analytics.

## Eliminación de un valor de clasificación individual

Varias clasificaciones pueden pertenecer a la misma variable. Por ejemplo: puede tener dos clasificaciones diferentes de eVar1. Si solo desea eliminar un valor clasificado único, reemplace el valor de clasificación por `~empty~`. Por ejemplo:

| SKU de inventario (eVar8) | Nombre de inventario | Categoría de inventario |
| --- | --- | --- |
| 857467 | Suéter de cuello de pico | Ropa de mujer |
| 948203 | Tobillera | Joyería |
| 174391 | Pantalones de pana blancos | `~empty~` |

El uso de `~empty~` en la clasificación “Categoría de inventario” conserva los datos de la clasificación “Nombre de inventario”. El valor `~empty~` solo elimina los datos de clasificación de esa celda.

## Eliminación de toda una fila de clasificación

Se utiliza `~deletekey~` en cualquier columna para eliminar toda la fila de clasificación. Por ejemplo:

| SKU de inventario (eVar8) | Nombre de inventario | Categoría de inventario |
| --- | --- | --- |
| 857467 | Suéter de cuello de pico | Ropa de mujer |
| 948203 | Tobillera | Joyería |
| 174391 | Pantalones de pana blancos | `~deletekey~` |

El uso de `~deletekey~` en la clasificación “Categoría de inventario” elimina todos los datos de clasificación para el valor clave `174391`. Es como si la fila nunca se hubiera clasificado.

## Problemas y sugerencias

* Si utiliza `~deletekey~`, solo necesita 1 por fila en un archivo de clasificación.
* `~empty~` y `~deletekey~` deben coincidir de manera *exacta*. No se permiten espacios ni mayúsculas.
* No puede eliminar valores dentro de la columna clave. Estos valores se pasan directamente a la variable y son permanentes.
* Si se quita un valor de clasificación que contiene subclasificaciones, estas también se eliminan. Las clasificaciones no pueden existir sin los valores clave, que constituyen las clasificaciones principales de las subclasificaciones.
* Se pueden eliminar los datos de subclasificación sin modificar las clasificaciones principales.

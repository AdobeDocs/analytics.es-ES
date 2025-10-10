---
description: Aprenda a utilizar Microsoft Excel con funciones de Report Builder sin acceder a la interfaz de usuario de Report Builder.
title: Aprenda a utilizar Microsoft Excel con funciones de Report Builder
uuid: 5342cc4f-085d-4a2d-a498-38b00a3ef4d3
feature: Report Builder
role: User, Admin
exl-id: b412f2b5-affe-4297-af4b-85e8c6dfd257
source-git-commit: fcecc8a493852f5682fd7fbd5b9bb484a850922c
workflow-type: tm+mt
source-wordcount: '500'
ht-degree: 35%

---

# Uso de funciones de Report Builder con Microsoft Excel

{{legacy-arb}}

Puede utilizar funciones de Report Builder para acceder a la funcionalidad sin acceder a la interfaz de usuario de Report Builder.

Por ejemplo, para actualizar automáticamente las solicitudes de Report Builder con filtros de entrada basados en datos recuperados en Excel desde otros orígenes, utilice la función RefreshRequestsInCellsRange(..) de cadena. Todas las llamadas son asíncronas y se devuelven inmediatamente y no esperan a ejecutarse por completo.

**Requisitos**

* Se requiere Report Builder 5.0 (o posterior).

En la tabla siguiente se enumeran las funciones expuestas.

| Nombre de función | Tipo | Descripción |
|:---| --- | ---|
| AsyncRefreshAll() | string | Actualiza todas las solicitudes de Report Builder presentes en un libro. |
| AsyncRefreshRange(string rangeAddressInA1Format) | string | Actualiza todas las solicitudes de Report Builder presentes en la dirección especificada del intervalo de celdas (una expresión de cadena que representa un intervalo de celdas en formato A1, por ejemplo, &quot;Hoja1!A2:A10&quot;). |
| AsyncRefreshRangeAltTextParam() | string | Actualiza todas las solicitudes de Report Builder presentes en el intervalo de celdas especificado que pasan por el Texto alternativo de MS Form Control. |
| AsyncRefreshActiveWorksheet() | string | Actualiza todas las solicitudes de Report Builder presentes en el libro activo. |
| AsyncRefreshWorksheet(string worksheetName) | string | Actualiza todas las solicitudes de Report Builder presentes en el libro especificado (el nombre del libro tal y como aparece en la ficha). |
| AsyncRefreshWorksheetAltTextParam(); | string | Actualiza todas las solicitudes de Report Builder presentes en el libro concreto que se pasó por el Texto alternativo de MS Form Control. |
| String GetLastRunStatus() | string | Devuelve una cadena que describe el estado de la última ejecución. |

Para tener acceso a las funciones de Report Builder, vaya a **[!UICONTROL Fórmulas]** > **[!UICONTROL Insertar función]**. Utilice el campo de búsqueda para buscar una función o seleccione una categoría para enumerar las funciones de esa categoría.

![Captura de pantalla que muestra la ventana Insertar función con la lista de categorías expandida.](assets/arb_functions.png)

## Ejemplo {#section_034311081C8D4D7AA9275C1435A087CD}

El ejemplo siguiente muestra *Si el valor de la celda P5 es texto o está en blanco, actualice el rango de la celda P9*.

```
=IF(OR(ISTEXT(P5),ISBLANK(P5)),AsyncRefreshRange("P9"),"")
```

## Uso de funciones de Report Builder con control de formato {#section_26123090B5BD49748C8D8ED7A1C5ED84}

Puede asignar una macro a un control que haya creado y ese control puede ser una función que actualice una solicitud de libro. Por ejemplo, la función AsyncRefreshActiveWorksheet actualizará todas las solicitudes de un libro. Sin embargo, a veces es posible que solo desee actualizar determinadas solicitudes.

1. Establezca el parámetro de macro.
1. Haga clic con el botón derecho en el control y seleccione **[!UICONTROL Asignar macro]**.
1. Introduzca el nombre de la función de Report Builder (sin parámetros ni paréntesis).

![Captura de pantalla que muestra la ventana Asignar macro.](assets/assign_macro.png)

## Pasar parámetros a funciones de Report Builder mediante el control de formato {#section_ECCA1F4990D244619DFD79138064CEF0}

Se pueden utilizar dos funciones que toman un parámetro con Control de formato. Debe usar el campo **Texto alternativo:**:

* AsyncRefreshRange(string rangeAddressInA1Format)
* AsyncRefreshWorksheet(string worksheetName)

Para pasar parámetros a funciones de Report Builder mediante el control de formato

1. Haga clic con el botón derecho del ratón en el control y seleccione **[!UICONTROL Formato de control]**.

   ![Captura de pantalla que muestra el control de formato seleccionado.](assets/format_control.png)

1. Haga clic en la ficha **[!UICONTROL Texto alternativo]**.

   ![Captura de pantalla que muestra la pestaña Texto alternativo y el campo Texto alternativo:.](assets/alt_text.png)

1. En **[!UICONTROL Texto alternativo]**, introduzca el rango de celdas que desee actualizar.
1. Abra la lista de parámetros de Report Builder en **[!UICONTROL Fórmulas]** > **[!UICONTROL Insertar función]**> **[!UICONTROL Adobe.ReportBuilder.Bridge]**.

1. Elija una de las dos opciones que acaban con AltTextParam y haga clic en **[!UICONTROL Aceptar]**.

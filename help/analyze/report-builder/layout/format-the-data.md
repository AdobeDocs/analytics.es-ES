---
description: Además de las opciones de formato de celda estándar disponibles mediante la función de Excel Formato > Celdas (Ctrl+1), es posible aplicar un formato limitado a los rangos de celdas con Report Builder. Estas opciones de formato dependen de la métrica seleccionada.
title: Dar formato a las fechas
topic: Report builder
uuid: 5211db30-07b3-4413-97c3-e40e6ff223cd
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Dar formato a las fechas

Además de las opciones de formato de celda estándar disponibles mediante la función de Excel Formato > Celdas (Ctrl+1), es posible aplicar un formato limitado a los rangos de celdas con Report Builder. Estas opciones de formato dependen de la métrica seleccionada.

After you [add dimensions](/help/analyze/report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md) to the Row Labels grid, click **[!UICONTROL Format]**.

In the **[!UICONTROL Format]** menu, click **[!UICONTROL Custom Format]** to apply customized formats for dates similar to the prepend and postpend feature. Por ejemplo, puede introducir texto que siempre aparezca tras la fecha (por ejemplo, A.D., B.C.E., A.H., etc.). Puede agregar texto antes de la fecha, como [!UICONTROL Start Date] y [!UICONTROL Start and End Date]. Asimismo, puede crear una expresión de fecha personalizada desde las abreviaciones de día, mes y año y emplear un separador personalizado entre las partes de la fecha. Todos los formatos de fecha deben constar de tres abreviaciones únicamente incluidas entre corchetes.

The following table describes how you can use date abbreviations in the [!UICONTROL Custom Format] field:

| Abreviación | Significado | Ejemplo   Se utiliza el miércoles, 14 de marzo de 2012. |
|--- |--- |--- |
| MM/dd/yyy | Fecha numérica completa | 03/14/2012 |
| M | Número de mes | 3 |
| MM | Número de mes con margen 0 para meses &lt; 10 | 03 |
| MMM | Nombre corto del mes | Mar |
| MMMM | Nombre largo del mes | Marzo de |
| D | Nombre largo de la fecha | Miércoles, 14 de marzo, 2012 |
| d | Número de día | 14 |
| dd | Número de día con margen 0 para días &lt; 10 | 01 - 09 |
| ddd | Nombre corto del día | Mié |
| dddd | Nombre largo del día | Miércoles |
| yy | Año de 2 dígitos | 10 |
| yyyy | Año de 4 dígitos | 2012 |

---
description: Además de las opciones de formato de celda estándar disponibles mediante la función de Excel Formato > Celdas (Ctrl+1), es posible aplicar un formato limitado a los rangos de celdas con el Creador de informes. Estas opciones de formato dependen de la métrica seleccionada.
seo-description: Además de las opciones de formato de celda estándar disponibles mediante la función de Excel Formato > Celdas (Ctrl+1), es posible aplicar un formato limitado a los rangos de celdas con el Creador de informes. Estas opciones de formato dependen de la métrica seleccionada.
seo-title: Dar formato a la fecha
solution: Analytics
title: Dar formato a la fecha
topic: Creador de informes
uuid: 5211 db 30-07 b 3-4413-97 c 3-e 40 e 6 ff 223 cd
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Dar formato a la fecha

Además de las opciones de formato de celda estándar disponibles mediante la función de Excel Formato &gt; Celdas (Ctrl+1), es posible aplicar un formato limitado a los rangos de celdas con el Creador de informes. Estas opciones de formato dependen de la métrica seleccionada.

After you [add dimensions](../../../analyze/report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md#task_E3F520C020F64C5A96DC5C96FEF71FC4) to the Row Labels grid, click **[!UICONTROL Format]**.

En el menú **[!UICONTROL Formato]**, haga clic en **Formato personalizado]para aplicar formatos personalizados a fechas de forma similar a la función de anteponer y posponer.[!UICONTROL ** Por ejemplo, puede introducir texto que siempre aparezca tras la fecha (por ejemplo, A.D., B.C.E., A.H., etc.). Puede añadir texto antes de la fecha; por ejemplo, [!UICONTROL Fecha de inicio] y [!UICONTROL Fecha de inicio y finalización]. Asimismo, puede crear una expresión de fecha personalizada desde las abreviaciones de día, mes y año y emplear un separador personalizado entre las partes de la fecha. Todos los formatos de fecha deben constar de tres abreviaciones únicamente incluidas entre corchetes.

En la siguiente tabla se describe cómo se pueden utilizar las abreviaciones de fecha en el campo [!UICONTROL Formato personalizado]:

| Abreviación | Significado | Ejemplo   Se utiliza el miércoles, 14 de marzo de 2012. |
|--- |--- |--- |
| MM/dd/yyy | Fecha numérica completa | 03/14/2012 |
| M | Número de mes | 3 |
| MM | Número de mes con margen 0 para meses &lt; 10 | 03 |
| MMM | Nombre corto del mes | Mar |
| MMMM | Nombre largo del mes | marzo |
| D | Nombre largo de la fecha | Miércoles, 14 de marzo, 2012  |
| d | Número de día | 14 |
| dd | Número de día con margen 0 para días &lt; 10 | 01 - 09 |
| ddd | Nombre corto del día | Mié |
| dddd | Nombre largo del día | Miércoles |
| yy | Año de 2 dígitos | 10 |
| yyyy | Año de 4 dígitos | 2012 |
---
description: Aprenda a aplicar formato estándar y limitado a rangos de celdas.
title: Formato de la fecha en Report Builder
uuid: 5211db30-07b3-4413-97c3-e40e6ff223cd
feature: Report Builder
role: User, Admin
exl-id: 9b251b09-9156-40b5-8e1f-fb6594a25c26
source-git-commit: fcecc8a493852f5682fd7fbd5b9bb484a850922c
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 81%

---

# Dar formato a las fechas

{{legacy-arb}}

Además de las opciones de formato de celda estándar disponibles mediante la función de Excel Formato > Celdas (Ctrl+1), puede aplicar formato limitado a los rangos de celdas con Report Builder. Estas opciones de formato dependen de la métrica seleccionada.

Después de [añadir dimensiones](/help/analyze/legacy-report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md) a la cuadrícula Rótulos de fila, haga clic en **[!UICONTROL Formato]**.

En el menú **[!UICONTROL Formato]**, haga clic en **[!UICONTROL Formato personalizado]** para aplicar formatos personalizados a fechas de forma similar a la función de anteponer y posponer. Por ejemplo, puede introducir texto que siempre aparezca tras la fecha (por ejemplo, A.D., B.C.E., A.H., etc.). Puede añadir texto antes de la fecha; por ejemplo, [!UICONTROL Fecha de inicio] y [!UICONTROL Fecha de inicio y finalización]. Asimismo, puede crear una expresión de fecha personalizada desde las abreviaciones de día, mes y año y emplear un separador personalizado entre las partes de la fecha. Todos los formatos de fecha deben constar de tres abreviaciones únicamente incluidas entre corchetes.

En la siguiente tabla se describe cómo se pueden utilizar las abreviaciones de fecha en el campo [!UICONTROL Formato personalizado]:

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

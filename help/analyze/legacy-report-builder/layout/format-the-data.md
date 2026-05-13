---
description: Aprenda a aplicar formato estándar y limitado a rangos de celdas.
title: Formato de la fecha en Report Builder
uuid: 5211db30-07b3-4413-97c3-e40e6ff223cd
feature: Report Builder
role: User, Admin
exl-id: 9b251b09-9156-40b5-8e1f-fb6594a25c26
TQID: https://experienceleague.adobe.com/8FuosvmSvi-bRNaG5QbwUExuDffOIXbrkuiQLh0NZXM
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 271
ht-degree: 20%

---

# Dar formato a las fechas

{{legacy-arb}}

Además de las opciones de formato de celda estándar disponibles mediante la función de Excel Formato > Celdas (Ctrl+1), puede aplicar formato limitado a los rangos de celdas con Report Builder. Estas opciones de formato dependen de la métrica que haya elegido.

Después de [añadir dimensiones](/help/analyze/legacy-report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md) a la cuadrícula Rótulos de fila, haga clic en **[!UICONTROL Formato]**.

En el menú **[!UICONTROL Formato]**, haga clic en **[!UICONTROL Formato personalizado]** para aplicar formatos personalizados a fechas de forma similar a la función de anteponer y posponer. Por ejemplo, puede introducir texto que siempre aparezca después de la fecha (como A.D. B.C.E. A.H., etc.). Puede agregar texto antes de la fecha, como [!UICONTROL Fecha de inicio] y [!UICONTROL Fecha de inicio y finalización]. Además, puede construir una expresión de fecha personalizada a partir de las abreviaciones de día, mes y año, y utilizar un separador personalizado entre partes de la fecha. Todos los formatos de fecha deben constar de tres abreviaturas incluidas únicamente entre corchetes.

En la tabla siguiente se describe cómo usar abreviaturas de fecha en el campo [!UICONTROL Formato personalizado]:

| Abreviatura | Significado | Ejemplo con miércoles, 14 de marzo de 2012 |
|--- |--- |--- |
| dd/MM/aaaa | Fecha numérica completa | 03/14/2012 |
| M | Número de meses | 3 |
| MM | Número de meses con relleno 0 para meses &lt; 10 | 03 |
| MMM | Nombre corto del mes | Mar. |
| MMMM | Nombre largo del mes | Marzo de |
| D | Nombre largo de la fecha | Miércoles, 14 de marzo, 2012 |
| d | Número de días | 14 |
| dd | Número de días con relleno 0 para días &lt; 10 | 01 - 09 |
| ddd | Nombre corto del día | Mié |
| dddd | Nombre largo del día | Miércoles |
| aa | El año expresado con 2 dígitos | 10 |
| yyyy | Año completo de 4 dígitos | 2012 |

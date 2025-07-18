---
title: Totales de métricas calculadas
description: Obtenga información sobre los totales de métricas calculadas en Analysis Workspace
feature: Calculated Metrics
exl-id: 3e4429de-3e0c-49a5-b32c-3a4d24a29816
source-git-commit: bf58da2a39e8b9fd298356f23a9bf8f6c394d3de
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 94%

---

# Totales de métricas calculadas

Cuando se ven datos en Analysis Workspace, en la mayoría de los casos se muestran los totales de métricas calculadas. En algunos casos, no es posible proporcionar un total, como cuando las filas del informe tienen un formato mixto (por ejemplo, decimal y monetario).

Cuando se muestran los totales, a menudo se calculan en el lado del servidor, lo que significa que el total anula la duplicación de métricas como visitas o visitantes. En determinadas circunstancias, las métricas calculadas se generan en el lado del cliente sumando las filas de la tabla, lo que significa que el total no anula la duplicación de métricas como visitas o visitantes. Esto ocurre:

* Cuando se utilizan [filas estáticas](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md) are en tablas de forma libre y la opción **[!UICONTROL Mostrar como la suma de las filas actuales]** (predeterminada) se encuentra seleccionada.
* En la [Visualización de anillo](/help/analyze/analysis-workspace/visualizations/donut.md), de modo que los números suman 100%.

Para obtener más información sobre los totales en Analysis Workspace, visite [Totales de Workspace](/help/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.md#static-row-total).

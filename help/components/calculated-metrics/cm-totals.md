---
title: Totales de métricas calculadas
description: Obtenga información sobre los totales de métricas calculadas en Analysis Workspace
feature: Calculated Metrics
exl-id: 3e4429de-3e0c-49a5-b32c-3a4d24a29816
TQID: https://experienceleague.adobe.com/3UJF1Hl3nLqjYAiQuvcE4Jpq26MaTgeba5BmnVfvEps
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: dcae653e-62c6-4cc8-84e6-ee110b848296id: e318d41c-1d01-4c1e-9b18-1f61d435ceeeid: ef60b66e-5984-4336-ba72-6d978b1b6f87id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 149
ht-degree: 94%

---

# Totales de métricas calculadas

Cuando se ven datos en Analysis Workspace, en la mayoría de los casos se muestran los totales de métricas calculadas. En algunos casos, no es posible proporcionar un total, como cuando las filas del informe tienen un formato mixto (por ejemplo, decimal y monetario).

Cuando se muestran los totales, a menudo se calculan en el lado del servidor, lo que significa que el total anula la duplicación de métricas como visitas o visitantes. En determinadas circunstancias, las métricas calculadas se generan en el lado del cliente sumando las filas de la tabla, lo que significa que el total no anula la duplicación de métricas como visitas o visitantes. Esto ocurre:

* Cuando se utilizan [filas estáticas](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md) are en tablas de forma libre y la opción **[!UICONTROL Mostrar como la suma de las filas actuales]** (predeterminada) se encuentra seleccionada.
* En la [Visualización de anillo](/help/analyze/analysis-workspace/visualizations/donut.md), de modo que los números suman 100%.

Para obtener más información sobre los totales en Analysis Workspace, visite [Totales de Workspace](/help/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.md#static-row-total).

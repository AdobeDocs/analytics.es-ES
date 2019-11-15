---
title: Totales de métricas calculadas
description: Descubra cómo difieren los totales de las métricas calculadas en las herramientas de Analytics
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Totales de métricas calculadas

La forma en que se muestran los totales de métricas calculadas difiere entre [!DNL Reports & Analytics] y [!DNL Analysis Workspace]. Esta sección explica las diferencias.

## Totales de métricas calculadas en [!DNL Reports & Analytics]

Cuando ve los informes en [!DNL Reports & Analytics], las métricas calculadas siempre se muestran `n/a` debajo del total. Dado que todas las métricas calculadas están definidas por el usuario, existen muchas circunstancias en las que este total no tiene sentido. Consideremos el siguiente ejemplo:

Su organización ha creado la métrica calculada `orders` / `visits` para determinar el porcentaje de visitas que compraron algo en el sitio. Si ha introducido esta métrica en un informe de productos, varios productos se atribuyen a un único pedido. Además, varios productos se atribuyen a una sola visita. Si en este informe se incluyó un total de métrica calculada, se plantean las siguientes preguntas:

| Pregunta | Respuesta |
|---|---|
| ¿Tiene sentido sumar los elementos de línea? | No lo hace, ya que se pueden incluir varios productos en un único pedido y en una sola visita se pueden incluir varios productos. Si se agregaran los artículos de línea, los pedidos totales y las visitas totales no coincidirían con los pedidos totales reales y las visitas totales. |
| ¿Tiene sentido realizar pedidos totales y visitas totales? | No, ya que el total no coincide con la suma de los elementos de línea individuales. Además, el total de pedidos y el total de visitas son métricas calculadas por separado. |

Dado que no hay ningún método lógico y concreto para determinar si una métrica calculada tiene sentido en los informes, el total de la métrica se omite por completo. Si desea obtener un total general, puede realizar una de las siguientes acciones:

* Cree una métrica calculada que incluya las versiones totales de las métricas que desea incluir.
* Cree un informe de extracción de datos, que se puede programar.
* Create a data request within [!DNL ReportBuilder].
* Usar [!DNL Analysis Workspace] (ver abajo).

## Totales de métricas calculadas en [!DNL Analysis Workspace]

Cuando se ven datos en Analysis Workspace, en la mayoría de los casos se muestran los totales de métricas calculadas. En algunos casos, no es posible proporcionar un total, por ejemplo, cuando las filas del informe tienen un formato mixto (por ejemplo, decimal y monetario).

Cuando se muestran los totales, a menudo se calculan en el lado del servidor, lo que significa que el total anula la duplicación de métricas como visitas o visitantes. En determinadas circunstancias, las métricas calculadas se generan en el lado del cliente sumando las filas de la tabla, lo que significa que el total no anula la duplicación de métricas como visitas o visitantes. Esto ocurre:

* Cuando se utilizan filas [](/help/analyze/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.md) estáticas en tablas improvisadas y se selecciona la opción **[!UICONTROL Mostrar como suma de filas]** actuales (predeterminada).
* En la visualización [de anillo](/help/analyze/analysis-workspace/visualizations/donut.md), de modo que los números suman 100%.

---
title: Totales de métricas calculadas
seo-title: Totales de métricas calculadas
description: Descubra cómo los totales de las métricas calculadas difieren en las herramientas de Analytics
seo-description: Cálculo de los totales de las métricas calculadas
translation-type: tm+mt
source-git-commit: 658925799c530b46ff7b56d5d0685af6d9fef1b8

---


# Totales de métricas calculadas

La manera en que se muestran los totales de métricas calculadas difiere entre [!DNL Reports & Analytics] y [!DNL Analysis Workspace]. Esta sección explica las diferencias.

## Totales de métricas calculadas en [!DNL Reports & Analytics]

Al ver los informes en [!DNL Reports & Analytics], las métricas calculadas siempre se muestran `n/a` debajo del total. Dado que todas las métricas calculadas están definidas por el usuario, existen muchas circunstancias en las que este total no tiene sentido. Consideremos el siguiente ejemplo:

Su organización ha creado la métrica `orders` calculada/ `visits` para determinar el porcentaje de visitas que compraron algo en el sitio. Si ha traído esta métrica a un informe de productos, varios productos se atribuyen a un único pedido. Además, varios productos se atribuyen a una sola visita. Si se ha incluido un total de métrica calculada en este informe, surgen las siguientes preguntas:

| Pregunta | Respuesta |
|---|---|
| ¿Tiene sentido sumar los elementos de línea? | No, ya que varios productos se pueden incluir en un único pedido y se pueden incluir varios productos en una sola visita. Si se agregaron los elementos de línea, los pedidos totales y el total de visitas no coincidirán con los pedidos totales y las visitas totales. |
| ¿Tiene sentido realizar pedidos totales y visitas totales? | No, ya que el total no coincide con la suma de los elementos de línea individuales. Además, los pedidos totales y las visitas totales son métricas calculadas por separado. |

Dado que no hay ningún método lógico y específico para determinar si una métrica calculada tiene sentido en los informes, el total de la métrica se omite por completo. Si desea obtener un total general, puede realizar una de las siguientes acciones:

* Cree una métrica calculada que incluya las versiones totales de las métricas que desee incluir.
* Crear un informe de extracción de datos, que se puede programar.
* Create a data request within [!DNL ReportBuilder].
* Uso [!DNL Analysis Workspace] (véase más abajo).

## Totales de métricas calculadas en [!DNL Analysis Workspace]

Cuando se ven los datos en Analysis Workspace, los totales de métricas calculadas se muestran en la mayoría de los casos. En algunos casos no es posible proporcionar un total, como cuando las filas del informe tienen un formato mixto (por ejemplo, decimal y moneda).

Cuando se muestran los totales, se suelen calcular en el servidor, lo que significa que el total de desduplicación de métricas como visitas o visitantes. En determinadas circunstancias, las métricas calculadas se generan del lado del cliente sumándose en filas de la tabla, lo que significa que el total no elimina las duplicaciones de métricas como visitas o visitantes. Esto sucede:

* Cuando [se utilizan filas](/help/analyze/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.md) estáticas en tablas improvisadas y se selecciona **[!UICONTROL la opción Mostrar como suma de filas]** actuales (predeterminada).
* En la visualización [Anillo](/help/analyze/analysis-workspace/visualizations/donut.md), de modo que los números suman el 100%.

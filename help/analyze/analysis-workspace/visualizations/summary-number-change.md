---
description: Utilice las visualizaciones Número y cambio de resumen para mostrar puntos de datos importantes en un proyecto.
title: Número de resumen y cambio de resumen
uuid: 177c1b89-6d98-473d-8447-6b4cdc479565
feature: Visualizations
role: User, Admin
exl-id: d6a08201-ca3a-48ff-983a-3ec6b989deda
source-git-commit: c0855c6bed6a9762c0440e1a8e004ee11020808e
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 93%

---

# [!UICONTROL Número de resumen] y [!UICONTROL Cambio de resumen]

*Este artículo documenta la visualización de número de resumen y cambio de resumen en **Adobe Analytics**.<br/>Ver [Número de resumen y cambio de resumen](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/summary-number-change) para la versión de **Customer Journey Analytics**de este artículo.*

Aquí tiene un vídeo sobre estas dos visualizaciones:

>[!VIDEO](https://video.tv.adobe.com/v/335564/?quality=12)

## Visualización [!UICONTROL Número de resumen] {#summary-number}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_summarynumber_button"
>title="Número de resumen"
>abstract="Cree una visualización que muestre los totales y subtotales."

<!-- markdownlint-enable MD034 -->

Utilice la visualización [!UICONTROL Número de resumen] para resaltar un número elevado que sea importante en un proyecto. Esta visualización se comporta de las siguientes maneras:

* Selecciona el total de la columna en caso de que no se haya seleccionado ninguna celda.
* Si se selecciona una única celda, se muestra el resumen de esta.
* Si se selecciona más de una celda, se muestra la primera celda seleccionada.
* Si se selecciona la columna, se usa el valor de la primera celda de la columna.

Haga clic en el icono de engranaje de **Configuración de la visualización** situado en la parte superior derecha para configurar la configuración de Número de resumen:

| Configuración | Definición |
|--- |--- |
| [!UICONTROL Porcentajes] | Muestra porcentajes en lugar de números en bruto. |
| [!UICONTROL Leyenda visible] | Muestra información acerca de la métrica mostrada. |
| [!UICONTROL Valor abreviado] | Elija abreviar los valores y mostrar hasta 3 decimales. |
| [!UICONTROL Valor de resumen por] | Elija mostrar el máximo, el mínimo, la media, la mediana o la suma para una selección de datos. |

## Visualización [!UICONTROL Cambio de resumen] {#summary-change}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_summarychange_button"
>title="Cambio de resumen"
>abstract="Cree una visualización que muestre el delta (cambio) entre dos números"

<!-- markdownlint-enable MD034 -->

Utilice la visualización [!UICONTROL Cambio de resumen] para mostrar el delta (cambio) entre dos números. El color verde y rojo del [!UICONTROL Cambio de resumen] se puede controlar mediante la [polaridad de evento personalizado](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) o mediante la opción [Mostrar tendencia ascendente como](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html?lang=es) de una métrica calculada.

Esta visualización se comporta de las siguientes maneras:

* Si no se selecciona ninguna celda, compara los valores de las dos primeras celdas de la columna.
* Si se selecciona una celda, muestra 0, ya que compara el valor de celda con ella misma.
* Si se seleccionan dos celdas, la primera celda seleccionada se toma como numerador y la segunda como denominador.
* Si se seleccionan más de dos celdas, solo se tienen en cuenta las dos primeras para la comparación.
* Si se selecciona un intervalo de celdas, se compara la primera celda con la última seleccionada en el intervalo.
* Si se selecciona la columna, se compara el primer valor consigo mismo, lo que da como resultado un cambio de 0.


![](assets/summary-change.png)


Haga clic en el icono de engranaje de **Configuración de la visualización** situado en la parte superior derecha para configurar la configuración de Cambio de resumen:

| Configuración | Definición |
| --- | --- |
| [!UICONTROL Porcentajes] | Muestra porcentajes en lugar de números en bruto. |
| [!UICONTROL Leyenda visible] | Muestra información acerca de la métrica mostrada. |
| [!UICONTROL Mostrar cambio de porcentaje] | Muestra el cambio porcentual entre los 2 números. |
| [!UICONTROL Mostrar diferencia en bruto] | Muestra la diferencia en bruto entre los 2 números. También puede abreviar valores y mostrar hasta 3 decimales con esta opción. |

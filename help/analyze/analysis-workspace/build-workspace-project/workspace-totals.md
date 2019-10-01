---
description: Cómo se calculan los totales de Workspace.
seo-description: Obtenga información sobre cómo se calculan los totales de Workspace.
seo-title: Cómo se calculan los totales de Workspace.
title: Totales del espacio de trabajo
translation-type: tm+mt
source-git-commit: b2e76715a2bab0931b1ddf8c612c29eea530ce6c

---


# Totales del espacio de trabajo

En las tablas improvisadas, aparece una fila total en cada nivel de desglose y puede mostrar dos totales:

* **[!UICONTROL Total]** general (número 'sin' gris): este total representa todas las visitas recopiladas, a veces denominadas 'total del grupo de informes'. Cuando se aplica un segmento en el nivel de panel o en la tabla improvisada, este total se ajusta para reflejar todas las visitas que coincidan con los criterios del segmento.
* **[!UICONTROL Total]** de tabla (número negro): este total suele ser igual o un subconjunto del [!UICONTROL total]total general. Refleja cualquier filtro de tabla aplicado en la tabla improvisada, incluida la opción [!UICONTROL Incluir ninguno] .

![](assets/total-row.png)

## Mostrar configuración total

En Configuración **** de columna, hay opciones para **[!UICONTROL Mostrar totales]** y **[!UICONTROL Mostrar total]** general. Si esta configuración no está marcada, los totales se eliminarán de la tabla. Esto puede ser deseable en casos en los que los totales no tengan sentido, por ejemplo, en ciertos escenarios [de métricas](https://docs.adobe.com/content/help/en/analytics/components/calculated-metrics/calcmetrics-reference/cm-totals.html)calculadas.

![](assets/column-settings-total.png)

## Configuración total de fila estática

[Los totales de filas](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.html) estáticas se comportan de forma diferente y se controlan en Configuración **[!UICONTROL de fila]**.

* **[!UICONTROL Mostrar la suma de las filas actuales como el total]** : muestra una suma del lado del cliente de las filas de la tabla, lo que significa que el total **no eliminará** las métricas duplicadas como visitas o visitantes.
* **[!UICONTROL Show Grand Total - this shows a server-side sum, which means the total will de-duplicate metrics like visits or visitors.]**

![](assets/static-rows.png)

## Preguntas frecuentes

| Questions | Respuesta |
|---|---|
| Which 'total' are the gray column percentages based on? | This depends on the Percentages setting selection under Row Settings:********<ul><li>Calcular porcentajes por columna: Esta es la configuración predeterminada. Percentages will be based on the Table Total.</li><li>Calculate percentages by row - Percentages will be based on the Grand Total.</li></ul> |
| How does the Include Unspecified (None) setting impact totals?**** | Si la opción **[!UICONTROL Incluir no especificado (Ninguno)]** está desactivada, la fila Ninguno/No especificado se eliminará de la tabla, el Total de tabla y se aplicará a cualquier métrica calculada que utilice tipos de métrica ['Total'](https://docs.adobe.com/content/help/en/analytics/components/calculated-metrics/calcmetric-workflow/m-metric-type-alloc.html) |
| When custom table filters are applied to a freeform table, do all of my calculated metrics and conditional formatting account for the filter? | Not currently. **[!UICONTROL Include Unspecified (None) will be accounted for, but custom table filters will not impact the following:]**<ul><li>The column max/min range that conditional formatting uses will look across all data.</li><li>Calculated metrics that leverage **[!UICONTROL Grand Total]** metric types.</li><li>Métricas calculadas con funciones que calculan entre filas en una tabla improvisada, por ejemplo: Suma de columna, Máximo de columna, Mínimo de columna, Recuento, Media, Mediana, Percentil, Cuartil, Recuento de filas, Desviación estándar, Variación, Acumulativo, Promedio Acumulado, Variantes de regresión, Puntuación T, Prueba T, Puntuación Z, Prueba Z.</li></ul> |
| In Calculated Metrics, what does the **[!UICONTROL Grand Total]** metric type reflect? | **[!UICONTROL Grand Total continues to refer to the Grand Total, and does not reflect filters applied to a table or the Table Total.]********** |
| What total is shown when data is either copied and pasted from a freeform table or downloaded via CSV? | La fila total reflejará únicamente el total **[!UICONTROL de la]** tabla y respetará la columna **[!UICONTROL Mostrar totales]** . |


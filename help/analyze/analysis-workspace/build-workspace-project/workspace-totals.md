---
description: Cómo se calculan los totales de Workspace.
seo-description: Obtenga información sobre cómo se calculan los totales de Workspace.
seo-title: Cómo se calculan los totales de Workspace.
title: Totales del espacio de trabajo
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

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
* **[!UICONTROL Mostrar total]** general: muestra una suma del lado del servidor, lo que significa que el total anulará la duplicación de métricas como visitas o visitantes.

![](assets/static-rows.png)

## Preguntas frecuentes

| Preguntas | Respuesta |
|---|---|
| ¿En qué 'total' se basan los porcentajes de la columna gris? | Esto depende de la selección de configuración de **[!UICONTROL porcentajes]** en Configuración de **[!UICONTROL fila]**:<ul><li>Calcular porcentajes por columna: Esta es la configuración predeterminada. Los porcentajes se basarán en el total de la tabla.</li><li>Calcular porcentajes por fila: los porcentajes se basarán en el total general.</li></ul> |
| ¿Cómo afecta el ajuste **[!UICONTROL Incluir no especificado (Ninguno)]** a los totales? | Si la opción **[!UICONTROL Incluir no especificado (Ninguno)]** está desactivada, la fila Ninguno/No especificado se eliminará de la tabla, el Total de tabla y se aplicará a cualquier métrica calculada que utilice tipos de métrica ['Total'](https://docs.adobe.com/content/help/en/analytics/components/calculated-metrics/calcmetric-workflow/m-metric-type-alloc.html) |
| Cuando se aplican filtros de tabla personalizados a una tabla improvisada, ¿tienen en cuenta todas mis métricas calculadas y el formato condicional para el filtro? | Actualmente no. **[!UICONTROL Incluir no especificado (ninguno)]** se contabilizará, pero los filtros de tabla personalizados no afectarán a lo siguiente:<ul><li>El rango máximo/mínimo de columna que utiliza el formato condicional se verá en todos los datos.</li><li>Métricas calculadas que aprovechan los tipos de métricas **[!UICONTROL Total]** general.</li><li>Métricas calculadas con funciones que calculan entre filas en una tabla improvisada, por ejemplo: Suma de columna, Máximo de columna, Mínimo de columna, Recuento, Media, Mediana, Percentil, Cuartil, Recuento de filas, Desviación estándar, Variación, Acumulativo, Promedio Acumulado, Variantes de regresión, Puntuación T, Prueba T, Puntuación Z, Prueba Z.</li></ul> |
| En Métricas calculadas, ¿qué refleja el tipo de métrica Total **[!UICONTROL general]** ? | **[!UICONTROL Total]** general sigue haciendo referencia al Total **[!UICONTROL general]** y no refleja los filtros aplicados a una tabla o al Total **[!UICONTROL de]** tabla. |
| ¿Qué total se muestra cuando los datos se copian y pegan desde una tabla improvisada o se descargan mediante CSV? | La fila total reflejará únicamente el total **[!UICONTROL de la]** tabla y respetará la columna **[!UICONTROL Mostrar totales]** . |


---
description: 'null'
title: Número de resumen y cambio de resumen
uuid: 177c1b89-6d98-473d-8447-6b4cdc479565
translation-type: tm+mt
source-git-commit: 6eda9e3e5bd450213253a8181042c24c318c0300

---


# Número de resumen y cambio de resumen

## Visualización Número de resumen

* Selecciona el total de la columna si no hay ninguna celda seleccionada.
* Si se selecciona una sola celda, se muestra el resumen de la misma.
* Si se selecciona más de una celda, se muestra la primera celda seleccionada.
* Si la columna está seleccionada, selecciona el primer valor de celda de la columna.

![](assets/summary-number.png)

## Visualización Cambio de resumen

* Si no hay ninguna celda seleccionada, compara los dos primeros valores de celda de la columna.
* Si se selecciona una celda, muestra 0, porque compara el valor de la celda con él mismo.
* Si se seleccionan dos celdas, la primera celda seleccionada se toma como numerador y la segunda como denominador.
* Si se seleccionan más de dos celdas, solo se consideran las dos primeras para la comparación.
* Si se selecciona un rango de celdas, se compara la primera con la última celda seleccionada en el rango.
* Si la columna está seleccionada, compara el primer valor con sí mismo, lo que muestra un cambio de 0.
* El color verde y rojo del cambio de resumen se puede controlar mediante:
   * [Polaridad](https://marketing.adobe.com/resources/help/es_ES/reference/success_event.html)de evento personalizada.
   * La opción [Mostrar tendencia ascendente como](https://marketing.adobe.com/resources/help/es_ES/analytics/calcmetrics/cm_build_metrics.html) de una métrica calculada.

## Configuración de cambio de resumen {#section_2581AC0107634FB4990AB8347E5897AA}

Haga clic en el icono de engranaje situado junto a la visualización para configurar los ajustes de Resumen:

| Configuración | Definición |
|--- |--- |
| Porcentajes | Utilice porcentajes en lugar de números sin procesar. |
| Leyenda visible | Muestra las métricas utilizadas. |
| Opciones de número de resumen: Valor abreviado | Puede elegir entre 0 y 3 decimales para valores abreviados. |
| Opciones de cambio de resumen: Mostrar cambio de porcentaje | Muestra el cambio, en porcentaje, entre los 2 números. |
| Opciones de cambio de resumen: Mostrar diferencia sin procesar | Muestra la diferencia sin procesar entre los 2 números. |

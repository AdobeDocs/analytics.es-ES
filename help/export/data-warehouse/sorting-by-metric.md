---
description: Proporciona informes de desgloses clasificados en Data Warehouse, ordenados por el valor de métrica descendente.
title: Ordenar por métrica
uuid: 07da2607-b3fd-463b-90d4-6884a93c7e25
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Ordenar por métrica

Proporciona informes de desgloses clasificados en Data Warehouse, ordenados por el valor de métrica descendente.

La ordenación por métrica permite interpretar más fácilmente los informes de Data Warehouse, así como compararlos más fácilmente con otras vistas de informes de desgloses de Analytics.

A continuación se muestra cómo al habilitar la opción "Orden de las métricas" se reordenarán las filas de un informe de Data Warehouse.

Los informes del Data Warehouse se pueden organizar con "Orden de las métricas", en función de cómo se configure la granularidad de la fecha, las dimensiones de informes o las métricas y de si la opción "Máximo de filas" está establecida:

* **Diseño 1**: los elementos de línea se ordenan en el orden de diccionario (valor predeterminado). Si la opción "Máximo de filas" está establecida, solo se proporcionan las primeras N filas en el informe.
* **Diseño 2**: el Data Warehouse aplica una ordenación métrica sobre todas las filas del informe. Las conexiones del primer valor de la métrica se desglosan en función de la segunda métrica, luego la tercera métrica, etc. Cuando todas las métricas están conectadas, se aplica la ordenación de diccionario estándar de los elementos de línea de desglose.
* **Diseño 3**: como en el caso del diseño 2, solo las filas N superiores (es decir, el número establecido en "máximo de filas") salen en el informe.
* **Diseño 4**: como en el caso del diseño 2, con la excepción de que los elementos de línea para cada periodo de granularidad de fecha se agrupan y se ordenan en ese intervalo de tiempo respectivo.

Consulte la columna "Diseño de informe" en esta tabla para determinar cómo "Orden de las métricas" interactúa con otras opciones de informes de Data Warehouse.

| Ordenar por métrica? | ¿Tiene métricas? | ¿Tienes desgloses? | ¿Granularidad de la fecha? | ¿Máximo de filas establecidas? | Diseño de informe |
|---|---|---|---|---|---|
| No | Sí o No | Sí o No | Sí o No | Sí o No | 1 |
| Sí | No | Sí o No | Sí o No | Sí o No | 1 |
| Sí | Sí | No | No | N/D | 1 |
| Sí | Sí | No | Sí o No | No | 1 |
| Sí | Sí | Sí | No | No | 2 |
| Sí | Sí | No | Sí | Sí | 3 |
| Sí | Sí | Sí | Sí o No | Sí | 3 |
| Sí | Sí | Sí | Sí | No | 4 |


---
description: Descubra cómo ordenar por métrica facilita la interpretación y comparación de los informes de Data Warehouse con otras vistas de informes de desgloses de Analytics.
title: Ordenar por métrica
feature: Data Warehouse
exl-id: 6bd82951-c3b4-4ba2-8e4d-b7c9b351911b
TQID: 'https://experienceleague.adobe.com/YPqL6i9RWACubLdf2ywm8xuPyeQkZ30L6rO6FAbhpJI'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2: id: f47edbe0-f963-46ff-a667-71011396f5f3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 337
ht-degree: 92%

---

# Ordenar por métrica

Proporciona informes de desgloses clasificados en Data Warehouse, ordenados por el valor de métrica descendente.

La ordenación por métrica permite interpretar más fácilmente los informes de Data Warehouse, así como compararlos más fácilmente con otras vistas de informes de desgloses de Analytics.

A continuación se muestra cómo al habilitar la opción &quot;Orden de las métricas&quot; se reordenarán las filas de un informe de Data Warehouse.

Los informes del Data Warehouse se pueden organizar con &quot;Orden de las métricas&quot;, en función de cómo se configure la granularidad de la fecha, las dimensiones de informes o las métricas y de si la opción &quot;Máximo de filas&quot; está establecida:

* **Diseño 1**: los elementos de línea se ordenan en el orden de diccionario (valor predeterminado). Si la opción &quot;Máximo de filas&quot; está establecida, solo se proporcionan las primeras N filas en el informe.
* **Diseño 2**: Data Warehouse aplica una ordenación métrica sobre todas las filas del informe. Las conexiones del primer valor de la métrica se desglosan en función de la segunda métrica, luego la tercera métrica, etc. Cuando todas las métricas están conectadas, se aplica la ordenación de diccionario estándar de los elementos de línea de desglose.
* **Diseño 3**: como en el caso del diseño 2, solo las filas N superiores (es decir, el número establecido en &quot;máximo de filas&quot;) salen en el informe.
* **Diseño 4**: como en el caso del diseño 2, con la excepción de que los elementos de línea para cada periodo de granularidad de fecha se agrupan y se ordenan en ese intervalo de tiempo respectivo.

Consulte la columna &quot;Diseño de informe&quot; en esta tabla para determinar cómo &quot;Orden de las métricas&quot; interactúa con otras opciones de informes de Data Warehouse.

| Ordenar por métrica? | ¿Tiene métricas? | ¿Tienes desgloses? | ¿Granularidad de la fecha? | ¿Máximo de filas establecidas? | Diseño de informe |
|---|---|---|---|---|---|
| No | Sí o No | Sí o No | Sí o No | Sí o No | 1 |
| Sí | No | Sí o No | Sí o No | Sí o No | 1 |
| Sí | Sí | No | No | N/A | 1 |
| Sí | Sí | No | Sí o No | No | 1 |
| Sí | Sí | Sí | No | No | 2 |
| Sí | Sí | No | Sí | Sí | 3 |
| Sí | Sí | Sí | Sí o No | Sí | 3 |
| Sí | Sí | Sí | Sí | No | 4 |

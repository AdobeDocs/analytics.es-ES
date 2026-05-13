---
title: Promedio de vistas de página por visita
description: El número promedio de veces que un elemento de dimensión determinado apareció en una visita.
feature: Metrics
exl-id: fef6e803-e819-4f0f-8cb0-c565328a8bea
TQID: https://experienceleague.adobe.com/sospsPhk77O5qOLcMLmu7gB7rvlxbp8rGqB39LCnQ5g
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 216
ht-degree: 92%

---

# Promedio de vistas de página por visita

La dimensión “Promedio de vistas de página por visita” muestra cuántas vistas de página se produjeron en promedio con respecto a la dimensión deseada. En el caso de las dimensiones basadas en el tiempo, puede ver cómo el número promedio de vistas de página dentro de una visita se mantiene a lo largo del tiempo. Esta [métrica](overview.md) es útil cuando desea comprender con qué frecuencia aparecen los elementos de dimensión en una visita.

>[!TIP]
>
>Utilice esta métrica junto con otra métrica (como [Visitas](visits.md)) para obtener mejores datos. Si utiliza esta métrica por sí misma, obtendrá elementos de dimensión que contengan vistas de página de anomalías por visita, lo que generalmente no es muy útil.

## Cálculo de esta métrica

Esta métrica se calcula mediante la fórmula [`Page views`](page-views.md)` divided by `[`Visits`](visits.md).

## Porcentajes superiores al 100%

Esta métrica contiene con frecuencia porcentajes superiores al 100%. El denominador es el promedio de vistas de página por visita de toda la dimensión, y el numerador es el promedio de vistas de página por visita del elemento de dimensión. Si el promedio de vistas de página por visita de toda la dimensión es menor que el promedio de vistas de página por visita de un elemento de dimensión determinado, verá porcentajes por encima del 100%. Al ordenar los informes de clasificación por esta métrica, se muestran los valores promedio de vistas de página por visita de la anomalía, lo cual generalmente no es muy útil. Adobe recomienda ordenar según otra métrica, como [Visitas](visits.md), en los informes de clasificación.

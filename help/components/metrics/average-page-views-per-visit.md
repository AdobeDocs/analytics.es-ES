---
title: Promedio de vistas de página por visita
description: El número promedio de veces que un elemento de dimensión determinado apareció en una visita.
feature: Metrics
exl-id: fef6e803-e819-4f0f-8cb0-c565328a8bea
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '215'
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

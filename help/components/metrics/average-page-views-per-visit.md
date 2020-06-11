---
title: Promedio de vistas de página por visita
description: El número promedio de veces que un valor de dimensión determinado apareció en una visita.
translation-type: tm+mt
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 0%

---


# Promedio de vistas de página por visita

La dimensión &#39;vistas de página promedio por visita&#39; muestra cuántas vistas de página se produjeron en promedio con respecto a la dimensión deseada. En el caso de las dimensiones basadas en el tiempo, puede ver cómo el número promedio de vistas de página dentro de una visita se mantiene a lo largo del tiempo. Esta métrica es útil cuando desea comprender con qué frecuencia aparecen los valores de dimensión en una visita.

>[SUGERENCIA] Utilice esta métrica junto con otra métrica (como [Visitas](visits.md)) para obtener mejores perspectivas. Si utiliza esta métrica por sí misma, obtendrá valores de dimensión que contengan vistas de página de anomalías por visita, lo que generalmente no es valioso.

## Cómo se calcula esta métrica

Esta métrica se calcula mediante la fórmula [`Page views`](page-views.md)` divided by `[`Visits`](visits.md).

## Porcentajes superiores al 100%

Esta métrica contiene con frecuencia porcentajes superiores al 100 %. El denominador es el promedio de vistas de página por visita de toda la dimensión, y el numerador es el promedio de vistas de página por visita del valor de dimensión. Si el promedio de vistas de página por visita de toda la dimensión es menor que el promedio de vistas de página por visita de un valor de dimensión determinado, verá porcentajes por encima del 100%. Al ordenar los informes de clasificación por esta métrica, se muestran los valores promedio de vistas de página por visita de la anomalía, lo cual generalmente no es valioso. Adobe recomienda ordenar según otra métrica, como [Visitas](visits.md), en los informes de clasificación.
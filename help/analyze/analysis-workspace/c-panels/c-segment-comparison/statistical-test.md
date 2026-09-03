---
description: Descubra cómo se utilizan las pruebas estadísticas en la comparación de segmentos.
keywords: Analysis Workspace;IQ de segmento
title: Pruebas Estadísticas Utilizadas En La Comparación De Segmentos
feature: Segmentation
role: User, Admin
exl-id: b1c235ca-2eab-48d2-bf11-e8a8c4067d03
TQID: https://experienceleague.adobe.com/49kZ6LC9OMizQvqxE2PCq1LtqhUHtf5iKQUgpgqSmmE
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2: id: e38cbddc-1633-4cd5-bed5-9f289f2a6029
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 451
ht-degree: 9%

---

# Pruebas estadísticas utilizadas en la comparación de segmentos

Cada una de las tablas de comparación principales muestra una puntuación diferente. Esta puntuación se calcula mediante varias pruebas estadísticas, en función de la comparación que se realice. Sin embargo, independientemente de la prueba que se utilice, la puntuación de diferencia se muestra como un valor entre 0 y 1.

Una puntuación de 0 significa que no hay diferencia entre los dos segmentos y una puntuación de 1 significa que hubo una diferencia muy grande entre los dos segmentos. Existen dos tipos de pruebas estadísticas empleadas para generar estas puntuaciones de diferencia:

* Para la tabla **[!UICONTROL Métricas principales]** se usa una prueba U de Mann-Whitney,
* Para la tabla **[!UICONTROL Principales elementos de Dimension]** y **[!UICONTROL Segmentos principales]** se utiliza una comparación de diferencias de riesgo.

## Puntuación de diferencia de las métricas principales

En la tabla Métricas principales, la herramienta de comparación de segmentos utiliza una prueba U de Mann-Whitney de dos muestras. Esta prueba es una prueba de igualdad no paramétrica que se utiliza para comparar las distribuciones de probabilidad unidimensionales de cada métrica para cada segmento considerado. La puntuación de diferencia en la tabla de métricas es una combinación del valor p de la estadística de U calculada (que representa la diferencia estocástica entre los dos segmentos se distribuyen en una métrica determinada) y la magnitud relativa de la diferencia observada. Una puntuación de diferencia grande (cercana a 1) significa que la métrica en particular tiene una gran diferencia relativa, así como una alta confianza estadística en que los segmentos son diferentes.

## Elementos de dimensión principales y puntuaciones de diferencia de los segmentos principales

Para calcular la puntuación de diferencia en las tablas Principales elementos de Dimension y Principales diferencias de segmentos, se utiliza un algoritmo de diferenciación de riesgo relativo (similar a la proporción de riesgo, aunque utilizando una diferencia en lugar de una proporción). Una diferencia de riesgo se calcula restando las incidencias acumuladas de un elemento de dimensión (o superposición con un segmento de la tabla de segmentos) de un segmento seleccionado del otro. Una puntuación de diferencia alta (cercana a 1) significa que el elemento de dimensión o segmento terciario en particular era muy destacado en uno de los segmentos seleccionados y no en el otro.

>[!NOTE]
>
>En las tres tablas, la estadística de diferencia está basada en una muestra de visitantes adecuada para que el proceso vaya tan rápido como sea posible sin perder la precisión estadística. Aunque la puntuación de diferencia se basa en una muestra, los resultados presentados en la tabla no se muestrean. Para garantizar la relevancia estadística, cada prueba estadística se basa en un algoritmo de asignación dinámica de modo que el segmento más pequeño contenga un tamaño de muestra que proporcione menos del 3 % de margen de error. Si un segmento contiene muy pocos visitantes (menos de 1000), se utilizan todos los datos disponibles en lugar de la muestra para calcular la puntuación de diferencia.

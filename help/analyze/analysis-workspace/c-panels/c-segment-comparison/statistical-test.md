---
description: Descubra cómo se utilizan las pruebas estadísticas en la comparación de segmentos.
keywords: Analysis Workspace;IQ de segmento
title: Pruebas Estadísticas Utilizadas En La Comparación De Segmentos
feature: Segmentation
role: User, Admin
exl-id: b1c235ca-2eab-48d2-bf11-e8a8c4067d03
source-git-commit: b4c1636bdc9d5be522b16f945a46beabf4f7a733
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 43%

---

# Pruebas estadísticas utilizadas en la comparación de segmentos

Cada una de las tablas de comparación principales muestra una puntuación diferente. Esta puntuación se calcula mediante varias pruebas estadísticas, en función de la comparación que se realice. Sin embargo, independientemente de la prueba que se utilice, la puntuación de diferencia se muestra como un valor entre 0 y 1.

Una puntuación de 0 significa que no hay diferencia entre los dos segmentos y una puntuación de 1 significa que hubo una diferencia muy grande entre los dos segmentos. Existen dos tipos de pruebas estadísticas empleadas para generar estas puntuaciones de diferencia:

* Para la tabla **[!UICONTROL Métricas principales]** se usa una prueba U de Mann-Whitney,
* Para la tabla **[!UICONTROL Principales elementos de Dimension]** y **[!UICONTROL Segmentos principales]** se utiliza una comparación de diferencias de riesgo.

## Puntuación de diferencia de las métricas principales

En la tabla Métricas principales, la herramienta de comparación de segmentos utiliza una prueba U de Mann-Whitney de dos muestras. Esta prueba es una prueba de igualdad no paramétrica que se utiliza para comparar las distribuciones de probabilidad unidimensionales de cada métrica para cada segmento considerado. La puntuación de diferencia en la tabla de métricas es una combinación del valor p de la estadística U calculada (que representa cómo están distribuidos estocásticamente diferente los dos segmentos en una métrica particular) y la magnitud relativa de la diferencia observada. Una puntuación de diferencia grande (cercana a 1) significa que la métrica en particular tiene una gran diferencia relativa, así como una alta confianza estadística en que los segmentos son diferentes.

## Elementos de dimensión principales y puntuaciones de diferencia de los segmentos principales

Para calcular la puntuación de diferencia en las tablas de elementos de dimensión principales y diferencia de segmentos principales, se utiliza un algoritmo de diferencia de riesgo relativo (parecido al cociente de riesgo, aunque con una diferencia en lugar de un cociente). La diferencia de riesgo se calcula restando las incidencias acumulativas de un elemento de dimensión (o de superposición con un segmento de la tabla de segmentos) de un segmento seleccionado del otro. Una puntuación de diferencia alta (cercana a 1) significa que el elemento de dimensión o segmento terciario en particular era muy destacado en uno de los segmentos seleccionados y no en el otro.

>[!NOTE]
>
>En las tres tablas, la estadística de diferencia está basada en una muestra de visitantes adecuada para que el proceso vaya tan rápido como sea posible sin perder la precisión estadística. Mientras que la puntuación de diferencia está basada en una muestra, los resultados presentados en la tabla no son muestras. Para garantizar la relevancia estadística, cada prueba estadística se basa en un algoritmo de asignación dinámica de modo que incluso el segmento más pequeño contiene un tamaño de muestra que ofrece un margen de error inferior al 3 %. Si un segmento contiene muy pocos visitantes (menos de 1000), se utilizan todos los datos disponibles en lugar de la muestra para calcular la puntuación de diferencia.

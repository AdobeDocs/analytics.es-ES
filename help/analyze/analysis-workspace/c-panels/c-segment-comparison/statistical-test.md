---
description: Cada una de las tablas de comparación principales muestra una puntuación diferente que se calcula mediante varias pruebas estadísticas, dependiendo de la comparación que se realice; no obstante, independientemente de la prueba que se utilice, la puntuación de diferencia se muestra como un valor entre 0 y 1.
keywords: Analysis Workspace;Segment IQ
title: Pruebas estadísticas utilizadas en la comparación de segmentos
topic: Reports and analytics
uuid: c3f52470-5bfc-4e6b-8638-1c142b08d013
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Pruebas estadísticas utilizadas en la comparación de segmentos

Cada una de las tablas de comparación principales muestra una puntuación diferente que se calcula mediante varias pruebas estadísticas, dependiendo de la comparación que se realice; no obstante, independientemente de la prueba que se utilice, la puntuación de diferencia se muestra como un valor entre 0 y 1.

Una puntuación de 0 significa que no hay diferencia entre los dos segmentos y una puntuación de 1 significa que hubo una gran diferencia entre los dos segmentos. Existen dos tipos de pruebas estadísticas utilizadas para generar estas puntuaciones de diferencia: para la tabla de métricas principales se utiliza una prueba U de Mann-Whitney y para los elementos de dimensión principales y la tabla de segmentos principales se utiliza una comparación de diferencia de riesgo.

## Puntuación de diferencia de las métricas principales {#section_5E8047464EB945C78543B25F8F30F17A}

En la tabla Métricas principales, la herramienta Comparación de segmentos utiliza una prueba U de Mann-Whitney de dos muestras, que es una prueba de igualdad no paramétrica utilizada para comparar las distribuciones de probabilidad unidimensionales de cada métrica para cada segmento considerado. La puntuación de diferencia en la tabla de métricas es una combinación del valor p de la estadística U calculada (que representa cómo se distribuyen estocásticamente diferentes los dos segmentos en una métrica en particular) y la magnitud relativa de la diferencia observada. Una puntuación de diferencia grande (cercana a 1) significa que la métrica en particular tiene una gran diferencia relativa, así como una confianza estadística alta en que los segmentos son diferentes.

## Elementos de dimensión principales y puntuaciones de diferencia de los segmentos principales {#section_8073ADA6053B44C9A23FDC5ED4AF2AC4}

Para calcular la puntuación de diferencia en las tablas Elementos de dimensión principales y Diferencia de segmento superior, se utiliza un algoritmo de diferencia de riesgo relativo (similar a la relación de riesgo, aunque se utiliza una diferencia en lugar de una proporción). Una diferencia de riesgo se calcula restando las incidencias acumulativas de un elemento de dimensión (o superponiéndose con un segmento de la tabla de segmentos) de un segmento seleccionado del otro. Una puntuación de diferencia alta (cercana a 1) significa que el elemento de dimensión o segmento terciario en particular fue muy prominente en uno de los segmentos seleccionados y no en el otro.

>[!NOTE] En las tres tablas, la estadística de diferencia está basada en una muestra de visitantes adecuada para que el proceso vaya tan rápido como sea posible sin perder la precisión estadística. Aunque la puntuación de diferencia se basa en una muestra, los resultados presentados en la tabla no se muestrean. Para garantizar la relevancia estadística, cada prueba estadística se basa en un algoritmo de asignación dinámica de modo que el segmento más pequeño contenga un tamaño de muestra que proporcione un margen de error inferior al 3 %. Si un segmento contiene muy pocos visitantes (menos de 1.000), usamos todos los datos disponibles y no tomamos muestras para calcular la puntuación de diferencia.

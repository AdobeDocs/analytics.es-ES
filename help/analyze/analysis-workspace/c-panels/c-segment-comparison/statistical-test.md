---
description: Cada una de las tablas de comparación principales muestra una puntuación diferente que se calcula mediante varias pruebas estadísticas, dependiendo de la comparación que se realice; no obstante, independientemente de la prueba que se utilice, la puntuación de diferencia se muestra como un valor entre 0 y 1.
keywords: Analysis Workspace; IQ de segmento
seo-description: Cada una de las tablas de comparación principales muestra una puntuación diferente que se calcula mediante varias pruebas estadísticas, dependiendo de la comparación que se realice; no obstante, independientemente de la prueba que se utilice, la puntuación de diferencia se muestra como un valor entre 0 y 1.
seo-title: Pruebas estadísticas utilizadas en comparación de segmentos
solution: Analytics
title: Pruebas estadísticas utilizadas en comparación de segmentos
topic: Reports and Analytics
uuid: c 3 f 52470-5 bfc -4 e 6 b -8638-1 c 142 b 08 d 013
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Pruebas estadísticas utilizadas en comparación de segmentos

Cada una de las tablas de comparación principales muestra una puntuación diferente que se calcula mediante varias pruebas estadísticas, dependiendo de la comparación que se realice; no obstante, independientemente de la prueba que se utilice, la puntuación de diferencia se muestra como un valor entre 0 y 1.

Una puntuación de 0 significa que no hay diferencia entre los dos segmentos y una puntuación de 1 significa que ha habido una diferencia muy grande entre los segmentos. Existen dos tipos de pruebas estadísticas utilizadas para generar dichas puntuaciones de diferencia: para la tabla de métricas principales se utiliza una prueba U de Mann-Whitney, y para los elementos de dimensión principales y la tabla de segmentos principales se utiliza una comparación de diferencia de riesgo.

## Top metrics difference score {#section_5E8047464EB945C78543B25F8F30F17A}

En la tabla de métricas principales, la herramienta Comparación de segmentos utiliza dos muestras de la prueba U de Mann-Whitney, que es una prueba de igualdad no paramétrica que se utiliza para comparar las distribuciones de probabilidad de una dimensión de cada métrica para cada segmento considerado. La puntuación de diferencia en la tabla de métricas es una combinación del valor p de la estadística U calculada (que representa cómo están distribuidos estocásticamente diferente los dos segmentos en una métrica particular) y la magnitud relativa de la diferencia observada. Una puntuación de diferencia grande (cercana a 1) significa que la métrica tiene una diferencia relativa grande, así como una confianza estadística alta de que los segmentos son diferentes.

## Top dimension items and top segments difference scores {#section_8073ADA6053B44C9A23FDC5ED4AF2AC4}

Para calcular la puntuación de diferencia en las tablas de elementos de dimensión principales y diferencia de segmentos principales, se utiliza un algoritmo de diferencia de riesgo relativo (parecido al cociente de riesgo, aunque con una diferencia en lugar de un cociente). La diferencia de riesgo se calcula restando las incidencias acumulativas de un elemento de dimensión (o de superposición con un segmento de la tabla de segmentos) de un segmento seleccionado del otro. Una puntuación de diferencia alta (cercana a 1) significa que el elemento de dimensión particular o el segmento terciario fue muy relevante en uno de los segmentos seleccionados y no en el otro.

>[!NOTE]
>
>En las tres tablas, la estadística de diferencia se basa en una muestra adecuada de visitantes para que el proceso se ejecute lo más rápido posible mientras permanece con precisión estadística. Mientras que la puntuación de diferencia está basada en una muestra, los resultados presentados en la tabla no son muestras. Para garantizar la relevancia estadística, cada prueba estadística se basa en un algoritmo de asignación dinámica de modo que incluso el segmento más pequeño contiene un tamaño de muestra que ofrece un margen de error inferior al 3 %. Si un segmento contiene muy pocos visitantes (menos de 1 000), se utilizan todos los datos disponibles y no se realiza una muestra al calcular la puntuación de diferencia.


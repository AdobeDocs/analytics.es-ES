---
description: Cada una de las tablas de comparación principales muestra una puntuación diferente que se calcula mediante varias pruebas estadísticas, dependiendo de la comparación que se realice; no obstante, independientemente de la prueba que se utilice, la puntuación de diferencia se muestra como un valor entre 0 y 1.
keywords: Analysis Workspace;IQ de segmento
title: Pruebas estadísticas utilizadas en la comparación de segmentos
feature: Conceptos básicos de Reports & Analytics
uuid: c3f52470-5bfc-4e6b-8638-1c142b08d013
role: Business Practitioner, Administrator
exl-id: b1c235ca-2eab-48d2-bf11-e8a8c4067d03
translation-type: tm+mt
source-git-commit: cddf2a76ca36914f133379959b7cbb5246bdd695
workflow-type: tm+mt
source-wordcount: '470'
ht-degree: 99%

---

# Pruebas estadísticas utilizadas en la comparación de segmentos

Cada una de las tablas de comparación principales muestra una puntuación diferente que se calcula mediante varias pruebas estadísticas, dependiendo de la comparación que se realice; no obstante, independientemente de la prueba que se utilice, la puntuación de diferencia se muestra como un valor entre 0 y 1.

Una puntuación de 0 significa que no hay diferencia entre los dos segmentos y una puntuación de 1 significa que ha habido una diferencia muy grande entre los segmentos. Existen dos tipos de pruebas estadísticas utilizadas para generar dichas puntuaciones de diferencia: para la tabla de métricas principales se utiliza una prueba U de Mann-Whitney, y para los elementos de dimensión principales y la tabla de segmentos principales se utiliza una comparación de diferencia de riesgo.

## Puntuación de diferencia de las métricas principales {#section_5E8047464EB945C78543B25F8F30F17A}

En la tabla de métricas principales, la herramienta Comparación de segmentos utiliza dos muestras de la prueba U de Mann-Whitney, que es una prueba de igualdad no paramétrica que se utiliza para comparar las distribuciones de probabilidad de una dimensión de cada métrica para cada segmento considerado. La puntuación de diferencia en la tabla de métricas es una combinación del valor p de la estadística U calculada (que representa cómo están distribuidos estocásticamente diferente los dos segmentos en una métrica particular) y la magnitud relativa de la diferencia observada. Una puntuación de diferencia grande (cercana a 1) significa que la métrica tiene una diferencia relativa grande, así como una confianza estadística alta de que los segmentos son diferentes.

## Elementos de dimensión principales y puntuaciones de diferencia de los segmentos principales {#section_8073ADA6053B44C9A23FDC5ED4AF2AC4}

Para calcular la puntuación de diferencia en las tablas de elementos de dimensión principales y diferencia de segmentos principales, se utiliza un algoritmo de diferencia de riesgo relativo (parecido al cociente de riesgo, aunque con una diferencia en lugar de un cociente). La diferencia de riesgo se calcula restando las incidencias acumulativas de un elemento de dimensión (o de superposición con un segmento de la tabla de segmentos) de un segmento seleccionado del otro. Una puntuación de diferencia alta (cercana a 1) significa que el elemento de dimensión particular o el segmento terciario fue muy relevante en uno de los segmentos seleccionados y no en el otro.

>[!NOTE]
>
>En las tres tablas, la estadística de diferencia está basada en una muestra de visitantes adecuada para que el proceso vaya tan rápido como sea posible sin perder la precisión estadística. Mientras que la puntuación de diferencia está basada en una muestra, los resultados presentados en la tabla no son muestras. Para garantizar la relevancia estadística, cada prueba estadística se basa en un algoritmo de asignación dinámica de modo que incluso el segmento más pequeño contiene un tamaño de muestra que ofrece un margen de error inferior al 3 %. Si un segmento contiene muy pocos visitantes (menos de 1 000), se utilizan todos los datos disponibles y no se realiza una muestra al calcular la puntuación de diferencia.

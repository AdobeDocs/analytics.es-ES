---
description: La detección de anomalías de Analysis Workspace utiliza una serie de técnicas estadísticas avanzadas para determinar si una observación debe considerarse como anómala o no.
seo-description: La detección de anomalías de Analysis Workspace utiliza una serie de técnicas estadísticas avanzadas para determinar si una observación debe considerarse como anómala o no.
seo-title: Técnicas estadísticas utilizadas en la detección de anomalías
title: Técnicas estadísticas utilizadas en la detección de anomalías
uuid: b6ef6a2e-0836-4c9a-bf7e-01910199bb92
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Técnicas estadísticas utilizadas en la detección de anomalías

La detección de anomalías de Analysis Workspace utiliza una serie de técnicas estadísticas avanzadas para determinar si una observación debe considerarse como anómala o no.

Según la granularidad de fecha utilizada en el informe, se utilizan 3 técnicas estadísticas diferentes, específicamente para la detección de anomalías por hora, por día, por semana o por mes. Cada técnica estadística se enumera a continuación.

## Anomaly detection for daily granularity {#section_758ACA3C0A6B4D399563ECABFB8316FA}

Para los informes de granularidad diaria, el algoritmo considera distintos factores importantes para ofrecer los resultados más precisos posibles. En primer lugar, el algoritmo determina qué tipo de modelo se aplicará en función de los datos disponibles de los cuales seleccionamos entre una de las dos clases: un modelo basado en series temporales o un modelo de detección atípica (llamado filtrado funcional).

El modelo de selección de series temporales se basa en las siguientes combinaciones por tipo de error, tendencia o temporada (ETS) como se describe en [Hyndman et al. (2008)](https://www.springer.com/us/book/9783540719168). En concreto, el algoritmo prueba las siguientes combinaciones:

1. ANA (error acumulativo, sin tendencia, temporada acumulativa)
1. AAA (error acumulativo, tendencia acumulativa, temporada acumulativa)
1. MNM (error multiplicativo, sin tendencia, temporada multiplicativa)
1. MNA (error multiplicativo, sin tendencia, temporada acumulativa)
1. AAN (error acumulativo, tendencia acumulativa, sin temporada)

Las pruebas de idoneidad del algoritmo de cada una de ellas mediante la selección de la que tiene mejor error de porcentaje absoluto promedio (MAPE). Si el MAPE del mejor modelo de serie temporal es superior al 15 % sin embargo, se aplica el filtrado funcional. Normalmente, los datos con un grado de repetición alto (como semana a semana o mes a mes) son la mejor opción con un modelo de serie temporal.

Tras la selección de modelo, a continuación, el modelo ajusta los resultados en función de los festivos y las temporadas año a año. Durante las vacaciones, el algoritmo comprueba si alguno de los festivos está presente en el rango de fechas de la generación de informes:

* Día de los Caídos (solo EE. UU.)
* 4 de julio (solo EE. UU.)
* Acción de gracias (solo EE. UU.)
* Black Friday
* Ciberlunes
* 24 al 26 de diciembre
* 1 de enero
* 31 de diciembre

Estos festivos se seleccionaron en base a un amplio análisis estadístico en muchos puntos de datos de clientes para identificar los festivos que más importaban en la mayor cantidad de tendencias de clientes. Aunque la lista no es exhaustiva para todos los clientes o ciclos comerciales, hemos descubierto que la aplicación de estos festivos mejoró significativamente el rendimiento del algoritmo en general para casi todos los conjuntos de datos de los clientes.

Una vez se ha seleccionado el modelo y se han identificado los festivos en el rango de fechas de generación de informes, el algoritmo se ejecuta de la siguiente manera:

1. Construir el período de referencia de anomalías: incluye hasta 35 días antes del intervalo de fechas de los informes y un intervalo de fechas coincidente 1 año antes (contabilizando los días bisiestos cuando sean necesarios e incluyendo cualquier festivo aplicable que pueda haberse producido en un día natural diferente del año anterior).
1. Comprueba si los festivos en el periodo actual (excluido el año anterior) son anómalos en función de los datos más recientes.
1. Si el festivo en el intervalo de fechas actual es anómalo, ajuste el valor esperado y el intervalo de confianza del festivo actual dado el festivo del año anterior (considerando 2 días antes y después). La corrección del festivo actual se basa en el error de porcentaje absoluto de la media más baja de:

   1. Efectos acumulativos
   1. Efectos multiplicativos
   1. Diferencia año a año

Observe la espectacular mejora del rendimiento en el Día de Navidad y Año Nuevo en el siguiente ejemplo:

![](assets/anomaly_statistics.png)

## Anomaly detection for hourly granularity {#section_014C9E9209AF43F8A03D5D46E3B3AEE7}

Los datos horarios dependen del mismo método de algoritmo de serie temporal que el algoritmo de granularidad diaria. Sin embargo, dependen en gran medida de dos patrones de tendencia: el ciclo de 24 horas, así como el ciclo de fin de semana/día laboral. Para capturar estos dos efectos de temporada, el algoritmo por horas construye dos modelos independientes para días de fin de semana y días laborables utilizando el mismo método detallado anteriormente.

Los plazos de aprendizaje de las tendencias horarias dependen de un plazo de retrospectiva de 336 horas.

## Anomaly detection for weekly and monthly granularities {#section_5D421576BFBC4B24A58DFCC0A6407545}

Las tendencias semanales y mensuales no muestran las mismas tendencias semanales o diarias que las granularidades por días u horas, por tanto, se utiliza un algoritmo independiente. Para semanal y mensual, se utiliza un método de detección de casos aparte de dos pasos conocido como la prueba de Desviación estudentizada extrema generalizada (GESD). Esta prueba considera el número máximo de anomalías esperadas combinadas con el método de diagramas de cajas ajustado (un método no paramétrico para la detección de casos aparte) para determinar el número máximo de casos aparte. Los dos pasos son:

1. Función de diagrama de cajas ajustado: esta función determina el número máximo de anomalías sobre los datos de entrada.
1. Función GESD: se aplica a los datos de entrada con el resultado del paso 1.

El paso de detección de anomalías de temporada de vacaciones y de temporada de año anterior resta los datos del año pasado de los datos de este año y luego repite los datos de nuevo utilizando el proceso de dos pasos anterior para verificar que las anomalías son adecuadas de temporada. Cada una de estas granularidades utiliza un periodo de 15 de inclusión retrospectiva de la fecha del rango de generación de informes seleccionada (tanto 15 meses como 15 semanas) y un rango de fechas correspondiente 1 año anterior para aprendizaje.

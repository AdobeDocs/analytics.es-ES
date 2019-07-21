---
description: La detección de anomalías de Analysis Workspace utiliza una serie de técnicas estadísticas avanzadas para determinar si una observación debe considerarse como anómala o no.
seo-description: La detección de anomalías de Analysis Workspace utiliza una serie de técnicas estadísticas avanzadas para determinar si una observación debe considerarse como anómala o no.
seo-title: Técnicas estadísticas utilizadas en la detección de anomalías
title: Técnicas estadísticas utilizadas en la detección de anomalías
uuid: b 6 ef 6 a 2 e -0836-4 c 9 a-bf 7 e -01910199 bb 92
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Técnicas estadísticas utilizadas en la detección de anomalías

La detección de anomalías de Analysis Workspace utiliza una serie de técnicas estadísticas avanzadas para determinar si una observación debe considerarse como anómala o no.

Según la granularidad de fecha utilizada en el informe, se utilizan tres técnicas estadísticas diferentes: específicamente para la detección de anomalías por hora, diarios, semanales/mensuales. Cada técnica estadística se enumera a continuación.

## Anomaly detection for daily granularity {#section_758ACA3C0A6B4D399563ECABFB8316FA}

Para los informes de granularidad diaria, el algoritmo considera distintos factores importantes para ofrecer los resultados más precisos posibles. Primero, el algoritmo determina qué tipo de modelo se aplicará según los datos disponibles que seleccionamos entre una de las dos clases: un modelo basado en series temporales o un modelo de detección de externos (denominado filtrado funcional).

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

Estos festivos se han seleccionado en base a un análisis estadístico exhaustivo de muchos puntos de datos de clientes para identificar los festivos más relevantes en el mayor número de tendencias de clientes. Aunque la lista no es completa para todos los ciclos de cliente o de negocio, hemos observado que la aplicación de estos festivos mejora significativamente el rendimiento del algoritmo en general para casi todos los conjuntos de datos de clientes.

Una vez se ha seleccionado el modelo y se han identificado los festivos en el rango de fechas de generación de informes, el algoritmo se ejecuta de la siguiente manera:

1. Construye el período de referencia de anomalías: esto incluye hasta 35 días antes del intervalo de fechas del informe y un intervalo de fechas coincidente 1 año anterior (teniendo en cuenta los días bisiestos cuando es necesario e incluye cualquier festivo aplicable que pueda haber tenido lugar en un día calendario distinto del año anterior).
1. Comprueba si los festivos en el periodo actual (excluido el año anterior) son anómalos en función de los datos más recientes.
1. Si el festivo en el rango de fechas actual es anómalo, se ajusta el valor esperado y el intervalo de confianza del festivo actual teniendo en cuenta el festivo del año anterior (se tienen en cuenta 2 días antes y después). La corrección del festivo actual se basa en el error de porcentaje absoluto de la media más baja de:

   1. Efectos acumulativos
   1. Efectos multiplicativos
   1. Diferencia año a año

Observe la drástica mejora en el rendimiento en el día de Navidad y en el día de Año Nuevo en el ejemplo siguiente:

![](assets/anomaly_statistics.png)

## Anomaly detection for hourly granularity {#section_014C9E9209AF43F8A03D5D46E3B3AEE7}

Los datos horarios dependen del mismo método de algoritmo de serie temporal que el algoritmo de granularidad diaria. Sin embargo, dependen en gran medida de dos patrones de tendencia: el ciclo de 24 horas, así como el ciclo de fin de semana/día laboral. Para capturar estos dos efectos de temporada, el algoritmo por horas construye dos modelos independientes para días de fin de semana y días laborables utilizando el mismo método detallado anteriormente.

Los plazos de aprendizaje de las tendencias horarias dependen de un plazo de retrospectiva de 336 horas.

## Anomaly detection for weekly and monthly granularities {#section_5D421576BFBC4B24A58DFCC0A6407545}

Las tendencias semanales y mensuales no muestran las mismas tendencias semanales o diarias que las granularidades por días u horas, por tanto, se utiliza un algoritmo independiente. Para semanal y mensual, se utiliza un método de detección de casos aparte de dos pasos conocido como la prueba de Desviación estudentizada extrema generalizada (GESD). Esta prueba considera el número máximo de anomalías esperadas combinadas con el método de diagramas de cajas ajustado (un método no paramétrico para la detección de casos aparte) para determinar el número máximo de casos aparte. Los dos pasos son:

1. Función de diagrama de cajas ajustado: esta función determina el número máximo de anomalías sobre los datos de entrada.
1. Función GESD: se aplica a los datos de entrada con el resultado del paso 1.

El paso de detección de anomalías por temporadas año a año y de festivos a continuación resta los datos del año anterior de los datos de este año y, a continuación, itera en los datos de nuevo utilizando un proceso de dos pasos adicional para verificar que las anomalías son adecuadas para la temporada. Cada una de estas granularidades utiliza un periodo de 15 de inclusión retrospectiva de la fecha del rango de generación de informes seleccionada (tanto 15 meses como 15 semanas) y un rango de fechas correspondiente 1 año anterior para aprendizaje.

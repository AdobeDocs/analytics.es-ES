---
title: Minuto
description: Minuto en el que se produjo la métrica.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 1%

---


# Minuto

La dimensión &#39;Minuto&#39; informa el minuto en que se produjo una métrica determinada (redondeada hacia abajo). El primer elemento de dimensión es el primer minuto del intervalo de fechas y el último elemento de dimensión es el último minuto del intervalo de fechas. Esta dimensión es valiosa para los informes de tendencias, ya que le permite ver las métricas a lo largo del tiempo. Dada la granularidad de esta dimensión, Adobe recomienda limitar el intervalo de fechas de sistema de informes a uno o dos días.

## Rellenar esta dimensión con datos

Esta dimensión funciona de forma predeterminada para todas las implementaciones. Si un grupo de informes contiene datos, esta dimensión funciona.

## Elementos de dimensión

Los elementos de dimensión incluyen un minuto determinado dentro del intervalo de fechas de un informe junto con su fecha. Tiene el formato `HH:MM YYYY-MM-DD`. Los elementos de dimensión que comienzan por `00:00` equivalen a medianoche ese día, mientras que los valores que comienzan por `23:59` equivalen a 11:59 PM para ese día.

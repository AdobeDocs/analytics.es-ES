---
title: Hora
description: Hora en la que se produjo la métrica.
translation-type: tm+mt
source-git-commit: e758c070f402113b6d8a9069437b53633974a3e9
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 10%

---


# Hora

La dimensión &#39;Hora&#39; informa la hora en que se produjo una métrica determinada (redondeada hacia abajo). El primer elemento de dimensión es la primera hora del intervalo de fechas y el último elemento de dimensión es la última hora del intervalo de fechas. Esta dimensión es valiosa para los informes de tendencias, ya que le permite ver las métricas a lo largo del tiempo.

## Rellene esta dimensión con datos

Esta dimensión funciona de forma predeterminada para todas las implementaciones. Si un grupo de informes contiene datos, esta dimensión funciona.

## Elementos de Dimension

Los elementos de Dimension incluyen una hora determinada dentro del intervalo de fechas de un informe junto con su fecha. Tiene el formato `HH:HH YYYY-MM-DD`.

## Tiempo de ahorro de verano

El horario de verano es una práctica en la que los relojes se establecen una hora antes en primavera y se retrasan una hora en otoño. Si la zona horaria de un grupo de informes utiliza DST, Adobe ajusta los datos correspondientes a esa hora.

* **Cuando comienza** el horario de verano: En marzo, los informes suelen mostrar un intervalo de horas en los datos donde los inicios de horario de verano se guardan. La hora no existía, por lo que no forma parte de la recopilación de datos. Tenga en cuenta que una pequeña cantidad de datos aún puede llegar a esta hora. Los servidores de recopilación de datos de Adobe tardan varios segundos (hasta un minuto) en tener en cuenta los ajustes del horario de verano.
* **Al finalizar** el horario de verano: En noviembre, los informes suelen mostrar una hora apilada en dobles en la que finaliza el horario de verano. La hora pasó dos veces, por lo que ambas horas se agregan en los informes.

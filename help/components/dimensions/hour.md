---
title: Hora
description: La hora en el que se produjo la métrica.
exl-id: 323c46dd-87d0-487a-b954-e5ccbc1b919d
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '242'
ht-degree: 100%

---

# Hora

La dimensión “Hora” indica la hora en la que se produjo una métrica determinada (redondeada hacia abajo). El primer elemento de dimensión es la primera hora del intervalo de fechas y el último elemento de dimensión es la última hora del intervalo de fechas. Esta dimensión es valiosa para los informes de tendencias, ya que le permite ver las métricas a lo largo del tiempo.

## Rellene esta dimensión con datos

Esta dimensión funciona de forma predeterminada para todas las implementaciones. Si un grupo de informes contiene datos, esta dimensión funciona.

## Elementos de dimensión

Los elementos de dimensión incluyen una hora determinada dentro del intervalo de fechas de un informe junto con su fecha. Tiene el formato `HH:HH YYYY-MM-DD`.

## Horario de verano

El horario de verano es una práctica en la que los relojes se establecen una hora antes en primavera y se retrasan una hora en otoño. Si la zona horaria de un grupo de informes utiliza DST, Adobe ajusta los datos correspondientes a esa hora.

* **Cuando comienza el horario de verano**: En marzo, los informes suelen mostrar un intervalo de horas en los datos donde se inicia el horario de verano. La hora no existía, por lo que no forma parte de la recopilación de datos. Tenga en cuenta que una pequeña cantidad de datos aún puede llegar a esta hora. Los servidores de recopilación de datos de Adobe tardan varios segundos (hasta un minuto) en tener en cuenta los ajustes del DST.
* **Al finalizar el horario de verano**: En noviembre, los informes suelen mostrar una hora apilada doble en la que finaliza el horario de verano. La hora ocurre dos veces, por lo que ambas horas se añaden a los informes.

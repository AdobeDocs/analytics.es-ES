---
title: Hora del día
description: La hora numérica del día, independientemente de qué día.
translation-type: tm+mt
source-git-commit: e758c070f402113b6d8a9069437b53633974a3e9
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 8%

---


# Hora del día

La dimensión &#39;Hora del día&#39; informa la hora numérica de un día determinado como un elemento de dimensión. Por ejemplo: si tiene un informe que abarca del 1 de enero al 7 de enero, la primera hora de cada día se agrupa en el mismo elemento de dimensión. Este informe es valioso si desea que un informe se desglose por hora del día relativa, pero no desea que las horas estáticas sean elementos de dimensión. Es especialmente valiosa como dimensión en los informes programados, ya que esta dimensión se desplaza con el intervalo de fechas seleccionado.

Esta dimensión se basa en el huso horario del grupo de informes y no en el huso horario local del visitante. Por ejemplo: si el grupo de informes se encuentra en la hora de la montaña y un visitante de California visita el sitio a las 10:00 AM, hora del Pacífico, los grupos de visitas se agrupan debajo del elemento de `11:00 AM` dimensión. Si desea una dimensión que registre la hora del visitante local, Adobe recomienda utilizar el complemento [getTimeParting](/help/implement/vars/plugins/gettimeparting.md) .

## Rellene esta dimensión con datos

Esta dimensión funciona de forma predeterminada para todas las implementaciones. Si un grupo de informes contiene datos, esta dimensión funciona.

## Elementos de Dimension

Los elementos de Dimension incluyen `12:00 AM` - `11:00 PM`, que representa la hora del día en que se produjo la visita (redondeada hacia abajo). Por ejemplo, si se generó una visita a las 3:58 p.m., se agrupa bajo el elemento de dimensión de `3:00 PM`.

## Tiempo de ahorro de verano

El horario de verano es una práctica en la que los relojes se establecen una hora antes en primavera y se retrasan una hora en otoño. Si la zona horaria de un grupo de informes utiliza DST, Adobe ajusta los datos correspondientes a esa hora.

* **Cuando comienza** el horario de verano: En marzo, los informes suelen mostrar un intervalo de horas en los datos donde los inicios de horario de verano se guardan. La hora no existía, por lo que no forma parte de la recopilación de datos. Tenga en cuenta que una pequeña cantidad de datos aún puede llegar a esta hora. Los servidores de recopilación de datos de Adobe tardan varios segundos (hasta un minuto) en tener en cuenta los ajustes del horario de verano.
* **Al finalizar** el horario de verano: En noviembre, los informes suelen mostrar una hora apilada en dobles en la que finaliza el horario de verano. La hora pasó dos veces, por lo que ambas horas se agregan en los informes.

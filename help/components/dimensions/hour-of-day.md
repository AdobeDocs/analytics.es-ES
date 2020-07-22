---
title: Hora del día
description: La hora numérica del día, independientemente de qué día.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 0%

---


# Hora del día

La dimensión &#39;Hora del día&#39; informa la hora numérica de un día determinado como un elemento de dimensión. Por ejemplo: si tiene un informe que abarca del 1 de enero al 7 de enero, la primera hora de cada día se agrupa en el mismo elemento de dimensión. Este informe es valioso si desea que un informe se desglose por hora del día relativa, pero no desea que las horas estáticas sean elementos de dimensión. Es especialmente valiosa como dimensión en los informes programados, ya que esta dimensión se desplaza con el intervalo de fechas seleccionado.

Esta dimensión se basa en el huso horario del grupo de informes y no en el huso horario local del visitante. Por ejemplo: si el grupo de informes se encuentra en la hora de la montaña y un visitante de California visita el sitio a las 10:00 AM, hora del Pacífico, los grupos de visitas se agrupan debajo del elemento de `11:00 AM` dimensión. Si desea una dimensión que registre la hora del visitante local, Adobe recomienda utilizar el complemento [getTimeParting](/help/implement/vars/plugins/gettimeparting.md) .

## Rellenar esta dimensión con datos

Esta dimensión funciona de forma predeterminada para todas las implementaciones. Si un grupo de informes contiene datos, esta dimensión funciona.

## Elementos de dimensión

Los elementos de dimensión incluyen `12:00 AM` - `11:00 PM`, que representa la hora del día en que se produjo la visita (redondeada hacia abajo). Por ejemplo, si se generó una visita a las 3:58 p.m., se agrupa bajo el elemento de dimensión de `3:00 PM`.

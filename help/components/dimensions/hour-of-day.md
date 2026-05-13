---
title: Hora del día
description: La hora numérica del día, independientemente de qué día.
feature: Dimensions
exl-id: b9361534-7e58-41ed-9a38-c02aeed7a2d8
TQID: https://experienceleague.adobe.com/cktusukSxy7fHIIUi-7MSmx8Gl9FlUObfmJGS3VC3Jw
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 362
ht-degree: 82%

---

# Hora del día

La &quot;Hora del día&quot; [dimension](overview.md) indica la hora numérica de cualquier día dado como un elemento de dimensión. Por ejemplo, si tiene un informe que abarca del 1 de enero al 7 de enero, la primera hora de cada día se agrupa en el mismo elemento de dimensión. Este informe es útil si desea un informe desglosado por hora del día relativa, pero no desea una hora estática como elementos de dimensión. Es especialmente útil como dimensión en los informes programados, ya que esta dimensión se desplaza con el intervalo de fechas seleccionado.

Esta dimensión se basa en la zona horaria del grupo de informes y no en la del visitante. Por ejemplo, si el grupo de informes se encuentra en la zona Pacífico y un visitante de California visita el sitio a las 10:00 a. m., hora del Pacífico, los grupos de visitas se agrupan bajo el elemento de dimensión `11:00 AM`. Si desea una dimensión que registre la hora del visitante local, Adobe recomienda utilizar el complemento [getTimeParting](/help/implement/vars/plugins/gettimeparting.md).

## Rellene esta dimensión con datos

Esta dimensión funciona de forma predeterminada para todas las implementaciones. Si un grupo de informes contiene datos, esta dimensión funciona.

## Elementos de dimensión

Los elementos de dimensión incluyen `12:00 AM` - `11:00 PM`, que representan la hora del día en la que se produjo la visita (redondeada hacia abajo). Por ejemplo, si se generó una visita a las 3:58 p.m., se agrupa bajo el elemento de dimensión de `3:00 PM`.

## Horario de verano

El horario de verano es una práctica en la que los relojes se establecen una hora antes en primavera y se retrasan una hora en otoño. Si la zona horaria de un grupo de informes utiliza DST, Adobe ajusta los datos correspondientes a esa hora.

* **Cuando comienza el horario de verano**: En marzo, los informes suelen mostrar un intervalo de horas en los datos donde se inicia el horario de verano. La hora no existía, por lo que no forma parte de la recopilación de datos. Tenga en cuenta que una pequeña cantidad de datos aún puede llegar a esta hora. Los servidores de recopilación de datos de Adobe tardan varios segundos (hasta un minuto) en tener en cuenta los ajustes del DST.
* **Al finalizar el horario de verano**: En noviembre, los informes suelen mostrar una hora apilada doble en la que finaliza el horario de verano. La hora ocurre dos veces, por lo que ambas horas se añaden a los informes.

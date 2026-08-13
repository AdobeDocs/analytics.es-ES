---
title: Hora
description: La hora en el que se produjo la métrica.
feature: Dimensions
exl-id: 323c46dd-87d0-487a-b954-e5ccbc1b919d
TQID: https://experienceleague.adobe.com/Gkigdxnrted-gkPoGCQMx229EvCmVvSt9Rr5QP-IfGU
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 243
ht-degree: 94%

---

# Hora

La dimensión [Hora](overview.md) indica la hora en la que se produjo una métrica determinada (redondeada hacia abajo). El primer elemento de dimensión es la primera hora del intervalo de fechas y el último elemento de dimensión es la última hora del intervalo de fechas. Esta dimensión es valiosa para los informes de tendencias, ya que le permite ver las métricas a lo largo del tiempo.

## Rellene esta dimensión con datos

Esta dimensión funciona de forma predeterminada para todas las implementaciones. Si un grupo de informes contiene datos, esta dimensión funciona.

## Elementos de dimensión

Los elementos de dimensión incluyen una hora determinada dentro del intervalo de fechas de un informe junto con su fecha. Tiene el formato `HH:HH YYYY-MM-DD`.

## Horario de verano

El horario de verano es una práctica en la que los relojes se establecen una hora antes en primavera y se retrasan una hora en otoño. Si la zona horaria de un grupo de informes utiliza DST, Adobe ajusta los datos correspondientes a esa hora.

* **Cuando comienza el horario de verano**: En marzo, los informes suelen mostrar un intervalo de horas en los datos donde se inicia el horario de verano. La hora no existía, por lo que no forma parte de la recopilación de datos. Tenga en cuenta que una pequeña cantidad de datos aún puede llegar a esta hora. Los servidores de recopilación de datos de Adobe tardan varios segundos (hasta un minuto) en tener en cuenta los ajustes del DST.
* **Al finalizar el horario de verano**: En noviembre, los informes suelen mostrar una hora apilada doble en la que finaliza el horario de verano. La hora ocurre dos veces, por lo que ambas horas se añaden a los informes.

---
title: Hora
description: La hora en el que se produjo la métrica.
feature: Dimensions
exl-id: 323c46dd-87d0-487a-b954-e5ccbc1b919d
TQID: 'https://experienceleague.adobe.com/Gkigdxnrted-gkPoGCQMx229EvCmVvSt9Rr5QP-IfGU'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 78%
---
# Hora

La dimensión [Hora](overview.md) indica la hora en la que se produjo una métrica determinada (redondeada hacia abajo). El primer elemento de dimensión es la primera hora del intervalo de fechas y el último elemento de dimensión es la última hora del intervalo de fechas. Esta dimensión es valiosa para los informes de tendencias, ya que le permite ver las métricas a lo largo del tiempo.

## Rellene esta dimensión con datos

Esta dimensión se deriva de la marca de tiempo de cada visita individual. No hay ninguna variable que establecer; funciona de forma predeterminada en cualquier implementación.

| Propiedad | Valor |
| --- | --- |
| **variable de AppMeasurement** | Ninguno (derivado de la marca de tiempo de la visita) |
| **Campo Web SDK / XDM** | Ninguno (derivado de la marca de tiempo de la visita) |
| **Parámetro de consulta** | n/a |
| **etiqueta XML** | n/a |
| **Límite de bytes** | n/a |
| **Persistencia** | Hit |

## Elementos de dimensión

Los elementos de dimensión incluyen una hora determinada dentro del intervalo de fechas de un informe junto con su fecha. Tiene el formato `HH:HH YYYY-MM-DD`.

## Horario de verano

El horario de verano es una práctica en la que los relojes se establecen una hora antes en primavera y se retrasan una hora en otoño. Si la zona horaria de un grupo de informes utiliza DST, Adobe ajusta los datos correspondientes a esa hora.

* **Cuando comienza el horario de verano**: En marzo, los informes suelen mostrar un intervalo de horas en los datos donde se inicia el horario de verano. La hora no existía, por lo que no forma parte de la recopilación de datos. Tenga en cuenta que una pequeña cantidad de datos aún puede llegar a esta hora. Los servidores de recopilación de datos de Adobe tardan varios segundos (hasta un minuto) en tener en cuenta los ajustes del DST.
* **Al finalizar el horario de verano**: En noviembre, los informes suelen mostrar una hora apilada doble en la que finaliza el horario de verano. La hora ocurre dos veces, por lo que ambas horas se añaden a los informes.

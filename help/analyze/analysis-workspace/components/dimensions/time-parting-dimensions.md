---
description: Obtenga información sobre cómo las dimensiones de partición de tiempo toman la marca de tiempo de los eventos recopilados y los desglosan en dimensiones más significativas, como Hora del día o Día de la semana.
title: Dimensiones de partición de tiempo
feature: Dimensions
role: User, Admin
exl-id: 92fbcc1e-1f7f-405a-8ad1-199fb7ba505e
TQID: https://experienceleague.adobe.com/bQVBmv3KhaDZtmUXSOY3UsustpCZKAwJ8rH9Qv49Rfw
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 266
ht-degree: 68%

---

# Dimensiones de partición de tiempo

La partición de tiempo toma la marca de tiempo de las visitas recogidas y la divide en dimensiones más significativas, como **Hora del día** o **Día de la semana**.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Dimensiones de partición de tiempo](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/time-parting-dimensions-in-analysis-workspace){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]


Las dimensiones de partición de tiempo se basan en el huso horario del grupo de informes o del grupo de informes virtuales. Estas dimensiones están disponibles en Analysis Workspace y pueden ayudar a responder a las siguientes preguntas:

* En un rango de datos de gran volumen, ¿cuál es la hora del día más popular para que los visitantes accedan a mi sitio o aplicación?
* ¿Hay días de la semana u horas del día en que la conversión es mayor en mi sitio o aplicación?
* ¿Qué rendimiento tienen las ventas del fin de semana en comparación con las ventas en días laborables?
* ¿Cuándo genera mayor conversión una determinada campaña de marketing? ¿Por la mañana o por la tarde?

>[!NOTE]
>
>Las dimensiones de partición de tiempo solo están disponibles en Analysis Workspace. Para utilizar dimensiones de partición de tiempo en otras soluciones de Analytics, puede implementar el [complemento getTimeParting](/help/implement/vars/plugins/gettimeparting.md).

Las dimensiones de partición de tiempo en Analysis Workspace incluyen:

| Dimensión | Valores de ejemplo |
| --- | --- |
| Hora del día | 0-23 |
| AM/PM | AM, PM |
| Día de la semana | Lunes, martes, miércoles, jueves, viernes, sábado, domingo |
| Fin de semana / Día de la semana | Fin de semana, día de la semana |
| Día del mes | 1-31 |
| Mes del año | Enero-diciembre |
| Día del año | 1-366 |
| Trimestre del año | T1, T2, T3, T4 |

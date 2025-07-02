---
description: Obtenga información sobre cómo las dimensiones de partición de tiempo toman la marca de tiempo de los eventos recopilados y la dividen en dimensiones más significativas, como Hora del día o Día de la semana.
title: Dimensiones de partición de tiempo
feature: Dimensions
role: User, Admin
exl-id: 92fbcc1e-1f7f-405a-8ad1-199fb7ba505e
source-git-commit: ff38740116ac6f12033ebdc17cffa3250a30f3f7
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 84%

---

# Dimensiones de partición de tiempo

La partición de tiempo toma la marca de hora de los aciertos recogidos y lo divide en dimensiones más significativas, como “Hora del día” o “Día de la semana”.


>[!BEGINSHADEBOX]

Vea ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Time=parting dimensions](https://video.tv.adobe.com/v/41459?quality=12&learn=on&captions=spa){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]


Las dimensiones de partición de tiempo se basan en el huso horario del grupo de informes o del grupo de informes virtuales. Estas dimensiones están disponibles en Analysis Workspace y pueden ayudar a responder a las siguientes preguntas:

* En un rango de datos de gran volumen, ¿cuál es la hora del día más popular para que los visitantes accedan a mi sitio o aplicación?
* ¿Hay días de la semana u horas del día en que la conversión es mayor en mi sitio o aplicación?
* ¿Qué rendimiento tienen las ventas del fin de semana en comparación con las ventas en días laborables?
* ¿Cuándo genera mayor conversión una determinada campaña de marketing? ¿Por la mañana o por la tarde?

>[!NOTE]
>
>Las dimensiones de partición de tiempo solo están disponibles en Analysis Workspace. Para utilizar dimensiones de partición de tiempo en otras soluciones de Analytics, puede implementar el [complemento getTimeParting](https://experienceleague.adobe.com/docs/analytics/implementation/vars/plugins/gettimeparting.html?lang=es).

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

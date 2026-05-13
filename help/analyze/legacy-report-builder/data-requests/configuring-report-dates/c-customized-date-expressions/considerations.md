---
description: Dos consideraciones importantes al utilizar la expresión personalizada para establecer el intervalo de fechas
title: Consideraciones de fecha personalizadas
uuid: a3bb3a63-0f15-4292-ade7-4ea852fe68c8
feature: Report Builder
role: User, Admin
exl-id: 66b817b3-7e9e-4030-92f3-797e730f9661
TQID: https://experienceleague.adobe.com/7PLNffmZnNnQ2X0HgnqYa8R3zWQvFPMSM8sbWocmxH4
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2: id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 415
ht-degree: 7%

---

# Consideraciones de fecha personalizadas

{{legacy-arb}}

Dos consideraciones importantes al utilizar la expresión personalizada para establecer el intervalo de fechas:

* El día en que se ejecuta el informe (con fecha de ) (o en que se actualizan las solicitudes) determina qué datos están disponibles.
* La sustitución de las fechas de inicio y finalización del informe afecta al intervalo de fechas que abarca el informe.

Dado que la disponibilidad de los datos depende tanto del lapso de tiempo del informe como de la fecha en la que se actualizan las solicitudes, asegúrese de ejecutar el informe el día adecuado para extraer la información deseada. Los ejemplos siguientes muestran ambas consideraciones.

Supongamos que realiza una solicitud de [!UICONTROL vistas de página] con granularidad agregada. En Norteamérica, la semana empieza el domingo. Para obtener informes actualizados de domingo a sábado (por ejemplo, del 23 de noviembre al 29 de noviembre de 2008), ejecute el informe (solicitudes de actualización) el domingo (30 de noviembre) de la semana anterior (del 23 de noviembre al 29 de noviembre).

Utilice esta expresión personalizada:

*Desde:* cw-1w *hasta:* cw-1d

Un análisis de la expresión personalizada cuando la [!UICONTROL fecha de finalización] inclusiva para la solicitud es el 30/11:

*De:* cw-1w

el día de la semana actual que comienza el domingo 30 de noviembre menos siete días = el día de la semana pasada que comienza el domingo 23 de noviembre

*Para:* cw-1d

el día de la semana actual que comienza el domingo 30 de noviembre menos un día = sábado 29 de noviembre

Una vez que la expresión personalizada esté asignada a la hoja de cálculo, actualice la solicitud con Domingo, 30 de noviembre de 2008 como [!UICONTROL Fecha de finalización] inclusiva para la solicitud flotante. Los datos reflejarán el periodo de una semana.

Si, en su lugar, actualiza la expresión y especifica el sábado 29 de noviembre como [!UICONTROL fecha de finalización] para la solicitud flotante, los datos reflejarán la semana del 16/11 al 22/11. Esto se debe a que la fecha de referencia para la actualización de la solicitud es un día antes.

Estas son las diferencias cuando la [!UICONTROL fecha de finalización] inclusiva para la solicitud es el 29/11:

*De:* cw-1w

el día de la semana actual que comienza el domingo 23 de noviembre menos siete días = el día de la semana pasada que comienza el domingo 16 de noviembre

*Para:* cw-1d

el día de la semana actual que comienza el domingo 23 de noviembre menos un día = sábado 22 de noviembre

En Europa y otros países, la semana empieza el lunes, en lugar del domingo. En este caso, puede personalizar el calendario para cambiar la fecha de inicio. (Consulte [Calendario personalizado](/help/analyze/legacy-report-builder/data-requests/configuring-report-dates/custom-calendar.md).)

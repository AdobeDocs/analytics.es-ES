---
description: 'Dos consideraciones importantes al utilizar la expresión personalizada para establecer el intervalo de fechas '
title: Consideraciones de fecha personalizadas
uuid: a3bb3a63-0f15-4292-ade7-4ea852fe68c8
feature: Report Builder
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 99%

---


# Consideraciones de fecha personalizadas

Dos consideraciones importantes al utilizar la expresión personalizada para establecer el intervalo de fechas:

* El día en que se ejecuta el informe (Con fecha) —o las solicitudes actualizadas— determina qué datos están disponibles.
* El desplazamiento de las fechas de inicio y finalización de un informe afecta al intervalo de fechas que abarca el informe.

La disponibilidad de los datos es sensible al intervalo de tiempo del informe y a la fecha en la que se actualizan las solicitudes en el informe, por lo que debe asegurarse de ejecutar el informe en el día adecuado para extraer la información deseada. Los siguientes ejemplos muestran estas dos consideraciones.

Suponga que realiza una solicitud por [!UICONTROL vistas de página] utilizando la granularidad agregada. En América del Norte, la semana comienza el domingo. Para obtener informes actualizados para el período de domingo a sábado (por ejemplo, 23 a 29 de noviembre de 2008), ejecute el informe (actualice las solicitudes) el domingo (30 de noviembre) para la semana anterior (23/11 a 29/11).

Utilice esta expresión personalizada:

*De:* cw-1w *A:* cw-1d

Un análisis de la expresión personalizada cuando la [!UICONTROL fecha de finalización] incluida para la solicitud es 30/11:

*De:* cw-1w

El día de la semana actual comenzando el domingo 30 de noviembre menos siete días = el día de la semana pasada comenzando el domingo 23 de noviembre.

*A:* cw-1d

El día de la semana actual comenzando el domingo 30 de noviembre menos un día = sábado 29 de noviembre.

Una vez que la expresión personalizada se asigne a la hoja de cálculo, actualice la solicitud utilizando domingo 30 de noviembre de 2008 como [!UICONTROL fecha de finalización] incluida para la solicitud flotante. Los datos reflejarán el período de toda la semana.

Si en cambio actualiza la expresión y especifica sábado, 29 de noviembre como [!UICONTROL fecha de finalización] para la solicitud flotante, los datos reflejarán la semana 16/11 a 22/11. Esto sucede porque la fecha de referencia de la actualización de la solicitud es un día antes.

A continuación se indican las diferencias cuando la [!UICONTROL fecha de finalización] incluida para la solicitud es 29/11:

*De:* cw-1w

El día de la semana actual comenzando el domingo 23 de noviembre menos siete días = el día de la semana pasada comenzando el domingo 16 de noviembre.

*A:* cw-1d

El día de la semana actual comenzando el domingo 23 de noviembre menos un día = sábado 22 de noviembre.

En Europa y algunos países, la semana comienza el lunes en lugar del domingo. En este caso, se puede personalizar el calendario para cambiar la fecha de inicio. (Consulte [Calendario personalizado](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md).)

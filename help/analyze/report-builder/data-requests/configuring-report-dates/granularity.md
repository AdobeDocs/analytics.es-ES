---
description: En el paso 1 del Asistente para solicitudes, puede aplicar un nivel de granularidad a la solicitud de datos. La granularidad especifica el nivel de detalle basado en el tiempo que se incluye en el informe.
title: Granularidad
topic: Report builder
uuid: 948b3ff2-fcff-45fc-9e8c-8a025ac562b1
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Granularidad

En el Asistente para solicitudes: Paso 1, es posible aplicar un nivel de granularidad a la solicitud de datos. La granularidad especifica el nivel de detalle basado en el tiempo que se incluye en el informe.

Los valores válidos son Hora, Día, Semana, Mes, Trimestre, Año y Agregado.

## Cómo procesa el creador de informes la granularidad

Supongamos que se selecciona un intervalo de fechas para un mes con la granularidad [!UICONTROL Mes]. Las solicitudes muestran el total para la métrica basada en exactamente 1 mes de datos. Si el intervalo de fechas de la solicitud abarca un trimestre, el informe muestra tres cifras: una para cada unidad de mes o fracción del mismo. Si hoy es 18 de marzo, al seleccionar el último trimestre se devuelve una cifra para 1 de enero a 31 de febrero, otra para 1 de febrero a 28 de febrero y una cifra final para 1 de marzo a 17 de marzo.

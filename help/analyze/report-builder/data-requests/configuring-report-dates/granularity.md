---
description: En el Paso 1 del Asistente para solicitudes, puede aplicar un nivel de granularidad a la solicitud de datos. La granularidad especifica el nivel de detalle basado en el tiempo que se incluye en el informe.
seo-description: En el Paso 1 del Asistente para solicitudes, puede aplicar un nivel de granularidad a la solicitud de datos. La granularidad especifica el nivel de detalle basado en el tiempo que se incluye en el informe.
seo-title: Granularidad
solution: Analytics
title: Granularidad
topic: Creador de informes
uuid: 948 b 3 ff 2-fcff -45 fc -9 e 8 c -8 a 025 ac 562 b 1
translation-type: tm+mt
source-git-commit: d75c58caf1220031fa36483a0ad50ea6f7be7c39

---


# Granularidad

En el Asistente para solicitudes: Paso 1, es posible aplicar un nivel de granularidad a la solicitud de datos. La granularidad especifica el nivel de detalle basado en el tiempo que se incluye en el informe.

Los valores válidos son Hora, Día, Semana, Mes, Trimestre, Año y Agregado.

## Cómo procesa la granularidad el creador de informes

Supongamos que se selecciona un intervalo de fechas para un mes con la granularidad [!UICONTROL Mes]. Las solicitudes muestran el total para la métrica basada en exactamente 1 mes de datos. Si el intervalo de fechas de la solicitud abarca un trimestre, el informe muestra tres cifras: una para cada unidad de mes o fracción del mismo. Si hoy es 18 de marzo, al seleccionar el último trimestre se devuelve una cifra para 1 de enero a 31 de febrero, otra para 1 de febrero a 28 de febrero y una cifra final para 1 de marzo a 17 de marzo.

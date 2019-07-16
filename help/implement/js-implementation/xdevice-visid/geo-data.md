---
description: Los datos de segmentación geográfica se registran en función de la primera visita y no cambia para una única visita independientemente del dispositivo que se use.
keywords: Implementación de Analytics
seo-description: Los datos de segmentación geográfica se registran en función de la primera visita y no cambia para una única visita independientemente del dispositivo que se use.
seo-title: Datos de segmentación geográfica
solution: Analytics
title: Datos de segmentación geográfica
topic: Desarrollador e implementación
uuid: 8449 bf 11-c 367-4698-a 73 e-f 6 cb 59 f 8 c 945
translation-type: tm+mt
source-git-commit: 67cc404c4502b1b7be3f089538d8a28d5cf7f659

---


# Datos de segmentación geográfica

>[!IMPORTANT]
>
>Este método de identificación de visitantes entre dispositivos ya no se recomienda. Please refer to the [Adobe Experience Cloud Device Co-op Documentation](https://marketing.adobe.com/resources/help/en_US/mcdc/).

Los datos de segmentación geográfica se registran en función de la primera visita y no cambia para una única visita independientemente del dispositivo que se use.

Si un cliente explora su sitio desde el equipo de casa y después desde un dispositivo móvil en un plazo de 30 minutos, no se cambian los datos de segmentación geográfica. Si utiliza VISTA para rellenar una evar con datos de segmentación geográfica, se basa en la dirección IP de cada visita. Esto podría generar varios valores de datos de segmentación geográfica si la dirección IP cambia para la misma visita.

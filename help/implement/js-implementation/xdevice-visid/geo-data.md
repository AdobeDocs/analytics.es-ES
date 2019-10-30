---
description: Los datos de segmentación geográfica se registran en función de la primera visita y no cambia para una única visita independientemente del dispositivo que se use.
keywords: Implementación de Analytics
seo-description: Los datos de segmentación geográfica se registran en función de la primera visita y no cambia para una única visita independientemente del dispositivo que se use.
seo-title: Datos de segmentación geográfica
solution: Analytics
title: Datos de segmentación geográfica
topic: Desarrollador e implementación
uuid: 8449bf11-c367-4698-a73e-f6cb59f8c945
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Datos de segmentación geográfica

>[!IMPORTANT]
>
>Ya no se recomienda este método de identificación de visitantes entre dispositivos. Consulte la documentación [de cooperación entre dispositivos de](https://marketing.adobe.com/resources/help/en_US/mcdc/)Adobe Experience Cloud.

Los datos de segmentación geográfica se registran en función de la primera visita y no cambia para una única visita independientemente del dispositivo que se use.

Si un cliente explora su sitio desde el equipo de casa y después desde un dispositivo móvil en un plazo de 30 minutos, no se cambian los datos de segmentación geográfica. Si usa VISTA para rellenar una eVar con datos de segmentación geográfica, se basa en la dirección IP de cada visita. Esto podría producir varios valores de segmentación geográfica si la dirección IP cambia para la misma visita.

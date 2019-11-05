---
description: Puede crear un segmento siempre que se produzca una asociación para una cookie de ID de visitante determinada.
keywords: Implementación de Analytics
seo-description: Puede crear un segmento siempre que se produzca una asociación para una cookie de ID de visitante determinada.
seo-title: Crear segmentos
solution: Analytics
title: Crear segmentos
topic: Desarrollador e implementación
uuid: 476a4667-033c-4e53-961d-ad67e7c2b045
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# Crear segmentos

>[!IMPORTANT]
>
>Ya no se recomienda este método de identificación de visitantes entre dispositivos. Consulte la documentación [de cooperación entre dispositivos de](https://marketing.adobe.com/resources/help/en_US/mcdc/)Adobe Experience Cloud.

Puede crear un segmento siempre que se produzca una asociación para una cookie de ID de visitante determinada.

Según la [tabla anterior](/help/implement/js-implementation/xdevice-visid/visit-example.md), si creó un segmento con un número de visitas igual a 9, incluiría las llamadas al servidor 12 y 13. Aunque técnicamente la llamada al servidor 11 formaba parte de la misma visita, los datos históricos de esa llamada al servidor no se modifican y el número de visitas permanece sin cambios.

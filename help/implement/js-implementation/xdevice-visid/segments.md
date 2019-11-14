---
description: Puede crear un segmento siempre que se produzca una asociación para una cookie de ID de visitante determinada.
keywords: Analytics Implementation
solution: Analytics
title: Crear segmentos
topic: Developer and implementation
uuid: 476a4667-033c-4e53-961d-ad67e7c2b045
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Crear segmentos

>[!IMPORTANT]
>
>Ya no se recomienda este método de identificación de visitantes entre dispositivos. Consulte la documentación [de cooperación entre dispositivos de](https://marketing.adobe.com/resources/help/en_US/mcdc/)Adobe Experience Cloud.

Puede crear un segmento siempre que se produzca una asociación para una cookie de ID de visitante determinada.

Según la [tabla anterior](/help/implement/js-implementation/xdevice-visid/visit-example.md), si creó un segmento con un número de visitas igual a 9, incluiría las llamadas al servidor 12 y 13. Aunque técnicamente la llamada al servidor 11 formaba parte de la misma visita, los datos históricos de esa llamada al servidor no se modifican y el número de visitas permanece sin cambios.

---
description: Puede crear un segmento siempre que se produzca una asociación para una cookie de ID de visitante determinada.
keywords: Implementación de Analytics
seo-description: Puede crear un segmento siempre que se produzca una asociación para una cookie de ID de visitante determinada.
seo-title: Crear segmentos
solution: Analytics
title: Crear segmentos
topic: Desarrollador e implementación
uuid: 476 a 4667-033 c -4 e 53-961 d-ad 67 e 7 c 2 b 045
translation-type: tm+mt
source-git-commit: 67cc404c4502b1b7be3f089538d8a28d5cf7f659

---


# Crear segmentos

>[!IMPORTANT]
>
>Este método de identificación de visitantes entre dispositivos ya no se recomienda. Please refer to the [Adobe Experience Cloud Device Co-op Documentation](https://marketing.adobe.com/resources/help/en_US/mcdc/).

Puede crear un segmento siempre que se produzca una asociación para una cookie de ID de visitante determinada.

Based on the [previous table](../../../implement/js-implementation/xdevice-visid/visit-example.md#concept_E3B32B8E539F4FDC8E3FA872328B87BA), if you created a segment where visit number equals 9, it would include server calls 12 and 13. Aunque técnicamente la llamada al servidor 11 formaba parte de la misma visita, los datos históricos de esa llamada al servidor no se modifican y el número de visitas permanece sin cambios.

---
description: Analytics contabiliza una visita cada vez que se produce una llamada al servidor con un Número de página de visita igual a 1.
keywords: Implementación de Analytics
seo-description: Analytics contabiliza una visita cada vez que se produce una llamada al servidor con un Número de página de visita igual a 1.
seo-title: Visitas
solution: Analytics
subtopic: Visitantes
title: Visitas
topic: Desarrollador e implementación
uuid: 3035 be 8 f -6 adc -45 df-a 3 f 2-5 de 6 d 3 ed 99 ce
translation-type: tm+mt
source-git-commit: 67cc404c4502b1b7be3f089538d8a28d5cf7f659

---


# Visitas

>[!IMPORTANT]
>
>Este método de identificación de visitantes entre dispositivos ya no se recomienda. Please refer to the [Adobe Experience Cloud Device Co-op Documentation](https://marketing.adobe.com/resources/help/en_US/mcdc/).

Analytics contabiliza una visita cada vez que se produce una llamada al servidor con un Número de página de visita igual a 1.

If you look at the [previous table](../../../implement/js-implementation/xdevice-visid/visit-example.md#concept_E3B32B8E539F4FDC8E3FA872328B87BA), this occurred 4 times: at hits 1, 9, 11, and 12. De forma similar a los visitantes, este valor vuelve a la normalidad después de la asociación inicial porque [!UICONTROL Número de página de visita] se restablece a 1 debido a un cambio en la [!UICONTROL ID de visitante] efectiva.

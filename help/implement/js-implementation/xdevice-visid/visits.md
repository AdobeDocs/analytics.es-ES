---
description: Analytics contabiliza una visita cada vez que se produce una llamada al servidor con un Número de página de visita igual a 1.
keywords: Implementación de Analytics
seo-description: Analytics contabiliza una visita cada vez que se produce una llamada al servidor con un Número de página de visita igual a 1.
seo-title: Visitas
solution: Analytics
subtopic: Visitantes
title: Visitas
topic: Desarrollador e implementación
uuid: 3035be8f-6adc-45df-a3f2-5de6d3ed99ce
translation-type: ht
source-git-commit: 67cc404c4502b1b7be3f089538d8a28d5cf7f659

---


# Visitas

>[!IMPORTANT]
>
>Ya no se recomienda este método de identificación de visitantes entre dispositivos. Consulte [Documentación de Adobe Experience Cloud Device Co-op](https://marketing.adobe.com/resources/help/es_ES/mcdc/).

Analytics contabiliza una visita cada vez que se produce una llamada al servidor con un Número de página de visita igual a 1.

Si observa la [tabla anterior](../../../implement/js-implementation/xdevice-visid/visit-example.md#concept_E3B32B8E539F4FDC8E3FA872328B87BA), esto ocurrió 4 veces: en las visitas individuales 1, 9, 11 y 12. De forma similar a los visitantes, este valor vuelve a la normalidad después de la asociación inicial porque [!UICONTROL Número de página de visita] se restablece a 1 debido a un cambio en la [!UICONTROL ID de visitante] efectiva.

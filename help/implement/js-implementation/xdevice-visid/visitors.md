---
description: Analytics contabiliza cada ID de visitante efectiva única como un visitante único.
keywords: Implementación de Analytics
seo-description: Analytics contabiliza cada ID de visitante efectiva única como un visitante único.
seo-title: Visitantes
solution: Analytics
subtopic: Visitantes
title: Visitantes
topic: Desarrollador e implementación
uuid: 16cfdb64-a3c6-4056-97da-3227cddcf1cd
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Visitantes

>[!IMPORTANT]
>
>Ya no se recomienda este método de identificación de visitantes entre dispositivos. Consulte la documentación [de cooperación entre dispositivos de](https://marketing.adobe.com/resources/help/en_US/mcdc/)Adobe Experience Cloud.

Analytics contabiliza cada ID de visitante efectiva única como un visitante único.

Si observa la [tabla anterior](../../../implement/js-implementation/xdevice-visid/visit-example.md#concept_E3B32B8E539F4FDC8E3FA872328B87BA), esto ocurrió 3 veces: en las visitas individuales 1, 9 y 10. Esto ocurre porque la [!UICONTROL ID de visitante] efectiva es la misma para ambas llamadas al servidor, y esto es así aunque haya varias horas de diferencia entre las visitas y se realicen desde dispositivos diferentes.

Esto puede aumentar el número de visitantes únicos que ve cuando la identificación de visitantes entre dispositivos está habilitada. El visitante se podría contabilizar dos veces en la misma visita: una en la visita inicial y otra después de que el usuario se autentique.

Cuando un visitante nuevo consulta el sitio, la cookie `s_vi` se rellena y se almacena. En el servidor de recopilación de datos, se crea un nuevo perfil para esta ID de visitante y se configura la [!UICONTROL ID de visitante] efectiva en el perfil para que coincida con la cookie.

Cuando la identificación de visitantes entre dispositivos están habilitada, si se proporciona una variable [!UICONTROL ID de visitante] en una visita posterior (por ejemplo, después de la autenticación), la [!UICONTROL ID de visitante] efectiva se actualiza para que coincida con el valor personalizado. Esto provoca que la [!UICONTROL ID de visitante] efectiva cambie directamente después de la autenticación, lo que produce varios recuentos del visitante.

![](assets/visitors.png)

Después de la asociación inicial, los recuentos de visitas vuelven a la normalidad porque el visitante está asociado mediante la cookie [!UICONTROL ID de visitante]. Si más adelante el visitante ve el sitio y después se autentica, el recuento de visitantes no aumenta porque la [!UICONTROL ID de visitante] efectiva no cambia después de la autenticación.

![](assets/visitors_2.png)


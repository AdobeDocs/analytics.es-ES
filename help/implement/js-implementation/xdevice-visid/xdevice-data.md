---
description: Descripción general de cómo la identificación de visitantes en varios dispositivos afecta a los datos que se ven en los informes.
keywords: Analytics Implementation
solution: Analytics
subtopic: Visitors
title: Impacto de los datos de identificación de visitantes en varios dispositivos
topic: Developer and implementation
uuid: 1db4d149-cd50-4b41-a850-988901f25051
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Impacto de los datos de identificación de visitantes en varios dispositivos

>[!IMPORTANT]
>
>Ya no se recomienda este método de identificación de visitantes entre dispositivos. Consulte la documentación [de cooperación entre dispositivos de](https://marketing.adobe.com/resources/help/en_US/mcdc/)Adobe Experience Cloud.

Descripción general de cómo la identificación de visitantes en varios dispositivos afecta a los datos que se ven en los informes.

Para comprender cómo afecta esta función a la recopilación de datos, resulta útil comprender los campos de datos que hay en el perfil del visitante:

| Campo de datos | Descripción |
|---|---|
| Visitor ID cookie | ID que se genera automáticamente en la primera visita desde un dispositivo o explorador y que se almacena en la cookie `s_vi`. |
| Variable de ID de visitante | [!UICONTROL ID de visitante] opcional que se configura con la variable `s.visitorID`. Este valor se rellena después de autenticar a un usuario y podría coincidir con una ID que su empresa use para realizar el seguimiento de un usuario en varios canales de marketing digitales. |
| ID de visitante efectiva | La [!UICONTROL ID de visitante] efectiva es la ID real del perfil del usuario. Este valor se toma de la cookie de [!UICONTROL ID de visitante] o de la variable de [!UICONTROL ID de visitante] si se proporciona una. |


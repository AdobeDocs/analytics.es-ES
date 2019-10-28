---
description: Descripción general de cómo la identificación de visitantes en varios dispositivos afecta a los datos que se ven en los informes.
keywords: Implementación de Analytics
seo-description: Descripción general de cómo la identificación de visitantes en varios dispositivos afecta a los datos que se ven en los informes.
seo-title: Impacto de los datos de identificación de visitantes en varios dispositivos
solution: Analytics
subtopic: Visitantes
title: Impacto de los datos de identificación de visitantes en varios dispositivos
topic: Desarrollador e implementación
uuid: 1db4d149-cd50-4b41-a850-988901f25051
translation-type: ht
source-git-commit: 67cc404c4502b1b7be3f089538d8a28d5cf7f659

---


# Impacto de los datos de identificación de visitantes en varios dispositivos

>[!IMPORTANT]
>
>Ya no se recomienda este método de identificación de visitantes entre dispositivos. Consulte [Documentación de Adobe Experience Cloud Device Co-op](https://marketing.adobe.com/resources/help/es_ES/mcdc/).

Descripción general de cómo la identificación de visitantes en varios dispositivos afecta a los datos que se ven en los informes.

Para comprender cómo afecta esta función a la recopilación de datos, resulta útil comprender los campos de datos que hay en el perfil del visitante:

| Campo de datos | Descripción |
|---|---|
| Cookie de ID de visitante | ID que se genera automáticamente en la primera visita desde un dispositivo o explorador y que se almacena en la cookie `s_vi`. |
| Variable de ID de visitante | [!UICONTROL ID de visitante] opcional que se configura con la variable `s.visitorID`. Este valor se rellena después de autenticar a un usuario y podría coincidir con una ID que su empresa use para realizar el seguimiento de un usuario en varios canales de marketing digitales. |
| ID de visitante efectiva | La [!UICONTROL ID de visitante] efectiva es la ID real del perfil del usuario. Este valor se toma de la cookie de [!UICONTROL ID de visitante] o de la variable de [!UICONTROL ID de visitante] si se proporciona una. |


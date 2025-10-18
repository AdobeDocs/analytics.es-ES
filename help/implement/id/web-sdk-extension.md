---
title: Identificación de visitantes con la extensión de etiquetas Web SDK
description: Identifique correctamente a los visitantes al implementar la extensión de etiquetas Web SDK.
source-git-commit: 3055a76f797438be71e82ea8f73800dc82ff4805
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 0%

---

# Identificación de visitantes con la extensión de etiquetas Web SDK

La extensión de etiquetas Web SDK de la recopilación de datos de Adobe Experience Platform permite a las organizaciones implementar Web SDK mediante una interfaz de administración de etiquetas. Los escenarios avanzados, como el uso compartido de ID entre dominios y la migración de perfiles de visitantes, se configuran fácilmente mediante reglas y acciones de extensión. El uso de Web SDK afianza la implementación y admite actualizaciones sin problemas en Customer Journey Analytics.

Dado que el servicio de ID de visitante se copia de forma nativa en la extensión de etiqueta, solo requiere que establezca **[!UICONTROL Dominio de Edge]** en el valor deseado. Si este campo está configurado correctamente, la identificación del visitante funciona sin ninguna configuración adicional.

>[!NOTE]
>
>No incluya la extensión de etiqueta del servicio de ID de visitante si utiliza la extensión de etiqueta de Web SDK. La extensión de etiqueta del servicio de ID de visitante solo es necesaria si usa la [extensión de Adobe Analytics](analytics-extension.md).

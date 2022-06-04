---
title: Implementar Adobe Analytics mediante el SDK web de Adobe Experience Platform
description: Utilice la extensión del SDK web en la recopilación de datos de Adobe Experience Platform para enviar datos a Adobe Analytics.
source-git-commit: 6979736e1849d25af2141e0ab76a143605a90620
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 33%

---


# Implementar Adobe Analytics mediante el SDK web de Adobe Experience Platform

Puede usar la variable [SDK web de Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/sdk/overview.html?lang=es) para enviar datos a Adobe Analytics. Este método de implementación funciona traduciendo la variable [Modelo de datos de experiencia (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=es) en un formato utilizado por Analytics.

## Configuración

Para configurar Analytics para recibir datos XDM:

1. Instale y [configure](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=es) el [SDK web de Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=es).

1. Asegúrese de que los grupos de informes aplicables estén asignados a los datos que desee. Los datos XDM pasan automáticamente al grupo de informes desde Adobe Experience Edge.

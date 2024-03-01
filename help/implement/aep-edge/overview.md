---
title: Implementar Adobe Analytics con Adobe Experience Platform Edge
description: Información general sobre el uso de datos XDM de Experience Platform en Adobe Analytics
exl-id: 7d8de761-86e3-499a-932c-eb27edd5f1a3
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 9d9212313f54e4b44c5341754942ac0e0c78b84c
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 35%

---

# Implementar Adobe Analytics con Adobe Experience Platform Edge

Adobe Experience Platform Edge le permite enviar datos destinados a varios productos a una ubicación centralizada. Experience Edge reenvía la información adecuada a los productos deseados. Este concepto le permite consolidar los esfuerzos de implementación, especialmente abarcando varias soluciones de datos.

Adobe ofrece tres formas principales de enviar datos a Experience Edge:

* **[SDK web de Adobe Experience Platform](web-sdk/overview.md)**: Utilice la extensión del SDK web en la recopilación de datos de Adobe Experience Platform para enviar datos a Edge.
* **[SDK de Adobe Experience Platform Mobile](mobile-sdk/overview.md)**: Utilice la extensión del SDK móvil en la recopilación de datos de Adobe Experience Platform para enviar datos a Edge.
* **[API del servidor de red Adobe Experience Platform Edge](server-api/overview.md)**: envíe datos directamente a Edge mediante una API.



## Cómo gestiona Adobe Analytics los datos de Experience Edge

Los datos enviados a Experience Edge deben ajustarse a esquemas basados en [XDM (modelo de datos de experiencia)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=es). XDM le proporciona flexibilidad en los campos que se definen como parte de los eventos. En el momento en que los eventos llegan a Adobe Analytics, estos eventos se traducen en datos más estructurados que Adobe Analytics puede gestionar: vistas de página o eventos de vínculo.

XDM no receta cómo definir las vistas de página o los eventos de vínculo, ni indica a Adobe Analytics cómo tratar su carga útil. Por ejemplo, ciertos campos XDM listos para usar que parecen estar relacionados con vistas de página o eventos de vínculo, como `eventType`, `web.webPageDetails.pageViews`, o `web.webInteraction.linkEvents` no dependen totalmente de la implementación y no son relevantes para Adobe Analytics.

Para gestionar correctamente las vistas de página y los eventos de vínculo, se aplica la siguiente lógica a los datos enviados a la red de Adobe Experience Edge y reenviados a Adobe Analytics.

| La carga útil XDM contiene... | Adobe Analytics... |
|---|---|
| `web.webPageDetails.name` o `web.webPageDetails.URL` y no `web.webInteraction.type` | considera la carga útil como **vista de página** |
| `web.webInteraction.type` y (`web.webInteraction.name` o `web.webInteraction.url`) | considera la carga útil como **evento de vínculo** |
| `web.webInteraction.type` y (`web.webPageDetails.name` o `web.webPageDetails.url`) | considera la carga útil como **evento de vínculo** <br/>`web.webPageDetails.name` y `web.webPageDetails.URL` están configuradas como `null` |
| no `web.webInteraction.type` y (no `webPageDetails.name` y no `web.webPageDetails.URL`) | borra la carga útil e ignora los datos |

{style="table-layout:auto"}

Consulte la [Grupo de campos de esquema de extensión completa de Adobe Analytics ExperienceEvent](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/analytics-full-extension.html?lang=en) para obtener más información.

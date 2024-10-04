---
title: Implementar Adobe Analytics con Adobe Experience Platform Edge
description: Información general sobre el uso de datos XDM de Experience Platform en Adobe Analytics
exl-id: 7d8de761-86e3-499a-932c-eb27edd5f1a3
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: c7fd66e99fd7d6c474682621a3c18bf41d541a96
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 77%

---

# Implementación de Adobe Analytics con la red Edge de Adobe Experience Platform

La red Edge de Adobe Experience Platform le permite enviar datos destinados a varios productos a una ubicación centralizada. La red Edge reenvía la información adecuada a los productos deseados. Este concepto le permite consolidar los esfuerzos de implementación, especialmente abarcando varias soluciones de datos.

Adobe ofrece tres formas principales de enviar datos a la red Edge:

* **[SDK web de Adobe Experience Platform](web-sdk/overview.md)**: Utilice la extensión del SDK web en la recopilación de datos de Adobe Experience Platform para enviar datos a Edge.
* **[SDK de Adobe Experience Platform Mobile](mobile-sdk/overview.md)**: Utilice la extensión del SDK móvil en la recopilación de datos de Adobe Experience Platform para enviar datos a Edge.
* **[API de servidor de red de Adobe Experience Platform Edge](server-api/overview.md)**: envíe datos directamente a Edge mediante una API.



## Cómo gestiona Adobe Analytics los datos de la red Edge

Los datos enviados a la red Edge de Adobe Experience Platform pueden seguir dos formatos:

* Objeto XDM: conformar esquemas basados en [XDM (Modelo de datos de experiencia)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=es). XDM le proporciona flexibilidad en los campos que se definen como parte de los eventos. En el momento en que los eventos llegan a Adobe Analytics, se traducen a un formato que Adobe Analytics puede gestionar.
* Objeto de datos: envíe datos a la red Edge mediante campos específicos asignados a Adobe Analytics. La red Edge detecta la presencia de estos campos y los reenvía a Adobe Analytics sin necesidad de ajustarse a un esquema.

El Edge Network utiliza la siguiente lógica para determinar las vistas de página de Adobe Analytics y los eventos de vínculo:

| La carga útil XDM contiene... | Adobe Analytics... |
|---|---|
| `xdm.web.webPageDetails.name` o `xdm.web.webPageDetails.URL` y no `xdm.web.webInteraction.type` | considera que la carga útil es una **vista de página** |
| `xdm.eventType = web.webPageDetails.pageViews` | considera que la carga útil es una **vista de página** |
| `xdm.web.webInteraction.type` y (`xdm.web.webInteraction.name` o `xdm.web.webInteraction.url`) | considera que la carga útil es un **evento de vínculo** |
| `xdm.web.webInteraction.type` y (`xdm.web.webPageDetails.name` o `xdm.web.webPageDetails.url`) | considera la carga un **evento de vínculo** <br/>También establece `xdm.web.webPageDetails.name` y `xdm.web.webPageDetails.URL` en `null` |
| no `xdm.web.webInteraction.type` y (no `xdm.webPageDetails.name` y no `xdm.web.webPageDetails.URL`) | borra la carga útil e ignora los datos |

{style="table-layout:auto"}

Además de diferenciar las vistas de página y los clics en vínculos, se ha implementado la siguiente lógica que determina si ciertos eventos se clasifican como A4T o se descartan.

| La carga útil XDM contiene... | Adobe Analytics... |
| --- | --- |
| `xdm.eventType = display` o <br/>`xdm.eventType = decisioning.propositionDisplay` o <br/>`xdm.eventType = personalization.request` o <br/>`xdm.eventType = decisioning.propositionFetch` y `xdm._experience.decisioning` | considera la carga útil una llamada a **A4T**. |
| `xdm.eventType = display` o <br/>`xdm.eventType = decisioning.propositionDisplay` o <br/>`xdm.eventType = personalization.request` o <br/>`xdm.eventType = decisioning.propositionFetch` y no `xdm._experience.decisioning` | borra la carga útil e ignora los datos |
| `xdm.eventType = click` o `xdm.eventType = decisioning.propositionInteract` y `xdm._experience.decisioning` y no `web.webInteraction.type` | considera la carga útil una llamada a **A4T**. |
| `xdm.eventType = click` o `xdm.eventType = decisioning.propositionInteract` y no `xdm._experience.decisioning` y no `web.webInteraction.type` | borra la carga útil e ignora los datos. |

{style="table-layout:auto"}

Consulte [Grupo de campos de esquema de extensión completa de Adobe Analytics ExperienceEvent](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/analytics-full-extension.html?lang=es) para obtener más información.

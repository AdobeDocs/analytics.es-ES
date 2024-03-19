---
title: Implementar Adobe Analytics con Adobe Experience Platform Edge
description: Información general sobre el uso de datos XDM de Experience Platform en Adobe Analytics
exl-id: 7d8de761-86e3-499a-932c-eb27edd5f1a3
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 914b822aae659d1d0f0b8a98480090ead99e102a
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 46%

---

# Implementación de Adobe Analytics con Adobe Experience Platform Edge Network

Adobe Experience Platform Edge Network le permite enviar datos destinados a varios productos a una ubicación centralizada. La red perimetral reenvía la información adecuada a los productos deseados. Este concepto le permite consolidar los esfuerzos de implementación, especialmente abarcando varias soluciones de datos.

Adobe ofrece tres formas principales de enviar datos a la red perimetral:

* **[SDK web de Adobe Experience Platform](web-sdk/overview.md)**: Utilice la extensión del SDK web en la recopilación de datos de Adobe Experience Platform para enviar datos a Edge.
* **[SDK de Adobe Experience Platform Mobile](mobile-sdk/overview.md)**: Utilice la extensión del SDK móvil en la recopilación de datos de Adobe Experience Platform para enviar datos a Edge.
* **[API de servidor de red de Adobe Experience Platform Edge](server-api/overview.md)**: envíe datos directamente a Edge mediante una API.



## Cómo gestiona Adobe Analytics los datos de red perimetral

Los datos enviados a Adobe Experience Platform Edge Network pueden seguir dos formatos:

* Objeto XDM: conformar esquemas basados en [XDM (modelo de datos de experiencia)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=es). XDM le proporciona flexibilidad en los campos que se definen como parte de los eventos. En el momento en que los eventos llegan a Adobe Analytics, se traducen a un formato que Adobe Analytics puede gestionar.
* Objeto de datos: envíe datos a la red perimetral mediante campos específicos asignados a Adobe Analytics. La red perimetral detecta la presencia de estos campos y los reenvía a Adobe Analytics sin necesidad de ajustarse a un esquema.


Edge Network utiliza la siguiente lógica para determinar las vistas de página de Adobe Analytics y los eventos de vínculo

| La carga útil XDM contiene... | Adobe Analytics... |
|---|---|
| `web.webPageDetails.name` o `web.webPageDetails.URL` y no `web.webInteraction.type` | considera que la carga útil es una **vista de página** |
| `web.webInteraction.type` y (`web.webInteraction.name` o `web.webInteraction.url`) | considera que la carga útil es un **evento de vínculo** |
| `web.webInteraction.type` y (`web.webPageDetails.name` o `web.webPageDetails.url`) | considera que la carga útil es un **evento de vínculo** <br/>`web.webPageDetails.name` y `web.webPageDetails.URL` están establecidos en `null` |
| no `web.webInteraction.type` y (no `webPageDetails.name` y no `web.webPageDetails.URL`) | borra la carga útil e ignora los datos |

{style="table-layout:auto"}

Consulte la [Grupo de campos de esquema de extensión completa de Adobe Analytics ExperienceEvent](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/analytics-full-extension.html) para obtener más información.

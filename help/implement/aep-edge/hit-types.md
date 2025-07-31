---
title: Tipos de eventos de Edge Network en Adobe Analytics
description: Interpretación de los eventos recibidos de Edge Network por Adobe Analytics.
feature: Implementation Basics
role: Admin, Developer
source-git-commit: 8d369bd3be3ae9c075e490e108666728a2cff5dc
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 28%

---

# Tipos de eventos de Edge Network en Adobe Analytics

Adobe Analytics trata las visitas de forma diferente en función de las funciones que llame en AppMeasurement. Por ejemplo, [`s.t`](/help/implement/vars/functions/t-method.md) y [`s.tl`](/help/implement/vars/functions/tl-method.md) incluyen u omiten ciertas dimensiones e incrementan las vistas de página de forma diferente. Adobe Experience Platform solo contiene el comando `sendEvent`. Las propiedades específicas dentro de la carga útil `xdm` determinan cómo se interpretan esos datos en Adobe Analytics.

Edge Network utiliza la siguiente lógica para determinar las vistas de página de Adobe Analytics y los eventos de vínculo:

| La carga útil XDM contiene... | Adobe Analytics... |
|---|---|
| `xdm.web.webPageDetails.name` o `xdm.web.webPageDetails.URL` y no `xdm.web.webInteraction.type` | considera que la carga útil es una **vista de página** |
| `xdm.eventType = web.webPageDetails.pageViews` | considera que la carga útil es una **vista de página** |
| `xdm.web.webInteraction.type` y (`xdm.web.webInteraction.name` o `xdm.web.webInteraction.url`) | considera que la carga útil es un **evento de vínculo** |
| `xdm.web.webInteraction.type` y (`xdm.web.webPageDetails.name` o `xdm.web.webPageDetails.url`) | considera la carga un **evento de vínculo** <br/>También establece `xdm.web.webPageDetails.name` y `xdm.web.webPageDetails.URL` en `null` |
| no `xdm.web.webInteraction.type` y (no `xdm.webPageDetails.name` y no `xdm.web.webPageDetails.URL`) | borra la carga útil e ignora los datos |

Además de diferenciar las vistas de página y los clics en vínculos, se ha implementado la siguiente lógica que determina si ciertos eventos se clasifican como A4T o se descartan.

| La carga útil XDM contiene... | Adobe Analytics... |
| --- | --- |
| `xdm.eventType = display` o <br/>`xdm.eventType = decisioning.propositionDisplay` o <br/>`xdm.eventType = personalization.request` o <br/>`xdm.eventType = decisioning.propositionFetch` y `xdm._experience.decisioning` | considera la carga útil una llamada a **A4T**. |
| `xdm.eventType = display` o <br/>`xdm.eventType = decisioning.propositionDisplay` o <br/>`xdm.eventType = personalization.request` o <br/>`xdm.eventType = decisioning.propositionFetch` y no `xdm._experience.decisioning` | borra la carga útil e ignora los datos |
| `xdm.eventType = click` o `xdm.eventType = decisioning.propositionInteract` y `xdm._experience.decisioning` y no `web.webInteraction.type` | considera la carga útil una llamada a **A4T**. |
| `xdm.eventType = click` o `xdm.eventType = decisioning.propositionInteract` y no `xdm._experience.decisioning` y no `web.webInteraction.type` | borra la carga útil e ignora los datos. |

Consulte [Grupo de campos de esquema de extensión completa de Adobe Analytics ExperienceEvent](https://experienceleague.adobe.com/es/docs/experience-platform/xdm/field-groups/event/analytics-full-extension) para obtener más información.

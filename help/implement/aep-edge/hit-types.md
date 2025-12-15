---
title: Tipos de eventos de Edge Network en Adobe Analytics
description: Interpretación de los eventos recibidos de Edge Network por Adobe Analytics.
feature: Implementation Basics
role: Admin, Developer
exl-id: 31085025-9c38-4375-8dfb-4fded6542ca7
source-git-commit: 0096a53505b3b1bc925c813c2c6c11ee3c7ee0c0
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 20%

---

# Tipos de eventos de Edge Network en Adobe Analytics

Adobe Analytics trata las visitas de forma diferente en función de las funciones que llame en AppMeasurement. Por ejemplo, [`s.t`](/help/implement/vars/functions/t-method.md) y [`s.tl`](/help/implement/vars/functions/tl-method.md) incluyen u omiten ciertas dimensiones e incrementan [las vistas de página](/help/components/metrics/page-views.md) de manera diferente. Adobe Experience Platform solo contiene el comando [`sendEvent`](https://experienceleague.adobe.com/es/docs/experience-platform/collection/js/commands/sendevent/overview). Las propiedades específicas dentro de la carga útil [`xdm`](https://experienceleague.adobe.com/es/docs/experience-platform/collection/js/commands/sendevent/xdm) o [`data`](https://experienceleague.adobe.com/es/docs/experience-platform/collection/js/commands/sendevent/data) determinan cómo se interpretan esos datos en Adobe Analytics.

Edge Network usa la siguiente lógica para determinar las [vistas de página](/help/components/metrics/page-views.md) y los [eventos de vínculo](/help/components/metrics/page-events.md) de Adobe Analytics:

## Vistas de página y eventos de vínculo que utilizan el objeto `xdm`

| La carga útil XDM contiene... | Adobe Analytics... |
|---|---|
| `xdm.web.webPageDetails.name` o `xdm.web.webPageDetails.URL` y no `xdm.web.webInteraction.type` | considera que la carga útil es una **vista de página** |
| `xdm.eventType = web.webpagedetails.pageViews` | considera que la carga útil es una **vista de página** |
| `xdm.web.webInteraction.type` y (`xdm.web.webPageDetails.name` o `xdm.web.webPageDetails.URL`) | considera la carga un **evento de vínculo** <br/>También establece `xdm.web.webPageDetails.name` y `xdm.web.webPageDetails.URL` en `null` |
| `xdm.web.webInteraction.type` y (`xdm.web.webInteraction.name` o `xdm.web.webInteraction.URL`) | considera la carga útil un **evento de vínculo** <br/>También establece `xdm.web.webPageDetails.name` y `xdm.web.webPageDetails.URL` en `null` si están presentes |
| no `xdm.web.webInteraction.type` y no `xdm.web.webPageDetails.name` y no `xdm.web.webPageDetails.URL` | borra la carga útil e ignora los datos |

>[!TIP]
>
>Los nombres de campo XDM de la carga útil distinguen entre mayúsculas y minúsculas (por ejemplo, `webPageDetails.URL`). El campo `xdm.eventType` es un valor de cadena con su propio conjunto de valores aceptados, y es posible que el uso de mayúsculas y minúsculas en esos valores no coincida con los nombres de campo XDM. Para ver los valores aceptados, consulte el campo `eventType` en la clase [XDM ExperienceEvent](https://experienceleague.adobe.com/es/docs/experience-platform/xdm/classes/experienceevent#eventType).

+++Vista de página mínima con `xdm` campos

```json
{
  "xdm": {
    "web": {
      "webPageDetails": {
        "name": "Example page",
        "URL": "https://example.com/page"
      }
    }
  }
}
```

+++

+++Vista de página mínima con `xdm.eventType`

```json
{
  "xdm": {
    "eventType": "web.webpagedetails.pageViews"
  }
}
```

+++

+++Evento de vínculo mínimo con campos recomendados

```json
{
  "xdm": {
    "web": {
      "webInteraction": {
        "type": "other",
        "name": "Header nav: Pricing",
        "URL": "https://example.com/pricing"
      }
    }
  }
}
```

+++

## Vistas de página y eventos de vínculo que utilizan el objeto `data`

| La carga del objeto de datos contiene... | Adobe Analytics... |
|---|---|
| `data.__adobe.analytics.pageName` o `data.__adobe.analytics.pageURL` y no `data.__adobe.analytics.linkType` | considera que la carga útil es una **vista de página** |
| `data.__adobe.analytics.linkType` y (`data.__adobe.analytics.linkName` o `data.__adobe.analytics.linkURL`) | considera la carga un **evento de vínculo** <br/>También establece `data.__adobe.analytics.pageName` y `data.__adobe.analytics.pageURL` en `null` |
| no `data.__adobe.analytics.linkType` y no `data.__adobe.analytics.pageName` y no `data.__adobe.analytics.pageURL` | borra la carga útil e ignora los datos |

+++Vista de página mínima con `data` campos

```json
{
  "data": {
    "__adobe": {
      "analytics": {
        "pageName": "Example page",
        "pageURL": "https://example.com/page"
      }
    }
  }
}
```

+++

+++Evento de vínculo mínimo con `data` campos

```json
{
  "data": {
    "__adobe": {
      "analytics": {
        "linkType": "o",
        "linkName": "Header nav: Pricing",
        "linkURL": "https://example.com/pricing"
      }
    }
  }
}
```

+++

>[!NOTE]
>
>Si incluye un objeto `xdm` y un objeto `data` en la misma carga útil, Adobe Analytics comprueba ambos objetos para ver si tienen campos respectivos.

## Eventos relacionados con A4T y decisiones

Además de diferenciar las vistas de página y los eventos de vínculo, la siguiente lógica determina si determinados eventos de toma de decisiones se clasifican como A4T o se descartan.

| La carga útil XDM contiene... | Adobe Analytics... |
|---|---|
| `xdm.eventType = decisioning.propositionDisplay` y `xdm._experience.decisioning` | considera la carga útil una llamada a **A4T**. |
| `xdm.eventType = decisioning.propositionDisplay` y no `xdm._experience.decisioning` | borra la carga útil e ignora los datos |
| `xdm.eventType = decisioning.propositionInteract` y `xdm._experience.decisioning` y no `xdm.web.webInteraction.type` | considera la carga útil una llamada a **A4T**. |
| `xdm.eventType = decisioning.propositionInteract` y no `xdm._experience.decisioning` y no `xdm.web.webInteraction.type` | borra la carga útil e ignora los datos. |
| `xdm.eventType = decisioning.propositionFetch` | borra la carga útil e ignora los datos |

>[!TIP]
>
>Los siguientes `eventType` valores están en desuso. Tenga en cuenta que estos valores afectan a la lógica del mismo modo que sus equivalentes actuales:
>
>* El tipo de evento `display` está obsoleto. Utilice `decisioning.propositionDisplay` en su lugar.
>* El tipo de evento `click` está obsoleto. Utilice `decisioning.propositionInteract` en su lugar.
>* El tipo de evento `personalization.request` está obsoleto. Utilice `decisioning.propositionFetch` en su lugar.

+++Pantalla mínima de A4T

```json
{
  "xdm": {
    "eventType": "decisioning.propositionDisplay",
    "_experience": {
      "decisioning": {
        "propositions": [
          {
            "id": "example-proposition-id",
            "scope": "example-scope",
            "scopeDetails": { "decisionProvider": "AJO" }
          }
        ],
        "propositionEventType": { "display": 1 }
      }
    }
  }
}
```

+++

+++Interacción mínima con A4T

```json
{
  "xdm": {
    "eventType": "decisioning.propositionInteract",
    "_experience": {
      "decisioning": {
        "propositions": [
          {
            "id": "example-proposition-id",
            "scope": "example-scope",
            "scopeDetails": { "decisionProvider": "AJO" }
          }
        ],
        "propositionEventType": { "interact": 1 }
      }
    }
  }
}
```

+++

Consulte [Grupo de campos de esquema de extensión completa de Adobe Analytics ExperienceEvent](https://experienceleague.adobe.com/es/docs/experience-platform/xdm/field-groups/event/analytics-full-extension) para obtener más información.

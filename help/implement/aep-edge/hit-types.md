---
title: Tipos de eventos de Edge Network en Adobe Analytics
description: Cómo Adobe Analytics interpreta los eventos recibidos de Edge Network.
feature: Implementation Basics
role: Admin, Developer
exl-id: 31085025-9c38-4375-8dfb-4fded6542ca7
TQID: https://experienceleague.adobe.com/Bf-OnlQu7TFYb1V4uKCVVoQkaPP4MuhyVWSdgjlZ6e8
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 478
ht-degree: 100%

---

# Tipos de eventos de Edge Network en Adobe Analytics

Adobe Analytics trata las visitas de forma diferente dependiendo de las funciones que llame en AppMeasurement. Por ejemplo, [`s.t`](/help/implement/vars/functions/t-method.md) y [`s.tl`](/help/implement/vars/functions/tl-method.md) incluyen u omiten ciertas dimensiones e incrementan [las vistas de página](/help/components/metrics/page-views.md) de manera diferente. Adobe Experience Platform solo contiene el comando [`sendEvent`](https://experienceleague.adobe.com/es/docs/experience-platform/collection/js/commands/sendevent/overview). Las propiedades específicas dentro de la carga útil [`xdm`](https://experienceleague.adobe.com/es/docs/experience-platform/collection/js/commands/sendevent/xdm) o [`data`](https://experienceleague.adobe.com/es/docs/experience-platform/collection/js/commands/sendevent/data) determinan cómo se interpretan esos datos en Adobe Analytics.

Edge Network utiliza la siguiente lógica para determinar las [vistas de página](/help/components/metrics/page-views.md) de Adobe Analytics y los [eventos de vínculo](/help/components/metrics/page-events.md):

## Vistas de página y eventos de vínculo que utilizan el objeto `xdm`

| La carga útil XDM contiene... | Adobe Analytics... |
|---|---|
| `xdm.web.webPageDetails.name` o `xdm.web.webPageDetails.URL` y no `xdm.web.webInteraction.type` | considera que la carga útil es una **vista de página** |
| `xdm.eventType = web.webpagedetails.pageViews` | considera que la carga útil es una **vista de página** |
| `xdm.web.webInteraction.type` y (`xdm.web.webPageDetails.name` o `xdm.web.webPageDetails.URL`) | considera la carga útil un **evento de vínculo** <br/>También establece `xdm.web.webPageDetails.name` y `xdm.web.webPageDetails.URL` en `null` |
| `xdm.web.webInteraction.type` y (`xdm.web.webInteraction.name` o `xdm.web.webInteraction.URL`) | considera la carga útil un **evento de vínculo** <br/>También establece `xdm.web.webPageDetails.name` y `xdm.web.webPageDetails.URL` en `null` si están presentes |
| no `xdm.web.webInteraction.type`, ni `xdm.web.webPageDetails.name` ni tampoco `xdm.web.webPageDetails.URL` | pierde la carga útil e ignora los datos |

>[!TIP]
>
>Los nombres de campo XDM de la carga útil distinguen entre mayúsculas y minúsculas (por ejemplo, `webPageDetails.URL`). El campo `xdm.eventType` es un valor de cadena con su propio conjunto de valores aceptados, y es posible que el uso de mayúsculas y minúsculas en esos valores no coincida con los nombres de campo XDM. Para los valores aceptados, consulte el campo `eventType` en la [clase XDM ExperienceEvent](https://experienceleague.adobe.com/es/docs/experience-platform/xdm/classes/experienceevent#eventType).

+++Vista de página mínima mediante campos `xdm`

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

+++Vista de página mínima mediante `xdm.eventType`

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

| La carga útil del objeto de datos contiene... | Adobe Analytics... |
|---|---|
| `data.__adobe.analytics.pageName` o `data.__adobe.analytics.pageURL` y no `data.__adobe.analytics.linkType` | considera que la carga útil es una **vista de página** |
| `data.__adobe.analytics.linkType` y (`data.__adobe.analytics.linkName` o `data.__adobe.analytics.linkURL`) | considera la carga útil un **evento de vínculo** <br/>También establece `data.__adobe.analytics.pageName` y `data.__adobe.analytics.pageURL` en `null` |
| no `data.__adobe.analytics.linkType`, ni `data.__adobe.analytics.pageName` ni tampoco `data.__adobe.analytics.pageURL` | pierde la carga útil e ignora los datos |

+++Vista de página mínima mediante campos `data`

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

+++Evento de vínculo mínimo mediante campos `data`

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

## Eventos relacionados con A4T y la toma de decisiones

Además de diferenciar las vistas de página y los eventos de vínculo, la siguiente lógica determina si determinados eventos de toma de decisiones se clasifican como A4T o se descartan.

| La carga útil XDM contiene... | Adobe Analytics... |
|---|---|
| `xdm.eventType = decisioning.propositionDisplay` y `xdm._experience.decisioning` | considera la carga útil una llamada a **A4T**. |
| `xdm.eventType = decisioning.propositionDisplay` y no `xdm._experience.decisioning` | pierde la carga útil e ignora los datos |
| `xdm.eventType = decisioning.propositionInteract` o `xdm._experience.decisioning` y no `xdm.web.webInteraction.type` | considera la carga útil una llamada a **A4T**. |
| `xdm.eventType = decisioning.propositionInteract` y no `xdm._experience.decisioning` ni tampoco `xdm.web.webInteraction.type` | pierde la carga útil e ignora los datos. |
| `xdm.eventType = decisioning.propositionFetch` | pierde la carga útil e ignora los datos |

>[!TIP]
>
>Los siguientes valores `eventType` están obsoletos. Tenga en cuenta que estos valores afectan a la lógica del mismo modo que sus equivalentes actuales:
>
>* El tipo de evento `display` está obsoleto. Utilice `decisioning.propositionDisplay` en su lugar.
>* El tipo de evento `click` está obsoleto. Utilice `decisioning.propositionInteract` en su lugar.
>* El tipo de evento `personalization.request` está obsoleto. Utilice `decisioning.propositionFetch` en su lugar.

+++Visualización de A4T mínima

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

+++Interacción con A4T mínima

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

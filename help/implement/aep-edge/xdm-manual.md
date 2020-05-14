---
title: Asignación manual de datos XDM a Analytics
description: 'Asignación manual de datos XDM de la plataforma de experiencia a Adobe Analytics '
translation-type: tm+mt
source-git-commit: 717c3e23eb2c3fb2477bd77ea92a1dce744f02df
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 1%

---


# Asignación manual de datos XDM a Analytics

El SDK web de Adobe Experience Platform (AEP) incluye ayudas para ayudarle a asignar manualmente datos entre la plataforma y Analytics.

Para datos XDM que no se asignan automáticamente a Analytics, puede agregar datos [de](https://docs.adobe.com/content/help/en/analytics/implementation/vars/page-vars/contextdata.html) contexto para que coincidan con su [esquema](https://docs.adobe.com/content/help/en/experience-platform/xdm/schema/composition.html). A continuación, las reglas [de](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/t-processing-rules.html) procesamiento de Analytics pueden utilizarlas para rellenar las variables de Analytics.

Además, puede utilizar un conjunto predeterminado de acciones y listas de productos para enviar o recuperar datos con el SDK web de AEP. Para ello, consulte [Productos](https://docs.adobe.com/content/help/en/experience-platform/edge/implement/commerce.html).

## Datos de contexto

Para su uso en Analytics, los datos XDM se acoplan con notación de puntos y se ponen a disposición como `contextData`. La siguiente lista de pares de valores muestra un ejemplo de `context data`:

```javascript
{
          "bh": "900",
          "bw": "1680",
          "c": "24",
          "c.a.d.key.[0]": "value1",
          "c.a.d.key.[1]": "value2",
          "c.a.d.object.key1": "value1",
          "c.a.d.object.key2.[0]": "value2",
          "c.a.x.environment.browserdetails.javascriptenabled": "true",
          "c.a.x.environment.type": "browser",
          "cust_hit_time_gmt": "1579781427",
          "g": "http://example.com/home",
          "gn": "home",
          "j": "1.8.5",
          "k": "Y",
          "s": "1680x1050",
          "tnta": "218287:1:0|0,218287:1:0|2,218287:1:0|1,218287:1:0|32767,218287:1:0|1,218287:1:0|0,218287:1:0|1,218287:1:0|0,218287:1:0|1",
          "user_agent": "Mozilla/5.0 AppleWebKit/537.36 Safari/537.36",
          "v": "Y"
        }
```

## Reglas de procesamiento

Se puede acceder a todos los datos recopilados por la red Edge mediante reglas [de procesamiento](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/t-processing-rules.html). En Analytics, puede utilizar reglas de procesamiento para incorporar datos de contexto en variables de Analytics.

Por ejemplo, en la regla siguiente, Analytics está configurado para rellenar términos de búsqueda **interna (eVar2)** con los datos asociados con **a.x_atag.search.term(Context Data)**.

![](assets/examplerule.png)


## Esquema XDM

La plataforma de experiencias utiliza esquemas para describir la estructura de los datos de forma coherente y reutilizable. Al definir los datos de manera consistente en todos los sistemas, resulta más fácil conservar el significado y, por lo tanto, obtener valor de los datos. Los datos de contexto de Analytics funcionan con la estructura definida por esquema.

El siguiente ejemplo muestra cómo se puede utilizar el [`event` comando](https://docs.adobe.com/content/help/en/experience-platform/edge/fundamentals/tracking-events.html) con la `xdm` opción para enviar y recuperar datos con el SDK web de AEP. En este ejemplo, el `event` comando coincide con el Esquema [Detalles del comercio de](https://github.com/adobe/xdm/blob/1c22180490558e3c13352fe3e0540cb7e93c69ca/docs/reference/context/experienceevent-commerce.schema.md) ExperienceEvent para que se realice un seguimiento de productListItems `name` y `SKU` valores:


```
alloy("event",{
  "xdm":{
    "commerce":{
      "productViews":{
        "value":1
      }
    },
    "productListItems":[
      {
        "SKU":"HT105",
        "name":"Large Field Hat",
      },
      {
        "SKU":"HT104",
        "name":"Small Field Hat",
      }
    ]
  }
});
```

Para obtener más información sobre el seguimiento de eventos con el SDK web de AEP, consulte [Seguimiento de eventos](https://docs.adobe.com/content/help/en/experience-platform/edge/fundamentals/tracking-events.html).
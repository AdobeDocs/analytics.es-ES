---
title: Asignación manual de datos XDM a Analytics
description: Asignación manual de datos XDM de Experience Platform a Adobe Analytics
exl-id: 6d973b35-1558-435c-9ae5-80c012d4e7ba
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 84%

---

# Asignación manual de datos XDM a Analytics

El SDK web de Adobe Experience Platform (AEP) incluye ayudas para que pueda asignar manualmente datos entre Platform y Analytics.

Para datos XDM que no se asignan automáticamente a Analytics, puede agregar [datos de contexto](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/contextdata.html) para que coincidan con su [esquema](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html). A continuación, las [reglas de procesamiento](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/t-processing-rules.html) de Analytics pueden utilizarlas para rellenar variables de Analytics.

Además, puede utilizar un conjunto predeterminado de acciones y listas de productos para enviar o recuperar datos con el SDK web de AEP. Para ello, consulte [Productos](https://experienceleague.adobe.com/docs/experience-platform/edge/implement/commerce.html).

## Datos de contexto

Para que los utilice Analytics, los datos XDM se acoplan con notación de puntos y se ponen a disposición como `contextData`. La siguiente lista de pares de valores muestra un ejemplo de `context data`:

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

Se puede acceder a todos los datos recopilados por la red perimetral mediante [reglas de procesamiento](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/t-processing-rules.html). En Analytics, puede utilizar reglas de procesamiento para incorporar datos de contexto en variables de Analytics.

Por ejemplo, en la regla siguiente, Analytics está configurado para rellenar los **términos de búsqueda interna (eVar2)** con los datos asociados con **a.x_atag.search.term(Context Data)**.

![](assets/examplerule.png)


## Esquema XDM

Experience Platform utiliza esquemas para describir la estructura de los datos de una manera uniforme y reutilizable. Al definir los datos de manera uniforme en todos los sistemas, resulta más fácil conservar el significado y, por lo tanto, obtener valor de los datos. Los datos de contexto de Analytics funcionan con la estructura definida por esquema.

El siguiente ejemplo muestra cómo se puede utilizar el [`event` comando ](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html) con la opción `xdm` para enviar y recuperar datos con el SDK web de AEP. En este ejemplo, el comando `event` coincide con el [Esquema de detalles comerciales de ExperienceEvent](https://github.com/adobe/xdm/blob/1c22180490558e3c13352fe3e0540cb7e93c69ca/docs/reference/context/experienceevent-commerce.schema.md) para que se realice un seguimiento de productListItems `name` y de los valores de `SKU`:


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

Para obtener más información sobre el seguimiento de eventos con el SDK web de AEP, consulte [Seguimiento de eventos](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html).

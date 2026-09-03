---
title: Implementación con AMP
description: Implementar Adobe Analytics en páginas de AMP.
feature: Implementation Basics
exl-id: 51a2662e-2a24-48f1-b17a-d1e1a57a394b
role: Developer
TQID: https://experienceleague.adobe.com/lEnXPmYFhMOlvL-au9C-MtGiKY5b84ojYska3urtH1M
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: e6c28e30-8689-4bf4-8fa8-561343d308a9id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: a947d2d7f45d4155a61cbfe0f8110851cca32e60
workflow-type: tm+mt
source-wordcount: 939
ht-degree: 66%

---

# Implementación con AMP

[AMP](https://amp.dev) es un marco HTML de código abierto que proporciona una manera directa de crear páginas web de carga rápida y sencilla.

Dado que Adobe Analytics utiliza una biblioteca JavaScript para compilar y enviar una solicitud de imagen, es necesario realizar ajustes en la implementación para enviar datos a Adobe en páginas que utilicen AMP.

## Determinar qué método de implementación de Adobe Analytics en páginas que utilizan AMP

Adobe ha creado dos métodos para implementar Adobe Analytics en páginas que utilizan AMP. Ambos utilizan la etiqueta HTML `<amp-analytics>`. Consulte [amp-analytics](https://amp.dev/es/documentation/components/amp-analytics) en la documentación de AMP para obtener más información.

* **Usar la plantilla `"adobeanalytics"`**: construya la solicitud de Analytics directamente en la página
* **Use la plantilla `"analytics_nativeConfig"`**: use un iframe que contenga el mismo código de AppMeasurement que implementa en el sitio normal

La siguiente tabla compara estos dos métodos:

|   | **`"adobeanalytics"`plantilla** | **`"adobeanalytics_nativeConfig"`plantilla** |
|---|---|---|
| Recuentos de visitante/visita en un grupo de informes existente | Inflación alta | Inflación mínima |
| Usar un grupo de informes independiente | Recomendado | No es necesario |
| Visitantes nuevos frente a visitantes de retorno | No admitido | Admitido |
| Servicio de ID de visitante (`VisitorAPI.js`) | No admitido | Admitido |
| Seguimiento de vídeos y vínculos | Compatibilidad parcial | Aún no es compatible |
| Dificultad de implementación | Difícil | Relativamente fácil |
| Integraciones de Adobe CX Enterprise | No admitido | Compatibilidad parcial |

Valore los pros y los contras para poder elegir el mejor método de implementación para su organización.

>[!WARNING]
>
>No utilice las plantillas `"adobeanalytics"` y `"adobeanalytics_nativeConfig"` en la misma página con AMP. Si intenta hacerlo, puede generar errores en la consola del explorador y contar dos veces los visitantes.

## Método 1: usar la etiqueta `<amp-analytics>` con la plantilla `"adobeanalytics"`

La plantilla de seguimiento de `"adobeanalytics"` utiliza la etiqueta HTML `<amp-analytics>` para construir una solicitud de seguimiento directamente. Puede especificar solicitudes de visita que se activen en eventos de página específicos, como la página que se hace visible o al hacer clic. Es posible personalizar los eventos de clic para aplicar a ciertos ID de elemento o ciertas clases al especificar un selector. La plantilla se puede cargar al añadir `type="adobeanalytics"` a la etiqueta amp-analytics.

En el siguiente código de ejemplo, existen dos activadores definidos: `pageLoad` y `click`. El activador `pageLoad` se ejecuta cuando el documento se vuelve visible e incluye la variable `pageName` tal como se define en la sección `vars`. El segundo activador `click` se ejecuta al hacer clic en un botón. La variable `eVar1` se ha establecido para este evento con el valor `button clicked`.

```html
<amp-analytics type="adobeanalytics">
  <script type="application/json">
    {
      "requests": {
        "myClick": "${click}&v1=${eVar1}",
      },
      "vars": {
        "host": "example.data.adobedc.net",
        "reportSuites": "reportSuiteID1,reportSuiteID2",
        "pageName": "Adobe Analytics Using amp-analytics tag"
      },
      "triggers": {
        "pageLoad": {
          "on": "visible",
          "request": "pageview"
        },
        "click": {
          "on": "click",
          "selector": "button",
          "request": "myClick",
          "vars": {
            "eVar1": "button clicked"
          }
        }
      }
    }
  </script>
</amp-analytics>
```

La etiqueta `<amp-analytics>` admite sustituciones de variables para que AMP pueda proporcionar valores de datos que tiene en cuenta. Consulte [variables admitidas en `amp-analytics`](https://github.com/ampproject/amphtml/blob/main/extensions/amp-analytics/analytics-vars.md) en GitHub para obtener más información.

>[!NOTE]
>
>Las solicitudes de imagen enviadas a Adobe mediante este método no incluyen datos para muchos informes predeterminados (por ejemplo, explorador, tamaño de pantalla o referente). Si desea incluir esta información en las visitas, asegúrese de que se incluya como parte de la cadena de consulta de solicitud de imagen. Consulte [Parámetros de consulta de recopilación de datos](../validate/query-parameters.md) para obtener una lista completa de los parámetros de consulta de solicitudes de imagen y sus variables asociadas.

Adobe identifica a los visitantes mediante una función AMP integrada y establece la cookie `adobe_amp_id`. Este ID de visitante es único para cualquier otro ID establecido por Adobe Analytics. Se cuenta un visitante único diferente para cada CDN desde la que un visitante recupera contenido, lo que puede aumentar el recuento de visitantes únicos. Se recomienda encarecidamente utilizar un grupo de informes independiente para las páginas de AMP debido a la forma en que AMP identifica a los visitantes únicos. El servicio de ID de visitante de Adobe no es compatible.

Esta solución necesita que el servidor de seguimiento especificado en la propiedad `host` coincida con el servidor de seguimiento en su sitio principal. De esta manera, se respetan los controles de políticas de privacidad existentes. De lo contrario, cree una política de privacidad independiente para las páginas que utilicen AMP.

## Método 2: usar la etiqueta `<amp-analytics>` con la plantilla `"adobeanalytics_nativeConfig"`

La etiqueta `"adobeanalytics_nativeConfig"` es más fácil de implementar, ya que usa la misma metodología de etiquetado que usa en sus páginas web normales. Agregue lo siguiente a la etiqueta `amp-analytics`:

```html
<amp-analytics type="adobeanalytics_nativeConfig">
  <script type="application/json">
    {
      "requests": {
        "base": "https://${host}",
        "iframeMessage": "${base}/stats.html?campaign=${queryParam(campaign)}&pageURL=${ampdocUrl}&ref=${documentReferrer}"
      },
      "vars": {
        "host": "example.data.adobedc.net"
      },
      "extraUrlParams": {
      "pageName": "Example AMP page",
      "v1": "eVar1 example value"
      }
    }
 </script>
</amp-analytics>
```

También se necesita una página HTML alojada en los servidores web:

```html
<html>
  <head>
    <title>Stats Example</title>
    <script language="JavaScript" type="text/javascript" src="VisitorAPI.js"></script>
    <script language="JavaScript" type="text/javascript" src="AppMeasurement.js"></script>
  </head>
  <body>
    <script>
      var v_orgId = "INSERT-ORG-ID-HERE";
      var s_account = "examplersid1,examplersid2";
      var s_trackingServer = "example.data.adobedc.net";
      var visitor = Visitor.getInstance(v_orgId);
      visitor.trackingServer = s_trackingServer;
      var s = s_gi(s_account);
      s.account = s_account;
      s.trackingServer = s_trackingServer;
      s.visitorNamespace = s_visitorNamespace;
      s.visitor = visitor;
      s.pageName = s.Util.getQueryParam("pageName");
      s.eVar1 = s.Util.getQueryParam("v1");
      s.campaign = s.Util.getQueryParam("campaign");
      s.pageURL = s.Util.getQueryParam("pageURL");
      s.referrer = s.Util.getQueryParam("ref");
      s.t();
    </script>
  </body>
</html>
```

Este método envía datos a una página web de utilidades mediante parámetros de cadena de consulta que se agregan al parámetro de solicitud `iframeMessage` Se puede especificar cualquier nombre para estos parámetros de cadena de consulta, siempre y cuando la página `stats.html` esté configurada para recopilar los datos correspondientes de dichos parámetros.

La plantilla `"adobeanalytics_nativeConfig"` también agrega parámetros de cadena de consulta basados en las variables enumeradas en la sección `extraUrlParams` de la etiqueta `<amp-analytics>`. En el ejemplo anterior, se incluyen los parámetros `pageName` y `v1`.

>[!IMPORTANT]
>
>La página `stats.html` debe alojarse en un subdominio independiente en el que se aloja la AMP. El marco de AMP no permite iFrames del mismo subdominio en que la página AMP misma existe. Por ejemplo, si la AMP está alojada en `amp.example.com`, aloje la página `stats.html` en un subdominio independiente como `ampmetrics.example.com`.

Con este método, si un usuario excluye el seguimiento en su sitio principal, también opta por excluirse del seguimiento en todas sus AMP. El uso de esta página de utilidades también significa que AMP puede admitir el servicio de ID de visitante de Adobe. No se necesita un grupo de informes separado.

El seguimiento de vínculos y el seguimiento de vídeos no se pueden usar con este método. La etiqueta `iframeMessage` de AMP solo se puede cargar una vez por página, por lo que no se puede enviar ninguna otra solicitud de imagen después de que se cargue el marco. Este método también requiere más recursos de procesamiento para ejecutarse, lo que puede afectar al rendimiento del desplazamiento. Este método no afecta al tiempo de carga de la página, ya que todos los recursos se cargan asincrónicamente.

## Preguntas más frecuentes

**¿Cómo puedo diferenciar a los visitantes de AMP de otros en mis datos?**

Para todas las páginas de AMP, la dimensión [!UICONTROL Versión de JavaScript] recopila un valor similar a `AMP vX.X`. También puede establecer una dimensión personalizada en &quot;AMP&quot; para poder segmentar a estos visitantes.

**¿En qué se diferencia este método de implementación de los Artículos instantáneos de Facebook?**

Los Artículos instantáneos de Facebook admiten una solución similar al método `"adobeanalytics_nativeConfig"`. La página `stats.html` de este método puede satisfacer sus necesidades de análisis tanto para AMP como para FIA de forma simultánea. Para obtener más información sobre la implementación del seguimiento en FIA, consulte [Artículos instantáneos de Facebook](fb-instant-articles.md).

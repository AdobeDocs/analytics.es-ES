---
title: Implementación con AMP
description: Implementar Adobe Analytics en páginas de AMP.
translation-type: tm+mt
source-git-commit: 09b453c1b4cd8555c5d1718759003945f5c230c5
workflow-type: tm+mt
source-wordcount: '1061'
ht-degree: 100%

---


# Implementación con AMP

[AMP](https://amp.dev) es un marco HTML de código abierto que proporciona una manera directa de crear páginas web de carga rápida y sencilla.

Dado que Adobe Analytics utiliza una biblioteca JavaScript para compilar y enviar una solicitud de imagen, es necesario realizar ajustes en la implementación para enviar datos a Adobe en páginas que utilicen AMP.

## Determinar qué método de implementación de Adobe Analytics en páginas que utilizan AMP

Adobe ha creado dos métodos para implementar Adobe Analytics en páginas que utilizan AMP. Ambos utilizan la etiqueta HTML `<amp-analytics>`. Consulte la [etiqueta amp-analytics](https://github.com/ampproject/amphtml/tree/master/extensions/amp-analytics) en el GitHub ampproject para obtener más información.

* **Utilice la `"adobeanalytics"` plantilla de seguimiento**: Construya la solicitud de Analytics directamente en la página
* **Utilice la `"analytics_nativeConfig"` plantilla de seguimiento**: Utilice un iframe que contenga el mismo código de AppMeasurement que implementa en el sitio normal

La siguiente tabla compara estos dos métodos:

|  | **Plantilla “adobeanalytics”** | **Plantilla “adobeanalytics_nativeConfig”** |
|---|---|---|
| Recuentos de visitante/visita en un grupo de informes existente | Alta inflación | Mínima inflación |
| Usar un grupo de informes independiente | Recomendado | No necesario |
| Visitantes nuevos frente a visitantes de retorno | No admitido | Admitido |
| Servicio de ID de visitante | No admitido | Admitido |
| Seguimiento de vídeos y vínculos | Compatibilidad parcial | No admitido aún |
| Dificultad de implementación | Algo difícil | Relativamente fácil |
| Integraciones de Adobe Experience Cloud | No admitido | Compatibilidad parcial |

Valore los pros y los contras dentro de la organización para determinar qué método desea utilizar. Consulte [ejemplos de AMP](https://github.com/Adobe-Marketing-Cloud/mobile-services/tree/master/samples/mobile-web) en el repositorio GitHub de Adobe para obtener código de muestra.

>[!WARNING]
>
>No utilice las plantillas `"adobeanalytics"` y `"adobeanalytics_nativeConfig"` en la misma página con AMP. Si intenta hacerlo, puede generar errores en la consola del explorador y contar dos veces los visitantes.

## Método 1: Uso de la etiqueta amp-analytics con la plantilla “adobeanalytics”

La plantilla de seguimiento de `"adobeanalytics"` utiliza la etiqueta HTML `<amp-analytics>` para construir una solicitud de seguimiento directamente. Puede especificar solicitudes de visita que se activen en eventos de página específicos, como la página que se hace visible o al hacer clic. Es posible personalizar los eventos de clic para aplicar a ciertos ID de elemento o ciertas clases al especificar un selector. La plantilla se puede cargar al añadir `type="adobeanalytics"` a la etiqueta amp-analytics.

En el siguiente código de ejemplo, existen dos activadores definidos: `pageLoad` y `click`. El activador `pageLoad` se ejecuta cuando el documento se vuelve visible e incluye la variable `pageName` tal como se define en la sección `vars`. El segundo activador `click` se ejecuta al hacer clic en un botón. `eVar1` se establece para este evento con el valor `button clicked`.

```html
<amp-analytics type="adobeanalytics">
  <script type="application/json">
    {
      "requests": {
        "myClick": "${click}&v1=${eVar1}",
      },
      "vars": {
        "host": "example.data.adobedc.net",
        "reportSuites": "reportSuiteID",
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

En el activador `click`, se puede especificar un selector para garantizar que, cada vez que se haga clic en el elemento DOM específico (en este caso, cualquier botón), la solicitud `buttonClick` se active y se establezca automáticamente para denotar esta visita como una llamada de seguimiento de vínculos.

Además, `amp-analytics` admite una cantidad de sustituciones de variables de modo que AMP pueda proporcionar valores de datos que tiene en cuenta. Consulte [las variables admitidas en amp-analytics](https://github.com/ampproject/amphtml/blob/master/extensions/amp-analytics/analytics-vars.md) en GitHub para obtener más información.

>[!NOTE]
>
>Las solicitudes de imagen enviadas a Adobe mediante este método no incluyen datos para muchos informes predeterminados (por ejemplo, explorador, tamaño de pantalla o referente). Si desea incluir esta información en las visitas, asegúrese de que se incluya como parte de la cadena de consulta de solicitud de imagen. Consulte [Parámetros de consulta de recopilación de datos](../validate/query-parameters.md) para obtener más información.

Adobe identifica a los visitantes mediante una función AMP integrada y establece la cookie `adobe_amp_id`. Este ID de visitante es único para cualquier otro ID establecido por Adobe Analytics (por ejemplo, la cookie `s_vi`). El servicio de Adobe Experience Cloud ID no es compatible con este método de implementación.

>[!NOTE]
>
>AMP utiliza CDN para entregar contenido. Está estructurado para contar un visitante único diferente para cada CDN desde la que un visitante recupera contenido, lo que puede aumentar el recuento de visitantes únicos.

Se recomienda utilizar un grupo de informes independiente para las páginas de AMP debido a la forma en que AMP identifica a los visitantes únicos.

Esta solución necesita que el servidor de seguimiento especificado en la propiedad `host` coincida con el servidor de seguimiento en su sitio principal. De esta manera, se respetan los controles de políticas de privacidad existentes. De lo contrario, cree una política de privacidad independiente para las páginas que utilicen AMP.

## Método 2: Uso de la etiqueta amp-analytics con la plantilla “adobeanalytics_nativeConfig”

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
      var s_account = "examplersid";
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

La plantilla `"adobeanalytics_nativeConfig"` también agrega parámetros de cadena de consulta en función de las variables que aparecen en la lista de la sección `extraUrlParams` de la etiqueta amp-analytics. En el ejemplo anterior, se incluyen los parámetros `pageName` y `v1`.

>[!IMPORTANT]
>
>La página `stats.html` debe alojarse en un subdominio independiente en el que se aloja la AMP. El marco de AMP no permite iframes del mismo subdominio en que la página AMP misma existe. Por ejemplo, si la AMP está alojada en `amp.example.com`, aloje la página `stats.html` en un subdominio independiente como `ampmetrics.example.com`.

Con este método, si un usuario excluye el seguimiento en su sitio principal, también opta por excluirse del seguimiento en todas sus AMP. El uso de esta página de utilidades también significa que AMP puede admitir el servicio de Adobe Experience Cloud ID. No se necesita un grupo de informes separado.

El seguimiento de vínculos y el seguimiento de vídeos no se pueden usar con este método. La etiqueta `iframeMessage` de AMP solo se puede cargar una vez por página, por lo que no se puede enviar ninguna otra solicitud de imagen después de que se cargue el marco. Este método también requiere más recursos de procesamiento para ejecutarse, lo que puede afectar al rendimiento del desplazamiento. Este método no afecta al tiempo de carga de la página, ya que todos los recursos se cargan asincrónicamente.

## Preguntas más frecuentes

**¿Está disponible el seguimiento de vídeo para cualquiera de los métodos?**

No. El estándar de AMP solo admite activadores para “visible”, “click” y “timer”. Todavía no admite activadores explícitos para el seguimiento de vídeos que la etiqueta `amp-analytics` puede escuchar. Además, la plantilla `"adobeanalytics_nativeConfig"` solo se puede cargar una vez, por lo que las solicitudes de imagen posteriores después de cargar una página no son posibles.

**¿Cómo puedo diferenciar a los visitantes de AMP de otros en mis datos?**

Para todas las páginas de AMP, la dimensión [!UICONTROL Versión de JavaScript] recopila un valor similar a `AMP vX.X`. También puede establecer una dimensión personalizada en “AMP” para poder segmentar a estos visitantes.

**¿En qué se diferencia este método de implementación de los Artículos instantáneos de Facebook?**

Los Artículos instantáneos de Facebook admiten una solución similar al método `"adobeanalytics_nativeConfig"`. La página `stats.html` de este método puede satisfacer sus necesidades de análisis tanto para AMP como para FIA de forma simultánea. Para obtener más información sobre la implementación del seguimiento en FIA, consulte [Artículos instantáneos de Facebook](fb-instant-articles.md).

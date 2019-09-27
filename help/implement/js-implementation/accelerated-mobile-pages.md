---
description: Implemente el proyecto Accelerated Mobile Pages (AMP) en Adobe Analytics.
keywords: Implementación de Analytics;amp;amp-analytics;plantilla adobeanalytics;plantilla adobeanalytics_nativeConfig;rastreo de clics;inflación de visitantes;servicio de ID
seo-description: Implemente el proyecto Accelerated Mobile Pages (AMP) en Adobe Analytics.
seo-title: Accelerated Mobile Pages
solution: Analytics
title: Accelerated Mobile Pages
topic: Desarrollador e implementación
uuid: c86e4a80-7191-4ee7-ab20-787730026c4b
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Accelerated Mobile Pages

Implemente el proyecto Accelerated Mobile Pages (AMP) en Adobe Analytics.

AMP es un [proyecto de código abierto](https://www.ampproject.org/) que le permite crear páginas web para contenido estático que se procesa rápidamente. Esta función es ideal para los editores que deseen crear contenido optimizado para móviles una sola vez y que se cargue al instante en todas partes. Los temas incluyen:

* [Cómo funciona](../../implement/js-implementation/accelerated-mobile-pages.md#section_21C2836D63104794BCEBEECB6593AFBF)
* [Uso de la etiqueta amp-analytics con la plantilla “adobeanalytics”](../../implement/js-implementation/accelerated-mobile-pages.md#section_2E4EBF4EF623440D95DE98E78C47244E)
* [Uso de la etiqueta amp-analytics con la plantilla “adobeanalytics_nativeConfig”](../../implement/js-implementation/accelerated-mobile-pages.md#section_3556B68304A4492991F439885727E9FF)
* [Resumen](../../implement/js-implementation/accelerated-mobile-pages.md#section_4D8ED26084F249738A5C2BC66B933A07)
* [Preguntas frecuentes](../../implement/js-implementation/accelerated-mobile-pages.md#section_5F57AA2DE0C5452FB65241058A924C73)

**Documentación y ejemplos adicionales**

* [Documentación](https://www.ampproject.org/docs/get_started/about-amp.html) del proyecto AMP externo y de código abierto
* [Ejemplos](https://github.com/Adobe-Marketing-Cloud/mobile-services/tree/master/samples/mobile-web/amphtml) de configuración

## Cómo funciona {#section_21C2836D63104794BCEBEECB6593AFBF}

Las AMP tienen páginas HTML etiquetadas especialmente almacenadas en caché en la Web en diferentes redes de envío de contenido (CDN) de socios y editores participantes. De esta forma, el contenido AMP se envía desde la fuente más cercana posible con la menor latencia posible. Esto crea un desafío de análisis porque nunca se puede estar 100 % seguro de dónde se creará el contenido de un editor, y las cookies de terceros son problemáticas para la identificación de los visitantes.

Además, para reducir considerablemente el tamaño de la página y para acelerar el tiempo de carga de la página, las AMP restringen el uso de JavaScript y cookies. Si bien esto es ventajoso para el dispositivo móvil porque reduce la cantidad de procesamiento, también genera desafíos para la medición exacta de los visitantes únicos y para comprender la adquisición y retención de usuarios.

Para solucionar estos problemas, Adobe ha colaborado con socios y editores de AMP en dos opciones que un editor puede elegir para adaptarse de la mejor manera a sus necesidades comerciales, ambas con la etiqueta `amp-analytics`. The first approach uses the `"adobeanalytics"` tracking template to construct the Analytics request directly from within the AMP. The second approach uses the `"analytics_nativeConfig"` tracking template, which uses an iframe containing the AppMeasurement code you deploy on your normal site. La siguiente tabla nos proporciona una idea de las ventajas y desventajas de cada método.

|  | **Plantilla “adobeanalytics”** | ** Plantilla "adobeanalytics_nativeConfig"** |
|---|---|---|
| Recuentos de visitante/visita (en grupo de informes existente) | Alta inflación | Mínima inflación |
| Uso de un grupo de informes separado | Recomendado | No necesario |
| Visitantes nuevos frente a visitantes de retorno | No admitido | Admitido |
| Servicio de ID de visitante | No admitido | Admitido |
| Seguimiento de vínculos y vídeos | Compatibilidad parcial | No admitido aún |
| Dificultad de implementación | Algo difícil | Relativamente fácil |
| [!DNL Experience Cloud] integraciones | No admitido | Admitido con advertencias |

## Uso de la etiqueta amp-analytics con la plantilla “adobeanalytics” {#section_2E4EBF4EF623440D95DE98E78C47244E}

The `"adobeanalytics"`tracking template utilizes the `amp-analytics` tag to construct a tracking request directly. Using the `"adobeanalytics"` template in the `amp-analytics` tag, you can specify hit requests that fire on specific page events, like the page becoming visible or on a click (and in the future, video views and more). Es posible personalizar los eventos de clic para aplicar a ciertos ID de elemento o ciertas clases al especificar un selector. Adobe has made this easy to set up using the `"adobeanalytics"` template specifically designed for [!DNL Adobe Analytics]. You can load the template by adding `type="adobeanalytics"` to the amp-analytics tag.

En el siguiente código de ejemplo, existen dos activadores definidos: `pageLoad` y `click`. The `pageLoad` trigger will fire when the document becomes visible and will include the `pageName` variable as defined in the `vars section`. El segundo activador `click` se activará al hacer clic en un botón. `eVar 1` se configurará para este evento con el valor `button clicked`.

```
  <amp-analytics type="adobeanalytics"> 
  <script type="application/json"> 
  { 
        "requests": { 
      "myClick": "${click}&v1=${eVar1}", 
  }, 
  "vars": { 
      "host": "metrics.example.com", 
      "reportSuites": "reportSuiteID", 
      "pageName": "Adobe Analytics Using amp-analytics tag" 
  }, 
    "triggers": { 
      "pageLoad": { 
        "on": "visible", 
        "request": "pageView" 
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

En el activador `click`, se puede especificar un selector para garantizar que, cada vez que se haga clic en el elemento DOM específico (en este caso, cualquier botón), la solicitud `buttonClick` se active y se establezca automáticamente para denotar esta visita como un evento de no es de etapa (es decir, llamada `trackLink`).

Además, `amp-analytics` admite una cantidad de sustituciones de variables de modo que AMP pueda proporcionar valores de datos que tiene en cuenta. Para conocer todo acerca de estas posibilidades y más también, puede visitar: [documentación de variables de amp-analytics](https://github.com/ampproject/amphtml/blob/master/extensions/amp-analytics/analytics-vars.md).

Tenga en cuenta que, si desea incorporar tecnología o variables DOM (como browser, screen size, device, referrer, etc.), tendrá que agregarlas explícitamente a cualquier solicitud, ya que no se generan automáticamente para el usuario. [Aquí](https://marketing.adobe.com/resources/help/en_US/sc/implement/query_parameters.html) podrá encontrar la documentación de cada uno de nuestros parámetros de cadena de consulta disponibles que se usan para seguimiento.

Si inspecciona las vistas creadas por amp-analytics, verá que en cada solicitud Adobe ha incluido el parámetro de consulta `vid`. Establecemos `vid` de acuerdo con una función AMP integrada para establecer un ID de cookie de Analytics personalizado con el nombre `adobe_amp_id`. Este ID es independiente de los demás ID establecidos por [!DNL Adobe Analytics] en cualquier otra parte (por ejemplo, `s_vi cookie`) y crea nuevos visitantes en cualquier de grupo de informes al que se envían las visitas.

Existen algunas advertencias que se deben tener en cuenta. Al usar la etiqueta amp-analytics como se menciona más arriba, los visitantes serán independientes de su seguimiento normal, y como el AMP puede cargarse desde cualquier red de envío de contenido, se obtendrá un visitante único para cada CDN en la que un visitante vea este AMP (de allí se desprende la inflación de visitante que se mencionó anteriormente). For this reason, Adobe recommends that if you use the `"adobeanalytics"` template for `amp-analytics`, you put your data into a separate report suite specific to AMP. Also, the [!DNL Experience Cloud] ID service (formerly, *`visitor ID service`*) is not supported using this method, so if your business requires additional [!DNL Experience Cloud] integrations, or will in the future, this is probably not the option for you.

Finalmente y tal vez lo más importante, esta solución de `amp-analytics` requiere que el servidor de seguimiento especificado en la sección `vars` coincida con el servidor de seguimiento en su sitio principal. De esta manera, se respetan los controles de políticas de privacidad existentes. De lo contrario, debe crear una política de privacidad por separado solo para las AMP.

## Uso de la etiqueta amp-analytics con la plantilla “adobeanalytics_nativeConfig” {#section_3556B68304A4492991F439885727E9FF}

The `"adobeanalytics_nativeConfig"` tag is easier to implement, as it will use the same tagging methodology you use on your normal web pages. Para lograr esto, agregue lo siguiente a su etiqueta `amp-analytics`:

```
<amp-analytics type="adobeanalytics_nativeConfig"> 
 <script type="application/json"> 
 { 
  "requests": { 
   "base": "https://${host}", 
   "iframeMessage": "${base}/stats.html?campaign=${queryParam(campaign)}&pageURL=${ampdocUrl}&ref=${documentReferrer}" 
  }, 
  "vars": { 
   "host": "statshost.publishersite.com" 
  }, 
  "extraUrlParams": { 
   "pageName": "Adobe Analytics Using amp-analytics tag", 
   "v1": "eVar1 test value" 
  } 
 } 
 </script> 
</amp-analytics>  
```

Este método envía datos a una página web de utilidades mediante parámetros de cadena de consulta especiales que se agregan al parámetro de solicitud `iframeMessage`. En este caso, observe que hemos agregado la variable `ampdocUrl AMP` y `documentReferrer` a los parámetros de cadena de consulta `pageURL`, y hacemos referencia respectivamente a la solicitud `iframeMessage` más arriba. Se puede especificar cualquier nombre para estos parámetros de cadena de consulta extra, siempre y cuando la página [!DNL stats.html] (que se muestra más arriba) esté configurada para recopilar los datos correspondientes de dichos parámetros.

The `"adobeanalytics_nativeConfig"` template also adds query string parameters based on the variables listed in the `extraUrlParams` section of the amp-analytics tag. En este caso, se puede ver que hemos especificado los parámetros `pageName` y `v1`, que nuestra página [!DNL stats.html] usará.

Be aware that you can only use a single `amp-analytics` template at a time and can not use the `"adobeanalytics"` template as well as the `"adobeanalytics_nativeConfig"` template on the same AMP. Si intenta hacerlo, podría ver un error en la consola del explorador y se inflará erróneamente el recuento de visitantes.

```
<html> 
<head> 
<title>Stats Test</title> 
<script language="JavaScript" type="text/javascript" src="VisitorAPI.js"></script> 
<script language="JavaScript" type="text/javascript" src="AppMeasurement.js"></script> 
<html> 
<head> 
<title>Stats Test</title> 
<script language="JavaScript" type="text/javascript" src="VisitorAPI.js"></script> 
<script language="JavaScript" type="text/javascript" src="AppMeasurement.js"></script> 
</head> 
<body> 
<script> 
var v_orgId = "1234567@PublisherOrg"; 
var s_account = "reportSuite"; 
var s_trackingServer = "metrics.publisher.com"; 
var s_visitorNamespace = "publisherNamespace"; 
var visitor = Visitor.getInstance(v_orgId); 
visitor.trackingServer = s_trackingServer; 
var s = s_gi(s_account); 
s.account = s_account; 
s.trackingServer = s_trackingServer; 
s.visitorNamespace = s_visitorNamespace; 
s.visitor = visitor; 
s.pagename = s.Util.getQueryParam("pageName"); 
s.eVar1=s.Util.getQueryParam("v1"); 
s.campaign=s.Util.getQueryParam("campaign"); 
s.pageURL=s.Util.getQueryParam("pageURL"); 
s.referrer=s.Util.getQueryParam(“ref”); 
s.t(); 
</script> 
</body> 
</html> 
```

Como se muestra más arriba, puede usar o vincular a su [!DNL VisitorAPI.js] y [!DNL AppMeasurement.js] existentes (como en nuestro ejemplo), o lo que use su implementación existente y luego usar los parámetros de configuración correctos. Para capturar los valores correctos en las variables correctas, se puede usar la función `s.Util.getQueryParam` proporcionada para obtener los valores pasados desde la dirección URL `iframeMessage` y establecer las variables adecuadas, tal como se haría en una página típica. If you use tag management software like Adobe's [ [!DNL Dynamic Tag Manager] ](https://www.adobe.com/solutions/digital-marketing/dynamic-tag-management.html), the query string parameters should be straightforward to capture. En este caso, `s.pageName` se establece con el valor pasado en el parámetro de cadena de consulta `pageName`. Aquí el nombre de la página debería establecerse en *`Adobe Analytics Example 2`*.

>[!IMPORTANT]
>
>Due to restrictions on iframes in the AMP framework, your [!DNL stats.html] page must be hosted on a separate subdomain from the domain the AMP itself is hosted on. El marco de AMP no permite iframes del mismo subdominio en que la página AMP misma existe. Por ejemplo, si la AMP está alojada en [!DNL amp.example.com], asegúrese de alojar la página [!DNL stats.html] en un subdominio separado como [!DNL ampmetrics.example.com] o algo similar.

Como la página de utilidad está alojada en su sitio original, no se necesita trabajo adicional para admitir la política de privacidad existente en todas las AMP. Esto significa que si un usuario final no opta por el seguimiento en el sitio primario, tampoco opta por el seguimiento en todas las AMP, sin que se requieran pasos adicionales. Usar esta página de utilidad también significa que AMP puede admitir el servicio de [!DNL Experience Cloud] ID de Adobe de modo que se pueda integrar la medición capturada en las AMP con el resto de [!DNL Experience Cloud] (para publicidad de destino con [!DNL Adobe Audience Manager] por ejemplo).

Para reiterar, si la organización aún no está usando el servicio de [!DNL Experience Cloud] ID (o tiene software de Tag Management como [!DNL Dynamic Tag Manager] de Adobe), puede etiquetar la página [!DNL stats.html] de cualquier modo que desee. Use su implementación existente como punto de referencia. La única diferencia con respecto a la implementación estándar es que usted recibirá los puntos de datos correspondientes desde la dirección URL `iframeMessage` de amp-analytics (o [!DNL document.URL] desde la página [!DNL stats.html]) para cada una de las variables que desea establecer. Además, si desea usar algunas de las [variables específicas de AMP](https://github.com/ampproject/amphtml/blob/master/extensions/amp-analytics/analytics-vars.md) (como se menciona más arriba) como referrer de AMP o page URL de AMP, inclúyalas en el objeto iframeMessage como se muestra en nuestro ejemplo más arriba.

Si bien esta solución es muy flexible, existen algunas advertencias. Debido a las restricciones inherentes en `amp-analytics``iframeMessage` , , solo se puede cargar cuando la página se carga una vez. This means you will not be able to do link tracking or video tracking with the `"adobeanalytics_nativeConfig"` template. Moreover, some DOM values that are typically captured automatically by our [!DNL AppMeasurement] code, such as `referrer` (which impacts the Search Engine Keyword reports, Referrer, and Referrer Type reports, or may include a marketing campaign tracking code) will have to be passed manually to the `iframeMessage` using whatever AMP variables [are available](https://github.com/ampproject/amphtml/blob/master/extensions/amp-analytics/analytics-vars.md). Por este motivo, Adobe recomienda establecer una variable personalizada con la AMP de valor si establece datos de AMP en un grupo de informes, de modo que pueda segmentar el tráfico de AMP al visualizar los informes antes mencionados. Tras ello, los informes de tecnología estándar, como explorador, dispositivo, tamaño o resolución de pantalla, deberían funcionar automáticamente.

Finalmente, como el iframe se carga como una página por separado y ejecuta completamente el JavaScript en esa página, la AMP no es tan liviana como el estándar de AMP que se pretende. Es decir, esto no afecta al tiempo de carga de página (el iframe se carga después de que la página termine de cargarse), pero la CPU y la red estarían realizando más actividades de lo habitual, lo que podría influir en la fluidez de desplazamiento. En la práctica, no hemos visto un gran impacto, pero estamos trabajando con Google para minimizar el impacto en la experiencia del usuario de este método.

## Resumen {#section_4D8ED26084F249738A5C2BC66B933A07}

If you need click tracking and don't mind visitors being counted as entirely new visitors separate from your site, use the `"adobeanalytics"` tracking template, with our recommendation that you put the data into a *`separate report suite`*. If you need the [!DNL Experience Cloud] ID service, do not want visitor or visit inflation, and are okay with only firing Analytics on page load, we recommend using the `"adobeanalytics_nativeConfig"` solution.

En Adobe Analytics hay satisfacción por asociarse con Google, y nuestros editores están igualmente satisfechos de proporcionar funciones de análisis líderes en la industria a editores en la Web móvil para una experiencia de usuario increíblemente veloz. Aunque estas dos soluciones actualmente ofrecen sus propias contrapartidas, estamos comprometidos con construir la mejor solución a largo plazo para responder a las cambiantes necesidades de análisis que tienen nuestros clientes.

El proyecto de AMP avanza con rapidez y hay cambios con mucha frecuencia. Por lo tanto, consulte [aquí](https://github.com/Adobe-Marketing-Cloud/mobile-services/tree/master/samples/mobile-web/amphtml) las actualizaciones de nuestros ejemplos. Lo que hemos mostrado aquí debería bastar para comenzar, pero se esperan cambios a medida que continuamos mejorando nuestras integraciones y a medida que más editores adoptan AMP con el paso del tiempo.

Si tiene preguntas o problemas, comuníquese con el Consultor o el servicio de atención al cliente de Adobe.

## Preguntas frecuentes {#section_5F57AA2DE0C5452FB65241058A924C73}

<table id="table_9A2ED5E482E8423CB54F99613C04BEA0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pregunta </th> 
   <th colname="col2" class="entry"> Respuesta </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> ¿Está disponible el seguimiento de vídeos para la plantilla <code>“adobeanalytics”</code> o <code>“adobeanalytics_nativeConfig”</code>? </p> </td> 
   <td colname="col2"> <p> Aún no lamentablemente. El estándar de AMP admite solo activadores para “visible”, “click” y “timer”, y aún no admite activadores explícitos para seguimiento de vídeos que una etiqueta amp-analytics puede escuchar. Además, como la etiqueta <code>“adobeanalytics_nativeConfig”</code> únicamente puede cargarse una sola vez, no es compatible con la visualización de vídeo que ocurre tras la carga de la AMP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Se menciona que la inflación de visitantes es más baja para la plantilla <code>“adobeanalytics_nativeConfig”</code> en la comparación. ¿Qué significa eso? ¿Qué causaría inflación de visitantes en las soluciones <code>“adobeanalytics”</code> o <code>“adobeanalytics_nativeConfig”</code>? </p> </td> 
   <td colname="col2"> <p>La plantilla <code>“adobeanalytics”</code> no permite a Adobe Analytics establecer una cookie de identificación de visitante, lo que significa que todas las visitas y visitantes de su página de AMP se considerarán como nuevos e independientes en el grupo de informes. </p> <p>Por su parte, la plantilla <code>“adobeanalytics_nativeConfig”</code> permite establecer la cookie de identificación de visitantes de Adobe Analytics en casi todos los casos, salvo en el de nuevos visitantes que utilicen el explorador Safari. Esto significa que cualquier visitante de Safari que no haya visitado previamente el sitio de un publicador quedará inflado en los informes de Adobe Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>¿Debería usar un grupo de informes separado para las AMP? </p> </td> 
   <td colname="col2"> <p>Recomendamos usar un grupo de informes separado para las AMP si usa la plantilla adobeanalytics, debido al problema de inflación de visitantes o visitas. Sin embargo, también estableceremos la versión de JavaScript en “AMP vX.X” desde la plantilla de etiqueta amp-analytics de modo que se pueda segmentar el tráfico fuera de un grupo de informes combinado si es necesario. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>¿Qué es el servicio de <span class="keyword">Experience Cloud ID</span>? ¿Lo necesito? </p> </td> 
   <td colname="col2"> <p>El servicio de <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> identidad </a> (anteriormente <span class="term"> servicio de ID de visitante </span>) habilita <span class="keyword"> los servicios principales de Experience Cloud </span> y permite integraciones entre diferentes soluciones de Adobe <span class="keyword"> Experience Cloud </span> . Si tiene integraciones con <span class="keyword">Adobe Audience Manager</span> o <span class="keyword">Adobe Target</span>, posiblemente esté usando este servicio. Este servicio también es la base de muchas funciones de <span class="keyword">Adobe Analytics</span> que vendrán. Si necesita soporte de servicio de ID o lo necesitará más adelante, recomendamos usar la solución <code>iframeMessage</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para la plantilla <code>“adobeanalytics_nativeConfig”</code>, ¿dónde debería alojar mi página de utilidad? </p> </td> 
   <td colname="col2"> <p>El estándar de AMP no permite que los iframes se carguen desde el dominio y subdominio exactos de la AMP. Como tal, recomendamos alojar la página de utilidad en un subdominio separado del sitio principal, especialmente si la empresa tiene su propia CDN donde planea almacenar en caché las AMP. Para conseguir la máxima compatibilidad, elija un subdominio como <span class="filepath">ampmetrics.publisher.com</span> que esté alejado de la ubicación donde residirá el contenido de AMP real. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>¿Esto no es similar a <span class="keyword">Artículos Instantáneos de Facebook</span>? ¿Cómo configuro <span class="keyword">Adobe Analytics</span> con Artículos Instantáneos de Facebook? </p> </td> 
   <td colname="col2"> <p> Los Artículos Instantáneos de Facebook admiten una solución similar a la solución de nativeConfig que se describe más arriba. De hecho, la página stats.html creada más arriba puede satisfacer las necesidades de análisis tanto para AMP como para FIA en simultáneo. Para obtener más información sobre la implementación de seguimiento en FIA, consulte <a href="../../implement/js-implementation/analytics-facebook-instant-articles.md#concept_AC9AD1431CD14F919E329A161A80AA08" format="dita" scope="local"> Artículos Instantáneos de Facebook </a> </p> </td> 
  </tr> 
 </tbody> 
</table>


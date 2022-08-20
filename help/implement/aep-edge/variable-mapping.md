---
title: Asignación de variables de Analytics en Adobe Experience Edge
description: Vea qué campos XDM de Edge se asignan automáticamente a variables de Analytics.
exl-id: fbff5c38-0f04-4780-b976-023e207023c6
source-git-commit: 4fedc1d27a03d4376103e4648e1e66cbd62346af
workflow-type: tm+mt
source-wordcount: '1381'
ht-degree: 97%

---

# Asignación de variables de Analytics en Adobe Experience Edge

La tabla siguiente muestra las variables que Adobe Experience Platform Edge Network asigna automáticamente a Adobe Analytics. Si utiliza estas rutas de campo XDM, no es necesaria ninguna configuración adicional para enviar datos a Adobe Analytics.

| Ruta de campo XDM | Dimensión y descripción de Analytics |
| --- | --- |
| `application.isClose` | Ayuda a definir la métrica móvil [Bloqueos](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html?lang=es#metrics). |
| `application.isInstall` | Ayuda a determinar cuándo aumentar la métrica móvil [Primeros lanzamientos](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `application.isLaunch` | Ayuda a determinar cuándo aumentar la métrica móvil [Primeros lanzamientos](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `application.closeType` | Determina si un evento de cierre es un bloqueo o no. Los valores válidos incluyen `close` (finaliza la sesión del ciclo vital y se recibió un evento de pausa para la sesión anterior) y `unknown` (una sesión de ciclo vital termina sin un evento de pausa). Ayuda a establecer la métrica [Bloqueos](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `application.isInstall` | La métrica móvil [Instalaciones](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `application.isLaunch` | La métrica móvil [Lanzamientos](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `application.name` | Ayuda a establecer el [ID de la aplicación](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html?lang=es#dimensions) de la dimensión móvil. |
| `application.isUpgrade` | La métrica móvil [Actualizaciones](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `application.version` | Ayuda a establecer el [ID de la aplicación](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions) de la dimensión móvil. |
| `application.sessionLength` | La métrica móvil [Duración anterior de la sesión](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `commerce.checkouts.id` | Aplica [serialización de eventos](../vars/page-vars/events/event-serialization.md) a la métrica [Cierres de compra](../../components/metrics/checkouts.md). |
| `commerce.checkouts.value` | Aumenta el valor de la métrica [Cierres de compra](../../components/metrics/checkouts.md) por la cantidad deseada. |
| `commerce.order.currencyCode` | Establece la variable de configuración [currencyCode](../vars/config-vars/currencycode.md). |
| `commerce.order.purchaseID` | Establece la variable de página [purchaseID](../vars/page-vars/purchaseid.md). |
| `commerce.productListAdds.id` | Aplica [serialización de eventos](../vars/page-vars/events/event-serialization.md) a la métrica [Adiciones al carro de compras](../../components/metrics/cart-additions.md). |
| `commerce.productListAdds.value` | Aumenta la métrica [Adiciones al carro de compras](../../components/metrics/cart-additions.md). |
| `commerce.productListOpens.id` | Aplica [serialización de eventos](../vars/page-vars/events/event-serialization.md) a la métrica [Carros de compras](../../components/metrics/carts.md). |
| `commerce.productListOpens.value` | Aumenta la métrica [Carros de compras](../../components/metrics/carts.md). |
| `commerce.productListRemovals.id` | Aplica [serialización de eventos](../vars/page-vars/events/event-serialization.md) a la métrica [Eliminaciones del carro de compras](../../components/metrics/cart-removals.md). |
| `commerce.productListRemovals.value` | Aumenta la métrica [Eliminaciones del carro de compras](../../components/metrics/cart-removals.md). |
| `commerce.productListViews.id` | Aplica [serialización de eventos](../vars/page-vars/events/event-serialization.md) a la métrica [Vistas del carro de compras](../../components/metrics/cart-views.md). |
| `commerce.productListViews.value` | Aumenta la métrica [Vistas del carro de compras](../../components/metrics/cart-views.md). |
| `commerce.productViews.id` | Aplica [serialización de eventos](../vars/page-vars/events/event-serialization.md) a la métrica [Vistas del producto](../../components/metrics/product-views.md). |
| `commerce.productViews.value` | Aumenta la métrica [Vistas del producto](../../components/metrics/product-views.md). |
| `commerce.purchases.value` | Aumenta la métrica [Compras](../../components/metrics/orders.md). |
| `device.model` | Dimensión móvil [Nombre del dispositivo](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions). |
| `device.colorDepth` | Ayuda a establecer la dimensión [Profundidad de color](../../components/dimensions/color-depth.md). |
| `device.screenHeight` | Ayuda a establecer la dimensión [Resolución del monitor.](../../components/dimensions/monitor-resolution.md) |
| `device.screenWidth` | Ayuda a establecer la dimensión [Resolución del monitor.](../../components/dimensions/monitor-resolution.md) |
| `device.type` | Tipo de dispositivo móvil. |
| `environment.browserDetails.acceptLanguage` | Ayuda a establecer la dimensión [Idioma](../../components/dimensions/language.md). |
| `environment.browserDetails.cookiesEnabled` | Establece dimensión [Compatibilidad con cookies](../../components/dimensions/cookie-support.md). Los valores válidos incluyen `Y` (el explorador acepta cookies) y `N` (el explorador rechaza las cookies). |
| `environment.browserDetails.javaEnabled` | Establece la dimensión [Habilitado para Java](../../components/dimensions/java-enabled.md). Los valores válidos incluyen `Y` (Java está habilitado) y `N` (Java está deshabilitado). |
| `environment.browserDetails.userAgent` | Se utiliza como método de identificación alternativo [visitante único](../../components/metrics/unique-visitors.md). Normalmente se rellena usando el encabezado de solicitud HTTP `User-Agent`. Puede asignar este campo a una eVar si desea utilizarlo en los informes. |
| `environment.browserDetails.viewportHeight` | Establece la dimensión [Altura del explorador](../../components/dimensions/browser-height.md). |
| `environment.browserDetails.viewportWidth` | Establece la dimensión [Anchura del explorador](../../components/dimensions/browser-width.md). |
| `environment.carrier` | La dimensión móvil [Nombre del operador](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions). |
| `environment.connectionType` | Ayuda a establecer la dimensión [Tipo de conexión](../../components/dimensions/connection-type.md). |
| `environment.ipV4` | Se utiliza como método de identificación alternativo [visitante único](../../components/metrics/unique-visitors.md). Normalmente se rellena usando el encabezado HTTP `X-Forwarded-For`. |
| `environment.language` | La configuración regional de la dimensión móvil. |
| `environment.operatingSystem` | El [sistema operativo](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions) de la dimensión móvil. |
| `environment.operatingSystemVersion` | Ayuda a establecer la dimensión [Versión del sistema operativo](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions). |
| `_experience.analytics.customDimensions.`<br/>`eVars.eVar1` -<br/>`_experience.analytics.customDimensions.`<br/>`eVars.eVar250` | Establece la dimensión respectiva [eVar](../../components/dimensions/evar.md). |
| `_experience.analytics.customDimensions.`<br/>`listProps.prop1.delimiter` -<br/>`_experience.analytics.customDimensions.`<br/>`listProps.prop75.delimiter` | El delimitador utilizado para un [Prop de lista](../vars/page-vars/prop.md#list-props). |
| `_experience.analytics.customDimensions.`<br/>`listProps.prop1.values` -<br/>`_experience.analytics.customDimensions.`<br/>`listProps.prop75.values` | Una matriz de cadenas que contiene los valores respectivos [Prop de lista](../vars/page-vars/prop.md#list-props). |
| `_experience.analytics.customDimensions.`<br/>`lists.list1.list[].value` -<br/>`_experience.analytics.customDimensions.`<br/>`lists.list3.list[].value` | Concatena todo `value` cadenas en cada `list[]` arreglo de discos a su respectivo [Variable de lista](../vars/page-vars/list.md) uso de delimitadores de coma. |
| `_experience.analytics.customDimensions.`<br/>`props.prop1` -<br/>`_experience.analytics.customDimensions.`<br/>`props.prop75` | Establece las dimensiones respectivas [Prop](../../components/dimensions/prop.md). |
| `_experience.analytics.event1to100.`<br/>`event1.id` -<br/>`_experience.analytics.event901to1000.`<br/>`event1000.id` | Aplica la [serialización de eventos](../vars/page-vars/events/event-serialization.md) a la métrica respectiva [Eventos personalizados](../../components/metrics/custom-events.md). |
| `_experience.analytics.event1to100.`<br/>`event1.value` -<br/>`_experience.analytics.event901to1000.`<br/>`event1000.value` | Incrementa la métrica respectiva [Eventos personalizados](../../components/metrics/custom-events.md) por la cantidad deseada. |
| `identityMap.ECID[0].id` | El [Adobe Experience Cloud ID](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=es). |
| `marketing.trackingCode` | Establece la dimensión [Código de seguimiento](../../components/dimensions/tracking-code.md). |
| `media.mediaTimed.completes.value` | El [contenido completado](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=es#content-complete) de la métrica Media Analytics. |
| `media.mediaTimed.dropBeforeStart.value` | `c.a.media.view`, `c.a.media.timePlayed`, `c.a.media.play` |
| `media.mediaTimed.federated.value` | Los [datos federados](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=es#federated-data) de la métrica Media Analytics. |
| `media.mediaTimed.firstQuartiles.value` | El [marcador de progreso del 25 %](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=es#twenty-five-progress-marker) de la métrica Media Analytics. |
| `media.mediaTimed.mediaSegmentView.value` | Las [vistas de segmentos de contenido](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=es#content-segment-views) de la métrica Media Analytics. |
| `media.mediaTimed.midpoints.value` | El [marcador de progreso del 50 %](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=es#fifty-progress-marker) de la métrica Media Analytics. |
| `media.mediaTimed.pauseTime.value` | La [duración total de la pausa](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=es#total-pause-duration) de la métrica Media Analytics. |
| `media.mediaTimed.pauses.value` | Las [pausas de eventos](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=es#pause-events) de la métrica Media Analytics. |
| `media.mediaTimed.primaryAssetReference.`<br/>`@id` | El [ID del recurso](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=es#asset-id) de la dimensión Media Analytics. |
| `media.mediaTimed.primaryAssetReference.`<br/>`dc:title` | El [nombre del vídeo](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=es#video-name) de la dimensión Media Analytics. |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Creator[N].iptc4xmpExt:Name` | El [creador](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=es#originator) de la dimensión Media Analytics. |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Episode.iptc4xmpExt:Number` | El [episodio](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=es#episode) de la dimensión Media Analytics. |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Genre` | El [género](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=es#genre) de la dimensión Media Analytics. |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Rating[N].iptc4xmpExt:RatingValue` | La [clasificación del contenido](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=es#content-rating) de la dimensión Media Analytics. |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Season.iptc4xmpExt:Number` | La [temporada](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=es#season) de la dimensión Media Analytics. |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Series.iptc4xmpExt:Identifier` | El [ID de contenido](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=es#content-id) de la dimensión Media Analytics. |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Series.iptc4xmpExt:Name` | El [show](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=es#show) de la dimensión Media Analytics. |
| `media.mediaTimed.primaryAssetReference.`<br/>`showType` | El [tipo de programa](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=es#show-type) de la dimensión Media Analytics. |
| `media.mediaTimed.primaryAssetReference.`<br/>`xmpDM:duration` | La [duración del vídeo](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=es#video-length) de la dimensión Media Analytics. |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`@id` | El [ID de sesión de medio](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=es#media-session-id) de la dimensión Media Analytics. |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`broadcastChannel` | El [canal de contenido](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=es#content-channel) de la dimensión Media Analytics. |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`broadcastContentType` | El [tipo de contenido](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=es#content-type) de la dimensión Media Analytics. |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`broadcastNetwork` | La [red](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=es#network) de la dimensión Media Analytics. |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`mediaSegmentView.value` | El [segmento de contenido](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=es#content-segment) de la dimensión Media Analytics. |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`playerName` | El [nombre del reproductor de contenido](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=es#content-player-name) de la dimensión Media Analytics. |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`playerSDKVersion.version` | La [versión del SDK](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=es#sdk-version) de la dimensión Media Analytics. |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`sourceFeed` | El [tipo de fuente de medios](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=es#media-feed-type) de la dimensión Media Analytics. |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`streamFormat` | El [formato de la emisión](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=es#stream-format) de la dimensión Media Analytics. |
| `media.mediaTimed.progress10.value` | El [marcador de progreso del 10 %](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=es#ten-progress-marker) de la métrica Media Analytics. |
| `media.mediaTimed.progress95.value` | El [marcador de progreso del 95 %](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=es#ninety-five-progress-marker) de la métrica Media Analytics. |
| `media.mediaTimed.resumes.value` | Las [reanudaciones de contenido](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=es#content-resumes) de la métrica Media Analytics. |
| `media.mediaTimed.starts.value` | Los [inicios de contenidos](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=es#media-starts) de la métrica Media Analytics. |
| `media.mediaTimed.thirdQuartiles.value` | El [marcador de progreso del 75 %](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=es#seventy-five-progress-marker) de la métrica Media Analytics. |
| `media.mediaTimed.timePlayed.value` | El [tiempo invertido en contenido](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=es#content-time-spent) de la métrica Media Analytics. |
| `media.mediaTimed.totalTimePlayed.value` | El [tiempo invertido en contenido](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=es#media-time-spent) de la métrica Media Analytics. |
| `placeContext.geo.latitude` | La dimensión móvil Latitud. |
| `placeContext.geo.longitude` | Longitud de la dimensión Móvil. |
| `placeContext.geo.postalCode` | La dimensión [Código postal](../../components/dimensions/zip-code.md). |
| `placeContext.geo.stateProvince` | La dimensión [Estados Unidos](../../components/dimensions/us-states.md). |
| `productListItems[]._experience.analytics.`<br/>`customDimensions.eVars.eVar1` -<br/>`productListItems[]._experience.analytics.`<br/>`customDimensions.eVars.eVar250` | Aplica la comercialización de [sintaxis del producto](../vars/page-vars/products.md) a eVars. |
| `productListItems[]._experience.analytics.`<br/>`event1to100.event1.value` -<br/>`productListItems[]._experience.analytics.`<br/>`event901-1000.event1000.value` | Aplica la comercialización de [sintaxis del producto](../vars/page-vars/products.md) en eventos. |
| `productListItems[].lineItemId` | La dimensión [Categoría](../../components/dimensions/category.md). Consulte también la variable de página [productos](../vars/page-vars/products.md). |
| `productListItems[].name` | La dimensión [Producto](../../components/dimensions/product.md). Consulte también la variable de página [productos. ](../vars/page-vars/products.md) If `productListItems[].SKU` y `productListItems[].name` ambos contienen datos, el valor de `productListItems[].SKU` se utiliza. |
| `productListItems[].priceTotal` | Ayuda a determinar la métrica [Ingresos](../../components/metrics/revenue.md). Consulte también la variable de página [productos](../vars/page-vars/products.md). |
| `productListItems[].quantity` | Ayuda a determinar la métrica [Unidades](../../components/metrics/units.md). Consulte también la variable de página [productos](../vars/page-vars/products.md). |
| `productListItems[].SKU` | La dimensión [Producto](../../components/dimensions/product.md). Consulte también la variable de página [productos. ](../vars/page-vars/products.md) If `productListItems[].SKU` y `productListItems[].name` ambos contienen datos, el valor de `productListItems[].SKU` se utiliza. |
| `web.webInteraction.URL` | La variable de implementación [linkURL](../vars/config-vars/linkurl.md). |
| `web.webInteraction.name` | La dimensión [Vínculo personalizado](../../components/dimensions/custom-link.md), [Vínculo de descarga](../../components/dimensions/download-link.md) o [Vínculo de salida](../../components/dimensions/exit-link.md), según el valor de `web.webInteraction.type` |
| `web.webInteraction.type` | Determina el tipo de vínculo en el que se hizo clic. Los valores válidos incluyen `other` (vínculos personalizados), `download` (vínculos de descarga) y `exit` (vínculos de salida). |
| `web.webPageDetails.URL` | La dimensión [Dirección URL de la página](../../components/dimensions/page-url.md). |
| `web.webPageDetails.errorPage` | Indicador que ayuda a determinar la [dimensión](../../components/dimensions/pages-not-found.md) y la [métrica](../../components/metrics/pages-not-found.md) “Páginas no encontradas”. |
| `web.webPageDetails.name` | La dimensión [Página](../../components/dimensions/page.md). |
| `web.webPageDetails.server` | La dimensión [Servidor](../../components/dimensions/server.md). |
| `web.webPageDetails.siteSection` | La dimensión [Sección del sitio](../../components/dimensions/site-section.md). |
| `web.webReferrer.URL` | La dimensión [Referente](../../components/dimensions/referrer.md). |

{style=&quot;table-layout:auto&quot;}

<!-- `environment.browserDetails.javaScriptVersion` and `web.webPageDetails.homePage` were included in the original table, but they no longer exist in Analytics. | -->

## Asignación de otros campos XDM a variables de Analytics

Si desea agregar dimensiones o métricas a Adobe Analytics, puede hacerlo mediante [Variables de datos de contexto](../vars/page-vars/contextdata.md). Los elementos de campo XDM que no se asignen automáticamente se envían a Adobe Analytics como datos de contexto con el prefijo a.x. A continuación, puede asignar esta variable de datos de contexto a la variable de Analytics deseada mediante [Reglas de procesamiento](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules.html?lang=es). Por ejemplo, si envía el siguiente evento:

```js
alloy("event",{
    "xdm":{
        "_atag":{
            "search":{
                "term":"Example search term"
            }
        }
    }
})
```

El SDK web envía esos datos a Adobe Analytics como variable de datos de contexto `a.x._atag.search.term`. A continuación, puede utilizar una regla de procesamiento para asignar el valor de la variable de datos de contexto a la variable de Analytics que desee, como un eVar:

![Regla de procesamiento de términos de búsqueda](assets/examplerule.png)

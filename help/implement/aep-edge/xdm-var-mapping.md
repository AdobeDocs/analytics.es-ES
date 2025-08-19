---
title: Asignación de variables de objeto XDM a Adobe Analytics
description: Vea qué campos XDM de Edge se asignan automáticamente a variables de Analytics.
exl-id: fbff5c38-0f04-4780-b976-023e207023c6
feature: Implementation Basics
role: Admin, Developer
source-git-commit: 7609ecb3c34fb0bc8293fc1ecd409cfabb327295
workflow-type: tm+mt
source-wordcount: '1458'
ht-degree: 49%

---

# Asignación de variables de objeto XDM a Adobe Analytics

La siguiente tabla muestra las variables XDM que Adobe Experience Platform Edge Network asigna automáticamente a Adobe Analytics. Si utiliza estas rutas de campo XDM, no es necesaria ninguna configuración adicional para enviar datos a Adobe Analytics. Estos campos se incluyen en el grupo de campos **[!UICONTROL Plantilla de Adobe Analytics ExperienceEvent]**. Se recomienda utilizar estos campos si tiene intención de enviar datos tanto a Adobe Analytics como a Adobe Experience Platform.

Si su organización planea pasar a Customer Journey Analytics, Adobe recomienda usar el objeto `data` para enviar datos directamente a Adobe Analytics sin ajustarse a un esquema. Esta estrategia permite que su organización use su propio esquema, en lugar de usar la [!UICONTROL Plantilla de Adobe Analytics ExperienceEvent] (que es menos aplicable a Customer Journey Analytics). Consulte [Asignación de variables de objetos de datos a Adobe Analytics](data-var-mapping.md) para obtener una tabla de asignación similar.

## Prioridades de valor

La mayoría de los campos de objeto XDM de esta tabla coinciden con un [campo de objeto de datos](data-var-mapping.md). Si establece un campo de objeto XDM determinado y su campo de objeto de datos respectivo, el campo de objeto de datos tiene prioridad. Si utiliza el campo de objeto XDM y el campo de objeto de datos, Adobe recomienda configurar eventos personalizados mediante el campo de objeto de datos. Si el campo `data.__adobe.analytics.events` está presente, sobrescribe todos los campos de objeto XDM relacionados con eventos comerciales y personalizados.

## Asignación de campo de objeto XDM

Las actualizaciones anteriores de esta tabla se encuentran en el [historial de confirmaciones en GitHub](https://github.com/AdobeDocs/analytics.en/commits/main/help/implement/aep-edge/xdm-var-mapping.md).

| Ruta de campo XDM | Variable y descripción de Analytics |
| --- | --- |
| `xdm.application.isClose` | Ayuda a definir la métrica del ciclo de vida móvil [Bloqueos](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/metrics/). |
| `xdm.application.isInstall` | Ayuda a determinar cuándo aumentar la métrica del ciclo de vida móvil [Primeros lanzamientos](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/metrics/). |
| `xdm.application.closeType` | Determina si un evento de cierre es un bloqueo o no. Los valores válidos incluyen `close` (finaliza la sesión del ciclo vital y se recibió un evento de pausa para la sesión anterior) y `unknown` (una sesión de ciclo vital termina sin un evento de pausa). Ayuda a establecer la métrica del ciclo de vida móvil [Bloqueos](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/metrics/). |
| `xdm.application.isInstall` | La métrica del ciclo de vida móvil [Instalaciones](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/metrics/). |
| `xdm.application.isLaunch` | La métrica del ciclo de vida móvil [Lanzamientos](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/metrics/). |
| `xdm.application.name` | Ayuda a establecer el [ID de la aplicación](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/metrics/) de la dimensión del ciclo de vida móvil. |
| `xdm.application.isUpgrade` | La métrica del ciclo de vida móvil [Actualizaciones](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/metrics/). |
| `xdm.application.version` | Ayuda a establecer la dimensión del ciclo de vida móvil [ID de aplicación](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/metrics/). |
| `xdm.application.sessionLength` | La métrica del ciclo de vida móvil [Duración anterior de la sesión](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/metrics/). |
| `xdm.commerce.checkouts.id` | Aplica [serialización de eventos](../vars/page-vars/events/event-serialization.md) a la métrica [Cierres de compra](/help/components/metrics/checkouts.md). |
| `xdm.commerce.checkouts.value` | Aumenta el valor de la métrica [Cierres de compra](/help/components/metrics/checkouts.md) por la cantidad deseada. |
| `xdm.commerce.order.currencyCode` | Establece la variable de configuración [currencyCode](../vars/config-vars/currencycode.md). |
| `xdm.commerce.order.purchaseID` | Establece la variable de página [purchaseID](../vars/page-vars/purchaseid.md). |
| `xdm.commerce.order.payments[0].transactionID` | Establece la variable de página [transactionID](../vars/page-vars/transactionid.md). |
| `xdm.commerce.productListAdds.id` | Aplica [Serialización de eventos](../vars/page-vars/events/event-serialization.md) a la métrica [Adiciones al carro de compras](/help/components/metrics/cart-additions.md). |
| `xdm.commerce.productListAdds.value` | Aumenta la métrica [Adiciones al carro de compras](/help/components/metrics/cart-additions.md). |
| `xdm.commerce.productListOpens.id` | Aplica [serialización de eventos](../vars/page-vars/events/event-serialization.md) a la métrica [Carros de compras](/help/components/metrics/carts.md). |
| `xdm.commerce.productListOpens.value` | Aumenta la métrica [Carros de compras](/help/components/metrics/carts.md). |
| `xdm.commerce.productListRemovals.id` | Aplica [serialización de eventos](../vars/page-vars/events/event-serialization.md) a la métrica [Eliminaciones del carro de compras](/help/components/metrics/cart-removals.md). |
| `xdm.commerce.productListRemovals.value` | Aumenta la métrica [Eliminaciones del carro de compras](/help/components/metrics/cart-removals.md). |
| `xdm.commerce.productListViews.id` | Aplica [serialización de eventos](../vars/page-vars/events/event-serialization.md) a la métrica [Vistas del carro de compras](/help/components/metrics/cart-views.md). |
| `xdm.commerce.productListViews.value` | Aumenta la métrica [Vistas del carro de compras](/help/components/metrics/cart-views.md). |
| `xdm.commerce.productViews.id` | Aplica [serialización de eventos](../vars/page-vars/events/event-serialization.md) a la métrica [Vistas del producto](/help/components/metrics/product-views.md). |
| `xdm.commerce.productViews.value` | Aumenta la métrica [Vistas del producto](/help/components/metrics/product-views.md). |
| `xdm.commerce.purchases.value` | Aumenta la métrica [Compras](/help/components/metrics/orders.md). |
| `xdm.device.model` | Dimensión del ciclo de vida móvil [Nombre del dispositivo](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/metrics/). |
| `xdm.device.colorDepth` | Ayuda a establecer la dimensión [Profundidad de color](/help/components/dimensions/color-depth.md). |
| `xdm.device.screenHeight` | Ayuda a establecer la dimensión [Resolución del monitor.](/help/components/dimensions/monitor-resolution.md) |
| `xdm.device.screenWidth` | Ayuda a establecer la dimensión [Resolución del monitor.](/help/components/dimensions/monitor-resolution.md) |
| `xdm.device.type` | Tipo de dispositivo móvil. |
| `xdm.environment.browserDetails.acceptLanguage` | Ayuda a establecer la dimensión [Idioma](/help/components/dimensions/language.md). |
| `xdm.environment.browserDetails.cookiesEnabled` | Establece dimensión [Compatibilidad con cookies](/help/components/dimensions/cookie-support.md). Los valores válidos incluyen `Y` (el explorador acepta cookies) y `N` (el explorador rechaza las cookies). |
| `xdm.environment.browserDetails.javaEnabled` | Establece la dimensión [Habilitado para Java](/help/components/dimensions/java-enabled.md). Los valores válidos incluyen `Y` (Java está habilitado) y `N` (Java está deshabilitado). |
| `xdm.environment.browserDetails.userAgent` | Se utiliza como método de identificación alternativo [visitante único](/help/components/metrics/unique-visitors.md). Normalmente se rellena usando el encabezado de solicitud HTTP `User-Agent`. Puede asignar este campo a una eVar si desea utilizarlo en los informes. |
| `xdm.environment.browserDetails.viewportHeight` | Establece la dimensión [Altura del explorador](/help/components/dimensions/browser-height.md). |
| `xdm.environment.browserDetails.viewportWidth` | Establece la dimensión [Anchura del explorador](/help/components/dimensions/browser-width.md). |
| `xdm.environment.carrier` | La dimensión del ciclo de vida móvil [Nombre del operador](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/metrics/). |
| `xdm.environment.connectionType` | Ayuda a establecer la dimensión [Tipo de conexión](/help/components/dimensions/connection-type.md). |
| `xdm.environment.ipV4` | Se utiliza como método de identificación alternativo [visitante único](/help/components/metrics/unique-visitors.md). Normalmente se rellena usando el encabezado HTTP `X-Forwarded-For`. |
| `xdm.environment._dc.language` | La configuración regional de la dimensión móvil. Solo se utiliza si no se ha definido xdm.environment.language. |
| `xdm.environment.language` | La configuración regional de la dimensión móvil. |
| `xdm.environment.operatingSystem` | El [sistema operativo](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/metrics/) de la dimensión del ciclo de vida móvil. |
| `xdm.environment.operatingSystemVersion` | Ayuda a establecer la dimensión del ciclo de vida móvil [Versión del sistema operativo](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/metrics/). |
| `xdm._experience.analytics.customDimensions.`<br/>`eVars.eVar1`<br/>`[...]`<br/>`xdm._experience.analytics.customDimensions.`<br/>`eVars.eVar250` | Establece la dimensión respectiva [eVar](/help/components/dimensions/evar.md). |
| `xdm._experience.analytics.customDimensions.`<br/>`hierarchies.hier1`<br/>`[...]`<br/>`xdm._experience.analytics.customDImensions.`<br/>`hierarchies.hier5` | Establece las dimensiones respectivas [Jerarquía](/help/components/dimensions/hierarchy.md). |
| `xdm._experience.analytics.customDimensions.`<br/>`listProps.prop1.delimiter`<br/>`[...]`<br/>`xdm._experience.analytics.customDimensions.`<br/>`listProps.prop75.delimiter` | Anulación del delimitador prop de lista. No se recomienda utilizar este campo, ya que el delimitador se recupera automáticamente de la [Administración de variables de tráfico](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-var.md) en la configuración del grupo de informes. El uso de este campo puede crear una discrepancia entre el delimitador utilizado y el delimitador que Analytics espera. |
| `xdm._experience.analytics.customDimensions.`<br/>`listProps.prop1.values`<br/>`[...]`<br/>`xdm._experience.analytics.customDimensions.`<br/>`listProps.prop75.values` | Una matriz de cadenas que contiene los valores respectivos [Prop de lista](../vars/page-vars/prop.md#list-props). |
| `xdm._experience.analytics.customDimensions.`<br/>`lists.list1.list[].value`<br/>`[...]`<br/>`xdm._experience.analytics.customDimensions.`<br/>`lists.list3.list[].value` | Concatena todas las cadenas `value` en cada matriz `list[]` a su respectiva [Variable de lista](../vars/page-vars/list.md). El delimitador se elige automáticamente en función del valor establecido en [Configuración del grupo de informes](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md). |
| `xdm._experience.analytics.customDimensions.`<br/>`props.prop1`<br/>`[...]`<br/>`xdm._experience.analytics.customDimensions.`<br/>`props.prop75` | Establece las dimensiones respectivas [Prop](/help/components/dimensions/prop.md). |
| `xdm._experience.analytics.event1to100.`<br/>`event1.id`<br/>`[...]`<br/>`xdm._experience.analytics.event901to1000.`<br/>`event1000.id` | Aplica la [serialización de eventos](../vars/page-vars/events/event-serialization.md) a la métrica respectiva [Eventos personalizados](/help/components/metrics/custom-events.md). Cada ID de evento reside en su página principal de 100 grupos. Por ejemplo, para aplicar la serialización a `event678`, utilice `xdm._experience.analytics.event601to700.event678.id`. |
| `xdm._experience.analytics.event1to100.`<br/>`event1.value`<br/>`[...]`<br/>`xdm._experience.analytics.event901to1000.`<br/>`event1000.value` | Incrementa la métrica respectiva [Eventos personalizados](/help/components/metrics/custom-events.md) por la cantidad deseada. Cada evento reside en su página principal de 100 grupos. Por ejemplo, el campo de `event567` es `xdm._experience.analytics.event501to600.event567.value`. |
| `xdm.identityMap.ECID[0].id` | El [Adobe Experience Cloud ID](https://experienceleague.adobe.com/en/docs/id-service/using/home). |
| `xdm.marketing.trackingCode` | Establece la dimensión [Código de seguimiento](/help/components/dimensions/tracking-code.md). |
| `xdm.media.mediaTimed.completes.value` | La métrica de servicios de medios de streaming [Contenido completado](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#content-complete). |
| `xdm.media.mediaTimed.dropBeforeStart.value` | `c.a.media.view`, `c.a.media.timePlayed`, `c.a.media.play` |
| `xdm.media.mediaTimed.federated.value` | La métrica de servicios de medios de streaming [Datos federados](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#federated-data). |
| `xdm.media.mediaTimed.firstQuartiles.value` | El marcador de progreso del 25 % [ de la métrica de servicios de medios de streaming.](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#twenty-five--progress-marker) |
| `xdm.media.mediaTimed.mediaSegmentView.value` | La métrica de servicios de medios de streaming [Vistas de segmentos de contenido](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#content-segment-views). |
| `xdm.media.mediaTimed.midpoints.value` | El marcador de progreso del [50 %](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#progress-marker) de la métrica de servicios de medios de streaming. |
| `xdm.media.mediaTimed.pauseTime.value` | La métrica de servicios de medios de streaming [Duración total de la pausa](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#total-pause-duration). |
| `xdm.media.mediaTimed.pauses.value` | La métrica de servicios de medios de streaming [Pausar eventos](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#pause-events). |
| `xdm.mediaCollection.sessionDetails.assetID` | La dimensión de servicios de medios de streaming [ID de recurso](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#asset-id). |
| `xdm.mediaCollection.sessionDetails.friendlyName` | La dimensión de servicios de medios de streaming [Nombre del vídeo](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#video-name). |
| `xdm.mediaCollection.sessionDetails.originator` | La dimensión de servicios de medios de streaming [Originator](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#originator). |
| `xdm.mediaCollection.sessionDetails.episode` | La dimensión de servicios de medios de streaming [Episodio](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#episode). |
| `xdm.mediaCollection.sessionDetails.genre` | La dimensión de servicios de medios de streaming [Genre](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#genre). |
| `xdm.mediaCollection.sessionDetails.rating` | La dimensión de servicios de medios de streaming [Clasificación del contenido](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#content-rating). |
| `xdm.mediaCollection.sessionDetails.season` | La dimensión de servicios de medios de streaming [Season](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#season). |
| `xdm.mediaCollection.sessionDetails.name` | La dimensión de servicios de medios de streaming [ID de contenido](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#content-id). |
| `xdm.mediaCollection.sessionDetails.show` | La dimensión de servicios de medios de streaming [Mostrar](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#show). |
| `xdm.mediaCollection.sessionDetails.showType` | La dimensión de servicios de medios de streaming [Tipo de programa](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#show-type). |
| `xdm.mediaCollection.sessionDetails.length` | La dimensión de servicios de medios de transmisión [Duración del vídeo](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#video-length). |
| `xdm.media.mediaTimed.primaryAssetViewDetails.@id` | La dimensión de servicios de medios de streaming [ID de sesión de medios](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#media-session-id). |
| `xdm.mediaCollection.sessionDetails.channel` | La dimensión de servicios de medios de streaming [Canal de contenido](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#content-channel). |
| `xdm.mediaCollection.sessionDetails.contentType` | La dimensión de servicios de medios de streaming [Tipo de contenido](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#content-type). |
| `xdm.mediaCollection.sessionDetails.network` | La dimensión de servicios de medios de streaming [Red](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#network). |
| `xdm.media.mediaTimed.primaryAssetViewDetails.`<br/>`mediaSegmentView.value` | La dimensión de servicios de medios de streaming [Segmento de contenido](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#content-segment). |
| `xdm.mediaCollection.sessionDetails.playerName` | Dimensión de los servicios de medios de streaming [Nombre del reproductor de contenido](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#content-player-name). |
| `xdm.mediaCollection.sessionDetails.appVersion` | La dimensión de servicios de medios de streaming [Versión de SDK](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#sdk-version). |
| `xdm.mediaCollection.sessionDetails.feed` | La dimensión de servicios de medios de streaming [Tipo de fuente de medios](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#media-feed-type). |
| `xdm.mediaCollection.sessionDetails.streamFormat` | La dimensión de servicios de medios de transmisión por secuencias [Formato de transmisión por secuencias](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#stream-format). |
| `xdm.media.mediaTimed.progress10.value` | El marcador de progreso del [10 % de la métrica de servicios de medios de streaming](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#ten--progress-marker). |
| `xdm.media.mediaTimed.progress95.value` | El marcador de progreso del 95 % [de la métrica de servicios de medios de streaming](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#ninety-five--progress-marker). |
| `xdm.mediaCollection.sessionDetails.hasResume` | La métrica de servicios de medios de streaming [Reanudación del contenido](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#content-resumes). |
| `xdm.media.mediaTimed.starts.value` | La métrica de servicios de medios de streaming [Comienzo de medios](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#media-starts). |
| `xdm.media.mediaTimed.thirdQuartiles.value` | El marcador de progreso del 75 %[ de la métrica de servicios de medios de streaming.](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#seventy-five--progress-marker) |
| `xdm.media.mediaTimed.timePlayed.value` | La métrica de servicios de medios de streaming [Tiempo invertido en contenido](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#content-time-spent). |
| `xdm.media.mediaTimed.totalTimePlayed.value` | La métrica de servicios de medios de streaming [Tiempo invertido en medios](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#media-time-spent). |
| `xdm.placeContext.geo._schema.latitude` | La ubicación de latitud del visitante. Ayuda a establecer [dimensiones de ubicación del ciclo de vida móvil](/help/components/dimensions/lifecycle-dimensions.md). |
| `xdm.placeContext.geo._schema.longitude` | La ubicación de longitud del visitante. Ayuda a establecer [dimensiones de ubicación del ciclo de vida móvil](/help/components/dimensions/lifecycle-dimensions.md). |
| `xdm.placeContext.geo.postalCode` | La dimensión [Código postal](/help/components/dimensions/zip-code.md). |
| `xdm.placeContext.geo.stateProvince` | La dimensión [Estados Unidos](/help/components/dimensions/us-states.md). |
| `xdm.placeContext.localTime` | Aparece como `t_time_info` en [Fuentes de datos](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md). |
| `xdm.productListItems[]._experience.analytics.`<br/>`customDimensions.eVars.eVar1`<br/>`[...]`<br/>`xdm.productListItems[]._experience.analytics.`<br/>`customDimensions.eVars.eVar250` | Aplica la comercialización de [sintaxis del producto](../vars/page-vars/products.md) a eVars. |
| `xdm.productListItems[]._experience.analytics.`<br/>`event1to100.event1.value`<br/>`[...]`<br/>`xdm.productListItems[]._experience.analytics.`<br/>`event901-1000.event1000.value` | Aplica la comercialización de [sintaxis del producto](../vars/page-vars/products.md) en eventos. |
| `xdm.productListItems[].productCategories[].categoryID` | La dimensión [Categoría](/help/components/dimensions/category.md). Consulte también la variable de página [productos](../vars/page-vars/products.md). |
| `xdm.productListItems[].name` | La dimensión [Producto](/help/components/dimensions/product.md). Consulte también la variable de página [productos](../vars/page-vars/products.md). Si `xdm.productListItems[].SKU` y `xdm.productListItems[].name` contienen datos, se utiliza el valor de `xdm.productListItems[].SKU`. |
| `xdm.productListItems[].priceTotal` | Ayuda a determinar la métrica [Ingresos](/help/components/metrics/revenue.md). Consulte también la variable de página [productos](../vars/page-vars/products.md). |
| `xdm.productListItems[].quantity` | Ayuda a determinar la métrica [Unidades](/help/components/metrics/units.md). Consulte también la variable de página [productos](../vars/page-vars/products.md). |
| `xdm.productListItems[].SKU` | La dimensión [Producto](/help/components/dimensions/product.md). Consulte también la variable de página [productos](../vars/page-vars/products.md). Si `xdm.productListItems[].SKU` y `xdm.productListItems[].name` contienen datos, se utiliza el valor de `xdm.productListItems[].SKU`. |
| `xdm.web.webInteraction.URL` | La variable de implementación [linkURL](../vars/config-vars/linkurl.md). |
| `xdm.web.webInteraction.name` | La dimensión [Vínculo personalizado](/help/components/dimensions/custom-link.md), [Vínculo de descarga](/help/components/dimensions/download-link.md) o [Vínculo de salida](/help/components/dimensions/exit-link.md), según el valor de `xdm.web.webInteraction.type` |
| `xdm.web.webInteraction.type` | Determina el tipo de vínculo en el que se hizo clic. Los valores válidos incluyen `other` (vínculos personalizados), `download` (vínculos de descarga) y `exit` (vínculos de salida). |
| `xdm.web.webPageDetails.URL` | La dimensión [Dirección URL de la página](/help/components/dimensions/page-url.md). |
| `xdm.web.webPageDetails.isErrorPage` | Indicador que ayuda a determinar la [dimensión](/help/components/dimensions/pages-not-found.md) y la [métrica](/help/components/metrics/pages-not-found.md) “Páginas no encontradas”. |
| `xdm.web.webPageDetails.name` | La dimensión [Página](/help/components/dimensions/page.md). |
| `xdm.web.webPageDetails.server` | La dimensión [Servidor](/help/components/dimensions/server.md). |
| `xdm.web.webPageDetails.siteSection` | La dimensión [Sección del sitio](/help/components/dimensions/site-section.md). |
| `xdm.web.webReferrer.URL` | La dimensión [Referente](/help/components/dimensions/referrer.md). |

{style="table-layout:auto"}

<!-- `environment.browserDetails.javaScriptVersion` and `web.webPageDetails.homePage` were included in the original table, but they no longer exist in Analytics. | -->

## Asignación de otros campos XDM a variables de Analytics

Si desea agregar dimensiones o métricas a Adobe Analytics, puede hacerlo mediante [Variables de datos de contexto](../vars/page-vars/contextdata.md).

### Asignación implícita

Los elementos de campo XDM que no se asignen automáticamente se envían a Adobe Analytics como datos de contexto con el prefijo `a.x.`. A continuación, puede asignar esta variable de datos de contexto a la variable de Analytics deseada mediante [reglas de procesamiento](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/processing-rules/pr-overview.md). Por ejemplo, si envía el siguiente evento:

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

El SDK web envía esos datos a Adobe Analytics como variable de datos de contexto `a.x._atag.search.term`. A continuación, puede utilizar una regla de procesamiento para asignar el valor de la variable de datos de contexto a la variable de Analytics que desee, como un `eVar`:

![Regla de procesamiento de términos de búsqueda](assets/examplerule.png)

## Asignación explícita

También puede asignar explícitamente elementos de campo XDM como datos de contexto. Cualquier elemento de campo XDM asignado explícitamente mediante el elemento `contextData` se envía a Adobe Analytics como datos de contexto sin prefijo. A continuación, puede asignar esta variable de datos de contexto a la variable de Analytics deseada mediante [reglas de procesamiento](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/processing-rules/pr-overview.md). Por ejemplo, si envía el siguiente evento:

```js
alloy("event",{
    "xdm":{
        "_atag":{
            "analytics": {
                "contextData" : {
                    "someValue" : "1"
                }
            }
        }
    }
})
```

Web SDK envía esos datos a Adobe Analytics como variable de datos de contexto `somevalue` con valor `1`.  A continuación, puede utilizar una regla de procesamiento para asignar el valor de la variable de datos de contexto a la variable de Analytics que desee, como un `eVar`:

![Regla de procesamiento de términos de búsqueda](assets/examplerule-explicit.png)

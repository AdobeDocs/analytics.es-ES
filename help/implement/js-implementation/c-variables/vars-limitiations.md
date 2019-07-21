---
description: Mirada de alto nivel a variables y sus limitaciones.
keywords: Implementación de Analytics; variable; limitaciones; límites
seo-description: Mirada de alto nivel a variables y sus limitaciones.
seo-title: Variables y limitaciones
solution: Analytics
subtopic: Variables
title: Variables y limitaciones
topic: Desarrollador e implementación
uuid: 028677 a 7-2132-4 ee 7-9 cc 1-697 c 2 c 09 b 087
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Variables y limitaciones

Mirada de alto nivel a variables y sus limitaciones.

>[!NOTE]
>
>See [Configuration Variables](../../../implement/js-implementation/c-variables/configuration-variables.md#concept_8FCA630706334F54B4DCB607378BCD00) and [Page Variables](../../../implement/js-implementation/c-variables/page-variables.md#concept_37933DFF2FC547A0A3B296D5E646B6A3) for an in-depth look at the most common Analytics variables.

La siguiente tabla proporciona información rápida sobre variables de [!DNL Analytics]:

| Variable | Descripción |
|---|---|
| s_account | Determina el grupo de informes en el que los datos se almacenan y se notifican. |
| browserHeight | Muestra la altura de la ventana del explorador. |
| browserWidth | Muestra la anchura de la ventana del explorador. |
| campaign | Identifica las campañas de marketing utilizadas para atraer visitantes al sitio. El valor de *`campaign`* generalmente se toma de un parámetro de cadena de consulta. |
| channel | Normalmente identifica una sección del sitio web. Por ejemplo: un comerciante puede tener secciones como Electrónica, Juguetes o Ropa. Un sitio de medios puede tener secciones como Noticias, Deportes o Negocios. |
| charSet | Traduce el conjunto de caracteres de la página web a UTF-8. |
| colorDepth | Muestra el número de bits utilizado para mostrar el color en cada píxel de la pantalla. |
| connectionType | En Internet Explorer, indica si el explorador está configurado con una conexión LAN o de módem. |
| cookieDomainPeriods | Determina el dominio donde se configurará la cookie de ID de visitante[!DNL Analytics] (s_vi) de ; para ello, se determina el número de puntos en el dominio de la dirección URL de la página. For `www.mysite.com`, *`cookieDomainPeriods`* should be "2." For `www.mysite.co.jp`, *`cookieDomainPeriods`* should be "3." |
| cookieLifetime | La utilizan los servidores de [!DNL Analytics] y JavaScript para determinar la vigencia de una cookie. |
| cookiesEnabled | Indica si JavaScript puede configurar una cookie de sesión de origen. |
| currencyCode | Determina la tasa de conversión que se aplicará a los ingresos cuando entre en las bases de datos de [!DNL Analytics]. Las bases de datos de [!DNL Analytics] almacenan importes monetarios en la moneda que elija. If that currency is the same as that specified in *`currencyCode`*, or *`currencyCode`* is empty, no conversion is applied. |
| dc | Permite seleccionar el centro de datos al que se envían los datos. |
| doPlugins | *`doPlugins`* es una referencia a la *`s_doPlugins`* función. It allows the *`s_doPlugins`* function to be called at the appropriate location within the JavaScript file. |
| dynamicAccountList | Selecciona dinámicamente un grupo de informes al que se enviarán los datos. La variable *`dynamicAccountList`* contiene las reglas que se utilizarán para determinar el grupo de informes de destino. |
| dynamicAccountMatch | Utiliza el objeto DOM para recuperar la sección de la dirección URL donde se aplican todas las reglas de *`dynamicAccountList`*. This variable is only valid when *`dynamicAccountSelection`* is set to 'True.' |
| dynamicAccountSelection | Permite seleccionar dinámicamente el grupo de informes en función de la dirección URL de cada página. |
| dynamicVariablePrefix | Permite a la implementación marcar variables que deben rellenarse de forma dinámica. Las cookies, los encabezados de solicitud y parámetros de cadena de consulta de imagen se pueden rellenar dinámicamente. |
| eVarN | Se utiliza para generar informes personalizados en el módulo de conversión[!DNL Analytics] de . Cuando una eVar está establecida en un valor para un visitante, [!DNL Analytics] recuerda automáticamente ese valor hasta que caduque. Cualquier evento de éxito que encuentra el visitante mientras la eVar está activa se contabiliza en el valor de eVar. |
| events | Registra eventos de éxito de carro de compras y personalizados comunes. |
| fpCookieDomainPeriods | Determina el dominio donde se configurarán las cookies de [!DNL Analytics] que no sean la [!UICONTROL ID de visitante] (s_vi); para ello, se determina el número de puntos en el dominio de la página. |
| hierN | Determina la ubicación de una página en la jerarquía del sitio. Esta variable resulta muy útil para los sitios que tienen más de tres niveles en la estructura del sitio. |
| homepage | En Internet Explorer, indica si la página actual está configurada como página de inicio del usuario. |
| javaEnabled | Indica si Java está habilitado en el explorador. |
| javascriptVersion | Muestra la versión de JavaScript admitida por el navegador. |
| linkDownloadFileTypes | Lista de extensiones de archivo separados por coma. Si su sitio contiene vínculos a archivos con cualquiera de estas extensiones, las direcciones URL de estos vínculos se verán en el informe [!UICONTROL Descargas de archivos]. |
| linkExternalFilters | Si el sitio contiene muchos vínculos a sitios externos y no se desea realizar el seguimiento de todos los vínculos de salida, use *`linkExternalFilters`* para crear un informe de un subconjunto específico de vínculos de salida.  |
| linkInternalFilters | Determina qué vínculos del sitio son vínculos de salida. Es una lista de filtros separados por coma que representan los vínculos que son parte del sitio. |
| linkLeaveQueryString | Determina si la cadena de consulta debe incluirse en los informes [!UICONTROL Vínculos de salida] y [!UICONTROL Descargas de archivos]. |
| linkName | Variable opcional utilizada en el [!UICONTROL seguimiento] de vínculos que determina el nombre de un vínculo de salida, de descarga o personalizado. La variable *`linkName`* normalmente no se necesita porque el tercer parámetro de *`tl()`* la función la sustituye. |
| linkTrackEvents | Contiene los eventos que deben enviarse con los vínculos personalizados, de descarga y de salida. La variable solo se tiene en cuenta si  *`linkTrackVars`* contiene "events". |
| linkTrackVars | Lista de variables separadas por coma que se enviarán con vínculos de descarga, de salida o personalizados. Si *`linkTrackVars`* se configura como "", todas las variables que tienen valores se envían con los datos del vínculo. |
| linkType | Variable opcional utilizada para el seguimiento de vínculos que determina qué informe mostrará el nombre o la dirección URL del vínculo (vínculos de salida, de descarga, personalizados). *`linkType`* normalmente no se necesita porque el segundo parámetro de *`tl()`* la función la sustituye. |
| mediaLength | Especifica la longitud total del contenido multimedia que se está reproduciendo. |
| mediaName | Especifica el nombre del vídeo o elemento multimedia. Solo está disponible mediante la [!UICONTROL API de inserción de datos] y la [!UICONTROL fuente de datos de procesamiento completo]. |
| mediaPlayer | Especifica el reproductor que se utiliza para reproducir un vídeo o elemento multimedia. |
| mediaSession | Especifica los segmentos de un vídeo o elemento multimedia consumidos. |
| Media.trackEvents | Identifica qué eventos deben enviarse con una visita multimedia. Solo es aplicable con JavaScript [!UICONTROL ActionSource]. |
| Media.trackVars | Identifica qué variables deben enviarse con una visita multimedia. Solo es aplicable con JavaScript [!UICONTROL ActionSource]. |
| mobile | Controla el orden con el que se usan las cookies y las ID de suscriptor para identificar a los visitantes. |
| s_objectID | Variable global que debe configurarse en el evento [!UICONTROL onClick] de un vínculo. Si crea una ID de objeto única para un vínculo o una ubicación de vínculo en una página, se puede mejorar el seguimiento del mapa de clics de visitantes o utilizar el mapa de clics de visitantes para informar sobre un tipo o ubicación de vínculo, en lugar de la URL del vínculo. |
| pageName | Contiene el nombre de cada una de las páginas del sitio. Si el registro de *`pageName`* se deja en blanco, se usa la dirección URL para representar el nombre de página en [!DNL Analytics]. |
| pageType | Solo se usa para designar una página de error 404 Página no encontrada. Solo tiene un posible valor, que es "errorPage". En una página de error 404, la variable *`pageName`* no debe rellenarse. |
| pageURL | En casos excepcionales, la dirección URL de la página no es la dirección URL que se desearía registrar en [!DNL Analytics]. To accommodate these situations, [!DNL Analytics] offers the *`pageURL`* variable, which overrides the actual URL of the page. |
| plugins | En exploradores Netscape y Mozilla, enumera los complementos instalados en el explorador. |
| products | Se usa para realizar el seguimiento de productos y categorías de productos, así como la cantidad de compra y el precio de compra. La variable *`products`* siempre debe configurarse junto con un evento de éxito. Optionally, the *`products`* variable can track custom numeric and currency events, as well as [!UICONTROL Merchandising] eVars. |
| propN | Se utiliza para generar informes personalizados en el [!DNL Analytics]módulo de tráfico[!UICONTROL  de ]. Las [!UICONTROL props] se pueden utilizar como contadores (para contabilizar el número de veces que se envía una vista de página), para los informes de rutas o en informes de correlación. |
| purchaseID | Se utiliza para evitar que [!DNL Analytics] contabilice un pedido varias veces. Whenever the purchase event is used on your site, you should use the *`purchaseID`* variable. |
| referrer | Restaura la información del referente perdida. |
| resolution | Indica la resolución de la pantalla del visitante que está viendo la página web. |
| server | Muestra el dominio de una página web (para ver a qué dominios se dirigen los visitantes) o el servidor que facilita la página (para una referencia rápida de balance de carga). |
| state | Captura el estado de un visitante del sitio. |
| trackDownloadLinks | Establezca *`trackDownloadLinks`* a'true'si desea rastrear los vínculos a archivos descargables del sitio. If *`trackDownloadLinks`* is 'true,' *`linkDownloadFileTypes`* determines which links are downloadable files. |
| trackExternalLinks | If *`trackExternalLinks`* is 'true,' *`linkInternalFilters`* and *`linkExternalFilters`* determines whether any link clicked is an exit link. |
| trackingServer | Se utiliza para la implementación de cookies de origen a fin de especificar el dominio en el cual se escriben la solicitud de imagen y la cookie. Se utiliza para páginas no seguras.  |
| trackingServerSecure | Se utiliza para la implementación de cookies de origen a fin de especificar el dominio en el cual se escriben la solicitud de imagen y la cookie. Se utiliza para páginas seguras.  |
| trackInlineStats | Determina si se recopilarán los datos del mapa de clics de visitantes. |
| transactionID | Enlaza datos sin conexión con una transacción en línea (como un posible cliente o una compra generada en línea). Cada *`transactionID`* única enviada a Adobe se registrará a fin de prepararla para una carga de [!UICONTROL fuentes de datos] de información sin conexión sobre esa transacción. Consulte la [Guía de fuentes de datos](https://marketing.adobe.com/resources/help/en_US/sc/datasources/). |
| s_usePlugins | Si la función *`s_doPlugins`* está disponible y contiene código útil, [!UICONTROL s_ useplugins] debe configurarse en'true '. When [!UICONTROL usePlugins] is 'true,' the *`s_doPlugins`* function is called prior to each image request. |
| visitorID | Visitors may be identified by the *`visitorID`* tag, or by IP address/User Agent. *`visitorID`* Puede ser de hasta 100 caracteres alfanuméricos y no debe contener guiones. |
| visitorNamespace | If *`visitorNamespace`* is used in your JavaScript file, do not delete or alter it. Esta variable se usa para identificar el dominio con el que se configuran las cookies. Si *`visitorNamespace`* cambia, es probable que todos los visitantes notificados a [!DNL Analytics] se conviertan en nuevos visitantes. Es decir, no modifique esta variable sin la autorización de un consultor de Adobe. |
| zip | Captura el código postal de un visitante del sitio. |


---
description: Mirada de alto nivel a variables y sus limitaciones.
keywords: Analytics Implementation;variable;limitations;limits
solution: Analytics
subtopic: Variables
title: Variables y limitaciones
topic: Developer and implementation
uuid: 028677a7-2132-4ee7-9cc1-697c2c09b087
translation-type: tm+mt
source-git-commit: edf88e40cae8b6886b04257f266666c13a37f88d

---


# Variables y limitaciones

Mirada de alto nivel a variables y sus limitaciones.

>[!NOTE]
>
>Consulte [Variables de configuración](/help/implement/js-implementation/c-variables/configuration-variables.md) y [Variables de página](/help/implement/js-implementation/page-variables/page-variables.md) para obtener una vista detallada de las variables de Analytics más comunes.

La siguiente tabla proporciona información rápida sobre variables de [!DNL Analytics]:

| Variable | Descripción |
|---|---|
| s_account | Determina el grupo de informes en el que los datos se almacenan y se notifican. |
| browserHeight | Muestra la altura de la ventana del explorador. |
| browserWidth | Muestra la anchura de la ventana del explorador. |
| campaign | Identifica las campañas de marketing utilizadas para atraer visitantes al sitio. El valor de *`campaign`* generalmente se toma de un parámetro de cadena de consulta. |
| canal | Normalmente identifica una sección del sitio web. Por ejemplo: un comerciante puede tener secciones como Electrónica, Juguetes o Ropa. Un sitio de medios puede tener secciones como Noticias, Deportes o Negocios. |
| charSet | Traduce el conjunto de caracteres de la página web a UTF-8. |
| colorDepth | Muestra el número de bits utilizado para mostrar el color en cada píxel de la pantalla. |
| connectionType | En Internet Explorer, indica si el explorador está configurado con una conexión LAN o de módem. |
| cookieDomainPeriods | Determina el dominio donde se configurará la cookie de [!DNL Analytics] [!UICONTROL ID de visitante] (s_vi) de ; para ello, se determina el número de puntos en el dominio de la dirección URL de la página. Para `www.mysite.com`, *`cookieDomainPeriods`* debe ser “2”. Para `www.mysite.co.jp`, *`cookieDomainPeriods`* debe ser “3”. |
| cookieLifetime | La utilizan los servidores de [!DNL Analytics] y JavaScript para determinar la vigencia de una cookie. |
| cookiesEnabled | Indica si JavaScript puede configurar una cookie de sesión de origen. |
| currencyCode | Determina la tasa de conversión que se aplicará a los ingresos cuando entre en las bases de datos de [!DNL Analytics]. Las bases de datos de [!DNL Analytics] almacenan importes monetarios en la moneda que elija. Si esa moneda es la misma que la especificada en *`currencyCode`*, o *`currencyCode`* está vacía, no se aplica ninguna conversión. |
| dc | Permite seleccionar el centro de datos al que se envían los datos. |
| doPlugins | *`doPlugins`* Es una referencia a la función *`s_doPlugins`*. Permite llamar a la función *`s_doPlugins`* en la ubicación apropiada dentro del archivo JavaScript. |
| dynamicAccountList | Selecciona dinámicamente un grupo de informes al que se enviarán los datos. La variable *`dynamicAccountList`* contiene las reglas que se utilizarán para determinar el grupo de informes de destino. |
| dynamicAccountMatch | Utiliza el objeto DOM para recuperar la sección de la dirección URL donde se aplican todas las reglas de *`dynamicAccountList`*. Esta variable solo es válida cuando *`dynamicAccountSelection`* está configurada en “True”. |
| dynamicAccountSelection | Permite seleccionar dinámicamente el grupo de informes en función de la dirección URL de cada página. |
| dynamicVariablePrefix | Permite a la implementación marcar variables que deben rellenarse de forma dinámica. Las cookies, los encabezados de solicitud y parámetros de cadena de consulta de imagen se pueden rellenar dinámicamente. |
| eVarN | Se utiliza para generar informes personalizados en el [!DNL Analytics] [!UICONTROL módulo de conversión de]. Cuando una eVar está establecida en un valor para un visitante, [!DNL Analytics] recuerda automáticamente ese valor hasta que caduque. Cualquier evento de éxito que encuentra el visitante mientras la eVar está activa se cuenta hacia el valor eVar. |
| eventos | Registra eventos de éxito de carro de compras y personalizados comunes. |
| fpCookieDomainPeriods | Determina el dominio donde se configurarán las cookies de [!DNL Analytics] que no sean la [!UICONTROL ID de visitante] (s_vi); para ello, se determina el número de puntos en el dominio de la página. |
| hierN | Determina la ubicación de una página en la jerarquía del sitio. Esta variable resulta muy útil para los sitios que tienen más de tres niveles en la estructura del sitio. |
| homepage | En Internet Explorer, indica si la página actual está configurada como página de inicio del usuario. |
| javaEnabled | Indica si Java está habilitado en el explorador. |
| javascriptVersion | Muestra la versión de JavaScript admitida por el navegador. |
| linkDownloadFileTypes | Lista de extensiones de archivo separados por coma. Si su sitio contiene vínculos a archivos con cualquiera de estas extensiones, las direcciones URL de estos vínculos se verán en el informe [!UICONTROL Descargas de archivos]. |
| linkExternalFilters | Si el sitio contiene muchos vínculos a sitios externos y no se desea realizar el seguimiento de todos los vínculos de salida, use *`linkExternalFilters`* para crear un informe de un subconjunto específico de vínculos de salida. |
| linkInternalFilters | Determina qué vínculos del sitio son vínculos de salida. Es una lista de filtros separados por coma que representan los vínculos que son parte del sitio. |
| linkLeaveQueryString | Determina si la cadena de consulta debe incluirse en los informes [!UICONTROL Vínculos de salida] y [!UICONTROL Descargas de archivos]. |
| linkName | Variable opcional utilizada en el [!UICONTROL seguimiento] de vínculos que determina el nombre de un vínculo de salida, de descarga o personalizado. La variable *`linkName`* no suele ser necesaria ya que el tercer parámetro de la función *`tl()`* la sustituye. |
| linkTrackEvents | Contiene los eventos que deben enviarse con los vínculos personalizados, de descarga y de salida. Esta variable solo se tiene en cuenta si *`linkTrackVars`* contiene “events”. |
| linkTrackVars | Lista de variables separadas por coma que se enviarán con vínculos de descarga, de salida o personalizados. Si *`linkTrackVars`* se configura como “”, todas las variables que tienen valores se envían con los datos del vínculo. |
| linkType | Variable opcional utilizada para el seguimiento de vínculos que determina qué informe mostrará el nombre o la dirección URL del vínculo (vínculos de salida, de descarga, personalizados). *`linkType`* no suele ser necesaria, ya que el segundo parámetro de la función *`tl()`* la sustituye. |
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
| pageURL | En casos excepcionales, la dirección URL de la página no es la dirección URL que se desearía registrar en [!DNL Analytics]. Para dar cabida a estas situaciones, [!DNL Analytics] ofrece la variable *`pageURL`*, que anula la dirección URL real de la página. |
| plugins | En exploradores Netscape y Mozilla, enumera los complementos instalados en el explorador. |
| Productos | Se usa para realizar el seguimiento de productos y categorías de productos, así como la cantidad de compra y el precio de compra. La variable *`products`* siempre debe configurarse junto con un evento de éxito. De forma opcional, la variable *`products`* puede realizar el seguimiento de eventos numéricos y monetarios, así como eVars de [!UICONTROL Marketing]. |
| propN | Se utiliza para generar informes personalizados en el [!DNL Analytics]módulo de tráfico[!UICONTROL  de ]. Las [!UICONTROL props] se pueden utilizar como contadores (para contabilizar el número de veces que se envía una vista de página), para los informes de rutas o en informes de correlación. |
| purchaseID | Se utiliza para evitar que [!DNL Analytics] contabilice un pedido varias veces. Siempre que se use el evento purchase en el sitio, se debe usar la variable *`purchaseID`*. |
| referrer | Restaura la información del referente perdida. |
| resolution | Indica la resolución de la pantalla del visitante que está viendo la página web. |
| server | Muestra el dominio de una página web (para ver a qué dominios se dirigen los visitantes) o el servidor que facilita la página (para una referencia rápida de balance de carga). |
| state | Captura el estado de un visitante del sitio. |
| trackDownloadLinks | Establezca *`trackDownloadLinks`* como “True” si desea realizar el seguimiento de los vínculos a archivos descargables del sitio. Si *`trackDownloadLinks`* tiene el valor “true”, *`linkDownloadFileTypes`* determina qué vínculos son archivos descargables. |
| trackExternalLinks | Si *`trackExternalLinks`* tiene el valor “true” *`linkInternalFilters`* y *`linkExternalFilters`* determina si un vínculo en el que se hizo clic es un vínculo de salida. |
| trackingServer | Se utiliza para la implementación de cookies de origen a fin de especificar el dominio en el cual se escriben la solicitud de imagen y la cookie. Se utiliza para páginas no seguras. |
| trackingServerSecure | Se utiliza para la implementación de cookies de origen a fin de especificar el dominio en el cual se escriben la solicitud de imagen y la cookie. Se utiliza para páginas seguras. |
| trackInlineStats | Determina si se recopilarán los datos del mapa de clics de visitantes. |
| transactionID | Enlaza datos sin conexión con una transacción en línea (como un posible cliente o una compra generada en línea). Cada *`transactionID`* único enviado a Adobe se registrará a fin de prepararlo para una carga de [!UICONTROL fuentes de datos] de información sin conexión sobre esa transacción. Consulte la [Guía de fuentes de datos](https://marketing.adobe.com/resources/help/en_US/sc/datasources/). |
| s_usePlugins | Si la función La función *`s_doPlugins`* está disponible y contiene código útil, [!UICONTROL s_usePlugins] debe configurarse como “True”. Cuando [!UICONTROL usePlugins] tiene el valor “true”, se llama a la función *`s_doPlugins`* antes de cada solicitud de imagen. |
| visitorID | Los visitantes se pueden identificar mediante la etiqueta *`visitorID`* o por dirección IP o agente de usuario. *`visitorID`* puede tener hasta 100 caracteres alfanuméricos y no debe contener guiones. |
| visitorNamespace | Si *`visitorNamespace`* se usa en el archivo JavaScript, no la elimine ni la modifique. Esta variable se usa para identificar el dominio con el que se configuran las cookies. Si *`visitorNamespace`* cambia, es probable que todos los visitantes notificados a se conviertan en nuevos visitantes. [!DNL Analytics] Es decir, no modifique esta variable sin la autorización de un consultor de Adobe. |
| zip | Captura el código postal de un visitante del sitio. |


---
description: Configuration variables set in AppMeasurement.js.
keywords: Implementación de análisis
seo-description: Variables de configuración establecidas en AppMeasurement.js para Adobe Analytics
seo-title: Variables de configuración
solution: Analytics
subtopic: Variables
title: Variables de configuración
topic: Desarrollador e implementación
uuid: a19484b6-e350-4c12-b4d6-a31c79a42db0
translation-type: tm+mt
source-git-commit: a340bb50ec437db64dafaddc0b20aec740aee299

---


# Información general sobre las variables de configuración

Las variables de configuración controlan la manera en que se capturan y procesan los datos en los informes. The most-common configuration variables that are typically set in the main global JavaScript AppMeasurement.js). Estas variables se pueden establecer en el código de nivel de página y en los vínculos de Analytics cuando sea necesario.

Not all of these variables appear in the code by default when you generate code through the **[!UICONTROL Admin Tool]** &gt; **[!UICONTROL Code Manager]**. Puede que algunas de estas variables de configuración no sean aplicables a las necesidades de implementación del sitio.

Algunos de los objetivos de usar estas variables de configuración son:

* Seguir varios sitios o dominios.
* Usar cualquier moneda en compras.
* Capturar datos en idiomas indiferentes.
* Seguimiento de vínculos (cantidad de archivos descargados, vínculos a sitios externos).
* Seguir vínculos personalizados con un fin determinado.

>[!NOTE]
>
>[!DNL AppMeasurement] requires that all configuration variables are set before the initial call to the track function, `t()`. Si las variables de configuración se configuran después de la llamada a `t()`, pueden producirse resultados inesperados. To ensure proper data collection, all configuration variables must be above the `doPlugins` function.

Para obtener ayuda con variables de configuración específicas, haga clic en cualquiera de los vínculos siguientes:

* [s.account](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Especifique el grupo de informes en el que se almacenan los datos y se generan los informes.

* [s.dynamicAccountSelection](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-dynaccsel.html): Seleccione dinámicamente el grupo de informes en función de la dirección URL de cada página.

* [s.dynamicAccountList](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-dynacclist.html): Especifique las reglas utilizadas para determinar el grupo de informes de destino.

* [s.dynamicAccountMatch](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-dynaccmatch.html): Utilice el objeto DOM para recuperar la sección de la URL a la que se aplican todas las reglas.

* [s.dynamicVariablePrefix](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-dynvarprefix.html): Implementar el indicador para variables rellenadas dinámicamente.

* [s.charSet](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-charset.html): Convierta los datos entrantes a UTF-8 para almacenamiento y generación de informes de Analytics.

* [s.currencyCode: Determine the conversion rate to apply to revenue.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-currcode.html)

* [s.cookieDomain: Determines which domain the  and  cookies are set.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-cookdom.html)`s_cc``s_sq`

* [s.cookieDomainPeriods: Determine the domain for  and  cookies by specifying the number of periods in the domain of the page URL.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-cookdomperiods.html)`s_cc``s_sq`

* [s.fpCookieDomainPeriods: Specify cookies set by JavaScript (, , plug-ins) that are inherently first-party cookies, even with third-party  or  domains.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-fpcookdomperiods.html)`s_sq``s_cc``2o7.net``omtrdc.net`

* [s.cookieLifetime: Determine lifespan of a cookie as processed by both JavaScript and data collection servers.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-cooklifetime.html)

* [s.doPlugins: Refer and allow the function to be called at the appropriate location within the JavaScript file.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-doplugins.html)

* [s.registerPreTrackCallback](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-regpretrackcback.html): Función para tomar como parámetros tanto la llamada de retorno (una función) como los parámetros de dicha función.

* [s.registerPostTrackCallback: Function for taking as parameters both the callback (a function), and the parameters to that function.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-regpretrackcback.html)

* [s.trackDownLoadLinks](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-trackdnloadlinks.html): Rastree los vínculos a los archivos descargables del sitio.

* [s.trackExternalLinks](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-trackextlinks.html): Determine si un vínculo en el que se hizo clic es un vínculo de salida.

* [s.trackInlineStats](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-trackinlinestats.html): Determine whether ClickMap data is gathered.

* [s.linkDownloadFileTypes](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkdownldftype.html): Incluya una lista de extensiones de archivo separadas por coma.

* [s.linkInternalFilters](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkintfilters.html): Incluye una lista de filtros separados por comas que representan los vínculos que forman parte del sitio.

* [s.linkLeaveQueryString](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linklvqrystring.html): Determine si la cadena de consulta debe incluirse o no en los informes Vínculos de salida y Descarga de archivos.

* [s.linkTrackVars](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html): Incluya una lista de variables separadas por coma que se envían con vínculos personalizados, de salida y de descarga.

* [s.linkExternalFilters](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkextfilters.html): Se utiliza para informar sobre un subconjunto específico de vínculos de salida.

* [s.usePlugins](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-useplugins.html): Call the `s_doPlugins` function prior to each image request.


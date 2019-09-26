---
description: Configuration variables set in AppMeasurement.js.
keywords: Implementación de análisis
seo-description: Configuration variables set in AppMeasurement.js for Adobe Analytics
seo-title: Variables de configuración
solution: Analytics
subtopic: Variables
title: Variables de configuración
topic: Desarrollador e implementación
uuid: a19484b6-e350-4c12-b4d6-a31c79a42db0
translation-type: tm+mt
source-git-commit: 9212d70ab8fd7bc0ccfb7e781a92b1731f0a40bd

---


# Información general sobre las variables de configuración

Las variables de configuración controlan la manera en que se capturan y procesan los datos en los informes. Las variables de configuración más comunes que generalmente se establecen en el archivo JavaScript AppMeasurement.js principal global). Estas variables se pueden establecer en el código de nivel de página y en los vínculos de Analytics cuando sea necesario.

Not all of these variables appear in the code by default when you generate code through the **[!UICONTROL Admin Tool]** &gt; **[!UICONTROL Code Manager]**. Puede que algunas de estas variables de configuración no sean aplicables a las necesidades de implementación del sitio.

Algunos de los objetivos de usar estas variables de configuración son:

* Seguir varios sitios o dominios.
* Usar cualquier moneda en compras.
* Capturar datos en idiomas indiferentes.
* Seguimiento de vínculos (cantidad de archivos descargados, vínculos a sitios externos).
* Seguir vínculos personalizados con un fin determinado.

>[!NOTE]
>
>[!DNL AppMeasurement] requiere que todas las variables de configuración se establezcan antes de la llamada inicial a la función track, `t()`. Si las variables de configuración se configuran después de la llamada a `t()`, pueden producirse resultados inesperados. To ensure proper data collection, all configuration variables must be above the `doPlugins` function.

Para obtener ayuda con variables de configuración específicas, haga clic en cualquiera de los vínculos siguientes:

* [s.account](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Especifique el grupo de informes en el que se almacenan los datos y se generan los informes.

* [s.dynamicAccountSelection](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Dynamically select the report suite based on the URL of each page.

* [s.dynamicAccountList](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Especifique las reglas utilizadas para determinar el grupo de informes de destino.

* [s.dynamicAccountMatch](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Use the DOM object to retrieve the section of the URL to which all rules are applied.

* [s.dynamicVariablePrefix: Deploy flagging for dynamically-populated variables.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html)

* [s.charSet: Convert incoming data to UTF-8 for storage and reporting by Analytics.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html)

* [s.currencyCode: Determine the conversion rate to apply to revenue.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html)

* [s.cookieDomain](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Determina qué dominio se configuran las `s_cc` cookies y `s_sq` las cookies.

* [s.cookieDomainPeriods: Determine the domain for  and  cookies by specifying the number of periods in the domain of the page URL.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html)`s_cc``s_sq`

* [s.fpCookieDomainPeriods](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Especifique las cookies configuradas por JavaScript (`s_sq`, `s_cc`, complementos) que son cookies inherentemente de origen, incluso con dominios de terceros `2o7.net` o `omtrdc.net` .

* [s.cookieLifetime: Determine lifespan of a cookie as processed by both JavaScript and data collection servers.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html)

* [s.doPlugins: Refer and allow the function to be called at the appropriate location within the JavaScript file.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html)

* [s.registerPreTrackCallback](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Function for taking as parameters both the callback (a function), and the parameters to that function.

* [s.registerPostTrackCallback](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Función para tomar como parámetros tanto la llamada de retorno (una función) como los parámetros de dicha función.

* [s.trackDownLoadLinks](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Rastree los vínculos a los archivos descargables del sitio.

* [s.trackExternalLinks](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Determine si un vínculo en el que se hizo clic es un vínculo de salida.

* [s.trackInlineStats](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Determine si los datos de ClickMap se recopilan.

* [s.linkDownloadFileTypes](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Incluya una lista de extensiones de archivo separadas por coma.

* [s.linkInternalFilters](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Incluye una lista de filtros separados por comas que representan los vínculos que forman parte del sitio.

* [s.linkLeaveQueryString](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Determine si la cadena de consulta debe incluirse o no en los informes Vínculos de salida y Descarga de archivos.

* [s.linkTrackVars](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Include a comma-separated list of variables that are sent with custom, exit, and download links.

* [s.linkExternalFilters](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Se utiliza para informar sobre un subconjunto específico de vínculos de salida.

* [s.usePlugins](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Llame a la `s_doPlugins` función antes de cada solicitud de imagen.


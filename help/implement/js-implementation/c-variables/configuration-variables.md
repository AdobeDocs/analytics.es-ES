---
description: Variables de configuración establecidas en AppMeasurement.js.
keywords: Implementación de análisis
seo-description: Variables de configuración establecidas en AppMeasurement.js para Adobe Analytics
seo-title: Variables de configuración
solution: Analytics
subtopic: Variables
title: Variables de configuración
topic: Desarrollador e implementación
uuid: a19484b6-e350-4c12-b4d6-a31c79a42db0
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# Configuration variables overview

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
>[!DNL AppMeasurement] requiere que todas las variables de configuración se establezcan antes de la llamada inicial a la función track, `t()`. If configuration variables are set after the call to , unexpected results may occur. `t()` To ensure proper data collection, all configuration variables must be above the `doPlugins` function.

Para obtener ayuda con variables de configuración específicas, consulte los siguientes vínculos:

* [s_account](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Especifique el grupo de informes en el que se almacenan los datos y se generan los informes.

* [s.dynamicAccountSelection](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Seleccione dinámicamente el grupo de informes en función de la dirección URL de cada página.

* [s.dynamicAccountList: Specify the rules used for determining the destination report suite.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html)

* [s.dynamicAccountMatch](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Utilice el objeto DOM para recuperar la sección de la URL a la que se aplican todas las reglas.

* [s.dynamicVariablePrefix: Deploy flagging for dynamically-populated variables.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html)

* [s.charSet: Convert incoming data to UTF-8 for storage and reporting by Analytics.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html)

* [s.currencyCode](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Determine la tasa de conversión que se aplicará a los ingresos.

* [s.cookieDomain: Determines which domain the  and  cookies are set.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html)`s_cc``s_sq`

* [s.cookieDomainPeriods](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Para determinar el dominio para `s_cc` y las `s_sq` cookies, especifique el número de puntos en el dominio de la dirección URL de la página.

* [s.fpCookieDomainPeriods](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Especifique las cookies configuradas por JavaScript (`s_sq`, `s_cc`, complementos) que son cookies inherentemente de origen, incluso con dominios de terceros `2o7.net` o `omtrdc.net` .

* [s.cookieLifetime](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Determinar la duración de una cookie tal como la procesan los servidores de recopilación de datos y JavaScript.

* [s.doPlugins](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Consulte y permita que se llame a la función en la ubicación adecuada dentro del archivo JavaScript.

* [s.registerPreTrackCallback](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Función para tomar como parámetros tanto la llamada de retorno (una función) como los parámetros de dicha función.

* [s.registerPostTrackCallback](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Función para tomar como parámetros tanto la llamada de retorno (una función) como los parámetros de dicha función.

* [s.trackDownLoadLinks](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Rastree los vínculos a los archivos descargables del sitio.

* [s.trackExternalLinks](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Determine si un vínculo en el que se hizo clic es un vínculo de salida.

* [trackInlineStats](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Determine si los datos de ClickMap se recopilan.

* [s.linkDownloadFileTypes](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Incluya una lista de extensiones de archivo separadas por coma.

* [s.linkInternalFilters](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Incluye una lista de filtros separados por comas que representan los vínculos que forman parte del sitio.

* [s.linkLeaveQueryString](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Determine si la cadena de consulta debe incluirse o no en los informes Vínculos de salida y Descarga de archivos.

* [s.linkTrackVars](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Incluya una lista de variables separadas por coma que se envían con vínculos personalizados, de salida y de descarga.

* [s.linkExternalFilters](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Se utiliza para informar sobre un subconjunto específico de vínculos de salida.

* [s.usePlugins](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Llame a la `s_doPlugins` función antes de cada solicitud de imagen.


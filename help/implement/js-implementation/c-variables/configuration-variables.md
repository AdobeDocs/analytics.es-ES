---
description: Variables de configuración establecidas en AppMeasurement.js.
keywords: Analytics Implementation
subtopic: Variables
title: Variables de configuración
topic: Developer and implementation
uuid: a19484b6-e350-4c12-b4d6-a31c79a42db0
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Información general sobre las variables de configuración

Las variables de configuración controlan la manera en que se capturan y procesan los datos en los informes. Las variables de configuración más comunes que se establecen generalmente en el JavaScript principal global (AppMeasurement.js. Estas variables pueden establecerse dentro de los vínculos y del código de nivel de página de Analytics cuando corresponde.

No todas estas variables aparecen en el código de forma predeterminada al generar código mediante **[!UICONTROL Herramienta de administración]** &gt; **[!UICONTROL Administrador de códigos]**. Es posible que algunas de estas variables de configuración no sean aplicables a las necesidades de implementación del sitio.

Algunos de los objetivos de usar estas variables de configuración son:

* Seguir varios sitios o dominios
* Usar cualquier moneda en compras
* Capturar datos en idiomas indiferentes
* Seguimiento de vínculos (número de archivos descargados, vínculos a sitios externos).
* Seguir vínculos personalizados con un fin determinado

> [!NOTE] [!DNL AppMeasurement] requiere que todas las variables de configuración estén establecidas antes de la llamada inicial a la función de seguimiento, `t()`. Si las variables de configuración se configuran después de la llamada a `t()`, pueden producirse resultados inesperados. Para garantizar la adecuada recopilación de datos, todas las variables de configuración deben estar encima de la función `doPlugins`.

Para obtener ayuda con variables de configuración específicas, haga clic en cualquiera de los vínculos siguientes:

* [s.account](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Especifique el grupo de informes en el que se almacenan los datos y se generan los informes.

* [s.dynamicAccountSelection](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-dynaccsel.html): Seleccione dinámicamente el grupo de informes en función de la dirección URL de cada página.

* [s.dynamicAccountList](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-dynacclist.html): Especifique las reglas utilizadas para determinar el grupo de informes de destino.

* [s.dynamicAccountMatch](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-dynaccmatch.html): Utilice el objeto DOM para recuperar la sección de la URL a la que se aplican todas las reglas.

* [s.dynamicVariablePrefix](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-dynvarprefix.html): Implementar el indicador para variables rellenadas dinámicamente.

* [s.charSet](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-charset.html): Convierta los datos entrantes a UTF-8 para almacenamiento y generación de informes de Analytics.

* [s.currencyCode](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-currcode.html): Determine la tasa de conversión que se aplicará a los ingresos.

* [s.cookieDomain](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-cookdom.html): Determina qué dominio se configuran las `s_cc` cookies y `s_sq` las cookies.

* [s.cookieDomainPeriods](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-cookdomperiods.html): Para determinar el dominio para `s_cc` y las `s_sq` cookies, especifique el número de puntos en el dominio de la dirección URL de la página.

* [s.fpCookieDomainPeriods](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-fpcookdomperiods.html): Especifique las cookies configuradas por JavaScript (`s_sq`, `s_cc`, complementos) que son cookies inherentemente de origen, incluso con dominios de terceros `2o7.net` o `omtrdc.net` .

* [s.cookieLifetime](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-cooklifetime.html): Determinar la duración de una cookie tal como la procesan los servidores de recopilación de datos y JavaScript.

* [s.doPlugins](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-doplugins.html): Consulte y permita que se llame a la función en la ubicación adecuada dentro del archivo JavaScript.

* [s.registerPreTrackCallback](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-regpretrackcback.html): Función para tomar como parámetros tanto la llamada de retorno (una función) como los parámetros de dicha función.

* [s.trackDownLoadLinks](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-trackdnloadlinks.html): Rastree los vínculos a los archivos descargables del sitio.

* [s.trackExternalLinks](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-trackextlinks.html): Determine si un vínculo en el que se hizo clic es un vínculo de salida.

* [s.trackInlineStats](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-trackinlinestats.html): Determine si los datos de ClickMap se recopilan.

* [s.linkDownloadFileTypes](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkdownldftype.html): Incluya una lista de extensiones de archivo separadas por coma.

* [s.linkInternalFilters](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-trackintfilters.html): Incluye una lista de filtros separados por comas que representan los vínculos que forman parte del sitio.

* [s.linkLeaveQueryString](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linklvqrystring.html): Determine si la cadena de consulta debe incluirse o no en los informes Vínculos de salida y Descarga de archivos.

* [s.linkTrackVars](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html): Incluya una lista de variables separadas por coma que se envían con vínculos personalizados, de salida y de descarga.

* [s.linkExternalFilters](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkextfilters.html): Se utiliza para informar sobre un subconjunto específico de vínculos de salida.

* [s.usePlugins](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-useplugins.html): Llame a la `s_doPlugins` función antes de cada solicitud de imagen.

* [s.useForcedlinkTracking](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-usedforcedlinktracking.html): Deshabilita el seguimiento de vínculos forzado para algunos exploradores.

* [s.linkType](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktype.html): Establece el tipo de vínculo para descargar, salir o personalizado.

* [s.linkName](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkname.html): Define el nombre que aparece en el informe de descarga, salida o vínculo personalizado.

* [s.ForcedlinkTrackingTimeout](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-forcedlinktrackingtimeout.html): Establece el tiempo de espera máximo al realizar el seguimiento.

* [s.linkTrackEvents](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackingevents.html): Deshabilita el seguimiento de vínculos forzado para algunos exploradores.

* [s.linkUrl](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkurl.html): Establece la dirección URL del vínculo.

* [s.linkObject](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkobject.html): Hace referencia a un objeto en el que se ha hecho clic.

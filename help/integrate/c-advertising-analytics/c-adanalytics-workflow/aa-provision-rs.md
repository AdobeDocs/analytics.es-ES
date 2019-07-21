---
description: 'null'
seo-description: 'null'
seo-title: Habilitar grupo de informes para análisis de publicidad
title: Habilitar grupo de informes para análisis de publicidad
uuid: 934 f 0 e 02-b 5 d 7-4 eca -93 d 8-92 f 95 bd 7014 a
translation-type: tm+mt
source-git-commit: e3b1ac3139f26ca3a97f3d2228276e690ec4cb79

---


# Habilitar grupo de informes para análisis de publicidad

Para ver cualquier dato de búsqueda de Análisis de publicidad en Analytics, debe configurar cada grupo de informes de Experience Cloud para los informes de Advertising Analytics.

1. [Asigne su grupo de informes a una organización](https://marketing.adobe.com/resources/help/en_US/mcloud/map-report-suite.html).
1. Navigate to **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**.

1. Select the report suite that is [mapped to your Experience Cloud organization](https://marketing.adobe.com/resources/help/en_US/mcloud/map-report-suite.html).
1. Click **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Advertising Analytics Configuration]**.

   ![](assets/aa_reporting.png)

   >[!IMPORTANT]
   >
   >AMO ID hace referencia a la variable de Adobe Advertising Cloud en la que se van a insertar los datos de búsqueda.

1. Establezca las variables de asignación y caducidad que desea que utilice la variable de AMO ID. Las variables de conversión (eVars) permiten que Adobe Analytics atribuya eventos de éxito a valores específicos de variables. En ocasiones, las variables encuentran más de un valor antes de visitar un evento de éxito. Para estos casos, la asignación determina qué valor de variable recibe crédito por el evento.

   | Configuración | Definición |
   |--- |--- |
   | Valor original (primero) | El primer valor visto obtiene crédito de asignación completo, independientemente de los valores subsiguientes para esa variable. |
   | Más reciente (último) | El último valor visto obtiene crédito de asignación completo para el evento de éxito, independientemente de las variables que se hayan activado antes de él. |
   | Caduca después | Le permite especificar un período de tiempo o un evento tras el cual caduca el valor de la eVar (es decir, ya no recibe crédito por los eventos de éxito).  Si se da un evento de éxito después de que caduque la eVar, el valor Ninguno recibe crédito por el evento (no había ninguna eVar activa). |

1. Click **[!UICONTROL Enable Advertising Analytics Reporting]** (first time), or **[!UICONTROL Update Advertising Analytics Reporting]** (subsequent times). Ahora, su grupo de informes está listo para recibir datos de búsqueda de Advertising Analytics. No está listo para [crear cuentas publicitarias](../../../integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md#concept_1958E8C15C334E8B9DC510EC8D5DCA7C).


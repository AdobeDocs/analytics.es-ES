---
description: Habilite permisos de usuario para Acceso a la API, Administración de grupos de informes, Herramientas e informes, y Elementos de tablero.
keywords: grupos; permisos
seo-description: Habilite permisos de usuario para Acceso a la API, Administración de grupos de informes, Herramientas e informes, y Elementos de tablero.
seo-title: Personalizar herramientas de grupos de informes permisos
solution: Analytics
subtopic: Usuarios y grupos
title: Personalizar permisos de herramientas de grupos de informes
topic: Herramientas de administración
uuid: 3 c 95 d 296-ffd 0-4971-9 c 5 f -110 ddbe 042 ce
translation-type: tm+mt
source-git-commit: 2d01f9edb976a57c18641fea03e01ad029893eea

---


# Personalizar permisos de herramientas de grupos de informes

>[!IMPORTANT]
>
>User and product management is moving to the [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). Adobe le avisará cuando deba migrar a sus usuarios. After all customers have migrated, help content for **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin Tools]** &gt; **[!UICONTROL User Management]** will be retired.

Habilite permisos de usuario para Acceso a la API, Administración de grupos de informes, Herramientas e informes, y Elementos de tablero.

**[!UICONTROL Administración de usuarios]** &gt; **[!UICONTROL Grupos]** &gt; **[!UICONTROL Acceso a informes]** &gt; **[!UICONTROL Herramientas de grupos de informes]** &gt; **[!UICONTROL Personalizar]**

La página [!UICONTROL Personalizar herramientas del grupo de informes] concede a los miembros de un grupo acceso a los elementos que siguen.

![](assets/report-suite-tools.png)

## Descripciones de los campos

Las opciones de esta página pertenecen a los grupos de informes seleccionados en la página [!UICONTROL Definir grupos de usuarios].

| Elemento | Descripción |
|--- |--- |
| **Servicios Web** |  |
| Estas opciones permiten a los usuarios hacer llamadas al método de Data Warehouse y extraer ajustes de configuración de grupos de informes. |  |
| Data Warehouse | Permite a un usuario no administrador realizar llamadas utilizando los métodos de Data Warehouse a través de la API de servicios Web. See [Data Warehouse - Developer Documentation](/help/export/data-warehouse/data-warehouse.md) |
| Grupos de informes (lectura) | Permite a los usuarios que no son administradores utilizar los métodos de grupos de informes en la API. |
| Grupos de informes (escritura) | Permite a los usuarios que no son administradores utilizar los métodos de grupos de informes en la API. |
| **Administración de grupos de informes** |  |
| These settings grant access to the menu items in  Admin &gt;  Report Suites  &gt;  Edit Settings ([Report Suite Manager](../../../admin/c-manage-report-suites/report-suites-admin.md)). |  |
| [Administración del tráfico](../../../admin/c-traffic-management/traffic-management.md) | Otorga permiso a Administración del tráfico. |
| [Administración de grupos de informes](../../../admin/c-manage-report-suites/report-suites-admin.md) | Concede permiso para administrar grupos de informes. |
| [Resumen de la cuenta](../../../admin/admin/general-acct-settings-admin.md) | Concede permiso para editar configuración de la cuenta para un grupo de informes. |
| [Filtros de dirección URL](../../../admin/admin/internal-url-filter-admin.md) | Concede permiso para acceder a los filtros de URL internos en los grupos de informes. Los filtros de URL internos se utilizan para determinar qué referentes (o páginas de referentes) son internos del sitio. |
| [Calendario personalizado](../../../admin/admin/custom-calendar.md) | Otorga permiso para editar el calendario personalizado. |
| [Búsqueda pagada](https://marketing.adobe.com/resources/help/en_US/reference/paid_search_detection.html) | La detección de búsqueda de pago diferencia entre búsquedas pagadas y naturales en los informes Motores de búsqueda y Palabras clave de búsqueda. |
| [Personalización de menús](../../../admin/admin/customize-menus.md) | Personalice los menús de los informes que ve un usuario en Reports &amp; Analytics. |
| [Configuración de informes en tiempo real](../../../admin/admin/realtime/t-realtime-admin.md) | Permisos para configurar análisis de informes en tiempo real. |
| [Configuración de vídeo](../../../admin/admin/video-management.md) | Permisos para designar un conjunto de variables de conversión personalizadas (eVars) y de eventos personalizados para utilizarlos para hacer rastreos y generar informes en vídeo. |
| [Clasificaciones de vídeo](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/video/video_config.html) | Permiso para designar un conjunto de variables de conversión personalizadas (eVars) y de eventos personalizados para utilizarlos para hacer rastreos y generar informes en vídeo. |
| [Variables de tráfico](../../../admin/admin/c-traffic-variables/traffic-var.md) | Permiso para correlacionar datos personalizados con eventos concretos relacionados con el tráfico. |
| [Clasificaciones de tráfico](/help/admin/admin/c-traffic-variables/traffic-classifications.md) | Consolidado en clasificaciones (en Herramientas e informes). |
| [Canales](https://marketing.adobe.com/resources/help/en_US/mchannel/index.html) | Otorga permiso para acceder a las opciones de Canales de marketing en Administrador del grupo de informes &gt; Editar configuración &gt; Canales de marketing. |
| [Costos](https://marketing.adobe.com/resources/help/en_US/mchannel/c_overview_budget.html) | Habilita el permiso para acceder a Canales de marketing &gt; Costos de canal de mercadotecnia, en el Administrador de grupos de informes. |
| [Variables de conversión](../../../admin/admin/conversion-var-admin/conversion-var-admin.md) | La variable de conversión de perspectiva personalizada (o eVar) se coloca en el código de Adobe en las páginas web del sitio seleccionadas. Su principal función es segmentar las métricas de éxito de conversión en los informes de marketing personalizados. |
| [Métodos de búsqueda](../../../admin/admin/finding-methods.md) | Le permite identificar cómo reciben crédito distintos informes de métodos de búsqueda para los eventos de éxito de conversión en el sitio. |
| [Clasificaciones de conversión](../../../admin/admin/conversion-var-admin/conversion-classifications.md) | Consolidado en clasificaciones (en Herramientas e informes). |
| [Visitante único](https://marketing.adobe.com/resources/help/en_US/reference/t_unique_visitor_variable.html) | Otorga permiso para especificar la variable de visitante único. |
| [Eventos de éxito](https://marketing.adobe.com/resources/help/en_US/reference/success_event.html) | Acciones que se pueden rastrear, como visualizaciones de productos, cierres de compra y adquisiciones. |
| [Jerarquías de clasificación](../../../components/c-classifications2/classification-hierarchies.md) | Consolidado en clasificaciones (en Herramientas e informes). |
| [Variables de lista](https://marketing.adobe.com/resources/help/en_US/sc/implement/listN.html) | También se conoce como List Var. Similar a cómo funcionan las props de lista, las variables de lista permiten incluir varios valores dentro de la misma solicitud de imagen. |
| [Medidas predeterminadas](../../../admin/admin/default-metrics.md) | Reports &amp; Analytics muestra un conjunto predeterminado de métricas en todos los informes de conversión, a menos que algún usuario seleccione un conjunto personalizado de métricas. Las medidas seleccionadas se muestran a todos los usuarios del grupo de informes asociado. |
| [Reglas de procesamiento](https://marketing.adobe.com/resources/help/en_US/sc/implement/ref-processing-rules.html) | Concede acceso a las reglas de procesamiento, lo que simplifica la recopilación de datos y gestiona el contenido al enviarlo a los informes. |
| **Herramientas e informes** |  |
| [Detección de anomalías](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/anomaly_detection.html) | Concede permiso para acceder a Detección de anomalías, que constituye un método estadístico para determinar el cambio experimentado en una métrica determinada respecto a los datos anteriores. |
| [Informe de canal](https://marketing.adobe.com/resources/help/en_US/mchannel/index.html) | Concede permiso para informes Canal de marketing, los cuales se encuentran en Informes &gt; Informes de canal de marketing. |
| [Informe en tiempo real](../../../admin/admin/realtime/t-realtime-admin.md) | Otorga acceso al informe en tiempo real. |
| [Páginas de bots](../../../admin/admin/bot-rules/bot-rules.md#concept_A306689C65EB4D0F9AE65E3FD48ED5F7) | Las reglas de bots permiten eliminar de un grupo de informes el tráfico generado por arañas de web y bots conocidos. Al eliminar el tráfico de bots, la medición de la actividad de los usuarios en el sitio web es más exacta. |
| [Bots](../../../admin/admin/bot-rules/bot-rules.md) | Las reglas de bots permiten eliminar de un grupo de informes el tráfico generado por arañas de web y bots conocidos. Al eliminar el tráfico de bots, la medición de la actividad de los usuarios en el sitio web es más exacta. |
| [Informe del Data Warehouse personalizado](../../..//export/data-warehouse/data-warehouse.md) | El Data Warehouse hace referencia a la copia de datos sin procesar para su almacenamiento y para elaborar informes personalizados, que se pueden ejecutar filtrando los datos. Puede solicitar informes para mostrar las relaciones de datos avanzadas que hay entre los datos sin procesar en función de sus propias preguntas. |
| [Visitas de retorno diario](../../../components/c-variables/dimensionslist/reports-daily-return-visits.md) | (Heredado) Informe que muestra el número de visitantes que vieron el sitio web más de una vez en un día determinado. Un día se define como el último período de 24 horas. |
| [Administrador de fuentes de datos](../../../admin/admin/data-sources.md) | La función Fuentes de datos permite importar datos a Analytics desde fuentes sin conexión. |
| [Excluir por dirección IP](../../../admin/admin/exclude-ip.md) | Se pueden excluir datos de las direcciones IP específicas, por ejemplo, las actividades de sitio web internas, las pruebas del sitio y el uso por parte de los empleados, de los informes. |
| ClickMap heredado | Otorga acceso al menú para la herramienta de superposición heredada ClickMap. |
| Instalación heredada de ClickMap | Otorga derechos de instalación para la herramienta heredada de ClickMap. |
| [Visitas de retorno](../../../components/c-variables/dimensionslist/reports-return-visits.md) | Informe que muestra el número de visitas en las que el número de visitas es mayor que 1. El informe de visitas de retorno incluye visitantes sin cookies. |
| [Importador/Exportador de clasificaciones](https://marketing.adobe.com/resources/help/en_US/reference/c_working_with_saint.html) y [Generador de reglas](https://marketing.adobe.com/resources/help/en_US/reference/classification_rule_builder.html) | Consolidado en clasificaciones (ver más adelante). |
| Administrador de fuentes de datos | Concede derechos a la Fuente de datos de análisis. |
| Clasificaciones | Combina los siguientes permisos: ' Clasificaciones de tráfico ',' Clasificaciones de video ',' Clasificaciones de conversión ',' Jerarquías de clasificación ',' Administrador de clasificaciones'y'Importador de clasificaciones/Exportador y Generador de reglas '. Nota: Con este permiso, los usuarios pueden editar las clasificaciones de todos los grupos de informes, no solo los seleccionados. |
| [Análisis de contribución](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/contribution-analysis.html) | Concede permisos para utilizar los análisis de contribución en Analysis Workspace. |
| **Elementos de tablero** |  |
| The settings in Dashboard Items enables access to [reportlets](https://marketing.adobe.com/resources/help/en_US/sc/user/dashboard.html) in Reports &amp; Analytics:, My Recommended Reports, Company Summary Reportlet, Image, KPI/Gauge Reportlet, Report Suite Totals, Text, Reportlet, Usage Summary Reportlet, and Web Resources |  |
| **Otro** |  |
| Social | Controla el acceso al menú Administración social en el Administrador de grupos de informes. |

---
description: Información general sobre Adobe Analytics, incluida la información sobre la interfaz de Analytics, así como información de introducción para administradores, analistas, usuarios y desarrolladores.
title: Información general de Adobe Analytics
feature: Analytics Basics
hide: true
hidefromtoc: true
source-git-commit: 58e5f3ca4b99e92b64e01095d61d5fe1fc97feb9
workflow-type: tm+mt
source-wordcount: '5077'
ht-degree: 41%

---

# Información general de Adobe Analytics

Adobe Analytics permite a las organizaciones recopilar datos y obtener perspectivas procesables de cualquier interacción digital con los clientes. Con un análisis en profundidad, informes versátiles e inteligencia predictiva, las organizaciones obtienen la base perspicaz que necesitan para crear mejores experiencias para sus clientes.

## Ventajas principales

A continuación se indican algunas de las formas clave en que Adobe Analytics ayuda a las organizaciones a obtener perspectivas críticas para servir mejor a sus clientes.

Para obtener más información sobre las ventajas que proporciona Adobe Analytics, consulte la [página de producto de Adobe Analytics](https://business.adobe.com/products/analytics/adobe-analytics.html).

+++Análisis web

Adobe Analytics proporciona las siguientes herramientas predictivas y de segmentación compleja para analizar el tráfico del sitio web:

* [Análisis ad hoc en Analysis Workspace](/help/analyze/analysis-workspace/home.md)

* [Análisis de flujo](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md)

* [Segmentación avanzada](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html?lang=es)

+++

+++Análisis de marketing

Adobe Analytics ayuda a las organizaciones a comprender dónde interactúan los clientes con sus marcas, qué canales prefieren los clientes y qué experiencias resuenan con ellos.

Las siguientes funciones clave de Adobe Analytics proporcionan estas funciones de marketing:

* Recopilación de datos multicanal

* [Integración de datos sin conexión](https://experienceleague.adobe.com/docs/analytics/import/data-sources/overview.html?lang=en)

* [Análisis ad hoc en Analysis Workspace](/help/analyze/analysis-workspace/home.md)

+++

+++Atribución

La atribución permite a las organizaciones ver cómo las distintas interacciones a lo largo del recorrido del cliente afectan a la conversión. Además de proporcionar opciones de atribución más tradicionales, como los modelos Lineal o Primer contacto, la atribución en Adobe Analytics también utiliza el aprendizaje automático y modelos estadísticos avanzados para comprender el impacto preciso de cada contacto.

Para obtener más información, consulte [Modelos de atribución y ventanas retroactivas](/help/analyze/analysis-workspace/attribution/models.md).

+++


+++Análisis predictivo

El análisis predictivo utiliza el aprendizaje automático y el modelado estadístico avanzado para analizar los datos de los clientes, encontrar patrones y predecir comportamientos futuros como la pérdida o la probabilidad de conversión. Permite a los analistas de datos aprovechar los enormes conjuntos de datos que, de lo contrario, se podrían desperdiciar.

Las siguientes funciones clave de Adobe Analytics proporcionan estas funciones predictivas:

* [Detección de anomalías](#anomaly-detection)

* [Análisis de contribución](#contribution-analysis)

* [Alertas inteligentes](#intelligent-alerts)

+++

## Requisitos previos para utilizar Adobe Analytics

Para poder usar Adobe Analytics, debe contar con:

* Una licencia de Adobe Analytics válida

  Adobe Analytics requiere una licencia de sitio. Póngase en contacto con el representante de cuenta de Adobe para obtener más información. <!--is this phrased correctly? Is this important? -->

* Un explorador compatible

  Cada usuario que acceda a Adobe Analytics debe utilizar un explorador compatible. Para obtener más información, consulte la [Requisitos del sistema de Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/analyze/admin-overview/sys-reqs.html?lang=en).

<!-- are there more? -->

## Explicación de la interfaz de Analytics

La interfaz de Adobe Analytics consta de las siguientes áreas clave, incluidas pestañas para administrar proyectos en Analysis Workspace, componentes de administración, herramientas y funciones de administrador.

![Pestaña Workspace](assets/landing-all2.png)

Expanda las siguientes secciones para obtener más información sobre cada área de Analysis Workspace:

+++pestaña Workspace

El [!UICONTROL Workspace] La pestaña muestra el [!UICONTROL Proyectos] de forma predeterminada, que muestra la carpeta Compañía, las carpetas personales que haya creado, sus proyectos y los cuadros de resultados móviles.

1. En Adobe Analytics, seleccione la [!UICONTROL **Workspace**] pestaña.

   ![Pestaña Workspace](assets/landing-all2.png)

Para obtener más información sobre las funciones disponibles en la [!UICONTROL Workspace] pestaña, consulte [Página de aterrizaje de Adobe Analytics](/help/analyze/landing.md).

+++

+++Pestaña de informes

A partir del 31 de diciembre de 2023, Adobe tiene la intención de descatalogar Reports &amp; Analytics, y sus informes y funciones correspondientes.

En su lugar, utilice el [!UICONTROL **Informes**] área en el carril izquierdo de la [!UICONTROL **Workspace**] pestaña. Para obtener más información, consulte *Vaya a la pestaña Informes* in [Página de aterrizaje de Adobe Analytics](/help/analyze/landing.md).

+++

+++Pestaña Componentes

El [!UICONTROL Componentes] Esta pestaña incluye funciones que le ayudan a ajustar y potenciar su análisis de datos.

1. En Adobe Analytics, seleccione la [!UICONTROL **Componentes**] pestaña, luego seleccione [!UICONTROL **Todos los componentes**].

   ![Pestaña Workspace](assets/components-tab.png)

2. Seleccione cualquiera de las siguientes funciones de producto para configurarlo:


   | Funcionalidad del producto | Función | Más información |
   |---------|----------|----------|
   | Segmentos  | Adobe Analytics le permite generar, administrar, compartir y aplicar a sus informes poderosos segmentos centrados en la audiencia utilizando capacidades de Analytics, Adobe Experience Cloud, Adobe Target y otros productos integrados de Adobe. | [Segmentación de Analytics](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html?lang=es) |
   | Métricas calculadas  | Las métricas calculadas y calculadas avanzadas (o derivadas) son métricas personalizadas que se pueden crear a partir de métricas existentes.  Permiten a los especialistas en marketing, gestores de productos y analistas plantear preguntas acerca de los datos sin tener que cambiar la implementación de Analytics. | [Métricas calculadas y calculadas avanzadas (derivadas)](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/cm-overview.html?lang=es) |
   | Intervalos de fechas | Analysis Workspace incluye una lista de intervalos de fechas predeterminados que los usuarios pueden utilizar al crear análisis. Además, puede crear intervalos de fechas personalizados y ponerlos a disposición de los usuarios en Analysis Workspace. | [Crear intervalos de fechas](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html?lang=es) <!-- should create an article in the Components Guide for managing/creating date ranges. This article in the Tools Guide needs updating. --> |
   | Grupos de informes virtuales | Los grupos de informes virtuales segmentan los datos de Adobe Analytics de modo que pueda controlar el acceso a cada segmento. | [Resumen de los grupos de informes virtuales](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=es) |
   | Alertas | Las alertas inteligentes permiten un control más granular sobre las alertas e integran la detección de anomalías con el sistema de alerta. | [Alertas inteligentes](https://experienceleague.adobe.com/docs/analytics/components/alerts/intellligent-alerts.html?lang=en) |
   | Objetivos | Los objetivos le permiten medir el rendimiento del sitio y llevar un control del avance hacia los objetivos. Al crear objetivos, seleccione qué métricas de atributos o eVar desea medir o bien, elija que se mida el sitio completo comparándolo con la métrica seleccionada. <p>Los objetivos forman parte de Reports &amp; Analytics. Más información acerca del [Anuncio del final de la vida útil](https://express.adobe.com/page/6WnF8JK6IRDhf/) de Reports &amp; Analytics.</p> | [Objetivos](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/targets.html?lang=en) |
   | Eventos de calendario | Para los informes con tendencias en el paso del tiempo, los eventos de calendario le permiten mostrar gráficamente los eventos y ver si las campañas u otros eventos han afectado al tráfico del sitio, los ingresos o alguna otra métrica. | [Eventos de calendario](https://experienceleague.adobe.com/docs/analytics/components/t-calendar-event.html?lang=en) |
   | Anotaciones | Las anotaciones en Workspace le permiten comunicar de forma eficaz los matices y perspectivas de datos contextuales a su organización. Permiten enlazar eventos de calendario con dimensiones y métricas específicas. | [Administración de anotaciones](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/annotations/manage-annotations.html?lang=en) |
   | Conjuntos de clasificación | Los conjuntos de clasificaciones proporcionan una interfaz única para administrar las clasificaciones y las reglas. <p>Las clasificaciones permiten aplicar categorías a los datos de variables de Analytics para mostrarlos de distintos modos cuando se generan los informes. Se establece una relación entre un valor de variable y los metadatos relacionados con ese valor. Las clasificaciones se pueden utilizar en la mayoría de las dimensiones personalizadas, como el código de seguimiento, las props y las eVars.</p> | [Información general sobre los conjuntos de clasificación](https://experienceleague.adobe.com/docs/analytics/components/classifications/sets/overview.html?lang=es) |
   | Ubicaciones | Para importar datos de clasificación de Adobe Analytics desde un destino de nube, primero debe agregar y configurar la ubicación donde desea que se recopilen los datos de clasificación. Puede crear, editar o eliminar ubicaciones. | [Administrador de ubicaciones](https://experienceleague.adobe.com/docs/analytics/components/locations/locations-manager.html?lang=en) |
   | Proyectos programados | Al administrar proyectos programados, puede editar y eliminar programaciones de proyectos recurrentes; buscar una programación en la barra de búsqueda o utilizando las opciones de filtro en el carril izquierdo; y filtrar por etiqueta, programaciones aprobadas, propietarios y más. | [Proyectos programados](/help/components/scheduled-projects-manager.md) |
   | Marcadores | Los marcadores le permiten acceder a los informes que utiliza con mayor frecuencia. Los marcadores que cree se añadirán a Experience Cloud y estarán disponibles en funciones integradas como los conectores de datos. <p>Los marcadores forman parte de Reports &amp; Analytics. Más información acerca del [Anuncio del final de la vida útil](https://express.adobe.com/page/6WnF8JK6IRDhf/) de Reports &amp; Analytics. | [Administrador de marcadores](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/bookmarks.html?lang=en) |
   | Tableros | Los paneles se crean para visualizar métricas y proporcionar una capacidad analítica interactiva con datos. Al hacer clic en los elementos de un panel, puede segmentar los datos de forma rápida y sencilla para derivar información del análisis. <p>Los paneles son parte de la Data Workbench. Más información sobre la Data Workbench [Anuncio de fin de vida útil](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=en). | [Administrador de tableros](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/dashboard-manage.html?lang=en) |
   | Informes programados | Los usuarios con nivel de administrador pueden ver y administrar informes programados en toda la organización. | [Cola de informes programados](https://experienceleague.adobe.com/docs/analytics/components/scheduled-reports-admin.html?lang=en) |
   | Configuración de informe | Esta configuración hace referencia a productos de Adobe Analytics heredados, que excluyen Analysis Workspace y sus componentes relacionados. Para realizar ajustes en la configuración de Analysis Workspace, vaya a Componentes > Preferencias. |  |
   | Preferencias | Administre la configuración de Analysis Workspace y sus componentes relacionados para todos los proyectos o paneles nuevos que cree. Los proyectos y paneles existentes no se ven afectados. | [Preferencias](/help/analyze/analysis-workspace/user-preferences.md) |

   {style="table-layout:auto"}

+++

+++Ficha Herramientas

<!-- The Tools tab ... -->

1. En Adobe Analytics, seleccione la [!UICONTROL **Herramientas**] pestaña, luego seleccione [!UICONTROL **Todas las herramientas**].

   ![Pestaña Workspace](assets/tools-tab.png)

2. Seleccione cualquiera de las siguientes funciones de producto para configurarlo:

   | Funcionalidad del producto | Función | Más información |
   |---------|----------|----------|
   | Data Warehouse | El Data Warehouse hace referencia a la copia de datos de Analytics para almacenarlos y elaborar informes personalizados, que se pueden ejecutar filtrando los datos. <p>El administrador de solicitudes permite ver, duplicar y volver a priorizar solicitudes.</p> | [Administrar solicitudes del Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-requests-manage.html?lang=en) |
   | Activity Map | Activity Map está diseñado para clasificar la actividad de los vínculos mediante superposiciones visuales y proporciona un tablero de análisis en tiempo real para supervisar la participación de la audiencia en las páginas web. Permite configurar diferentes vistas para identificar visualmente la aceleración de la actividad del cliente, cuantificar las iniciativas de marketing y responder a las necesidades y los comportamientos de la audiencia. | [Preguntas frecuentes sobre Activity Map](https://experienceleague.adobe.com/docs/analytics/analyze/activity-map/activity-map.html?lang=es) |
   | Recommendations Classic | Recommendations es una función de Adobe Target que muestra automáticamente productos, servicios o contenido que podría interesar a sus visitantes en función de la actividad previa del usuario, sus preferencias u otros criterios. | [Recomendaciones](https://experienceleague.adobe.com/docs/target/using/recommendations/recommendations.html?lang=en) |
   | Search&amp;Promote |  |  |
   | Mobile Services |  |  |
   | Paneles de Analytics (aplicación móvil) | La aplicación de paneles de Adobe Analytics ofrece datos de Adobe Analytics en cualquier momento y lugar. A través de la aplicación, los usuarios pueden ver los informes de valoración intuitivos que crea mediante la interfaz de usuario de Adobe Analytics para escritorio. | La aplicación de paneles de Adobe Analytics en la tienda de iOS App Store o Google Play |
   | Report Builder | El Report Builder de Adobe es un complemento para Microsoft Excel. Le permite generar solicitudes personalizadas a partir de datos de Adobe Analytics, que se pueden insertar en sus hojas de cálculo de Excel. Las solicitudes pueden hacer referencia de forma dinámica a las celdas de las hojas de cálculo y es posible actualizar y personalizar el modo en el que Report Builder presenta los datos. | [¿Qué es Report Builder?](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/home.html?lang=es) |

   {style="table-layout:auto"}

+++

+++Ficha Admin

La pestaña Admin incluye funciones y opciones de configuración para administrar Adobe Analytics.

1. En Adobe Analytics, seleccione la [!UICONTROL **Administrador**] pestaña, luego seleccione [!UICONTROL **Todos los administradores**].

   ![Pestaña Workspace](assets/admin-tab.png)

2. Seleccione cualquiera de las siguientes funciones de producto para configurarlo:

   | Funcionalidad del producto | Función | Más información |
   |---------|----------|----------|
   | Usuarios y recursos de Analytics | Aunque la mayoría de las funciones de administración de usuarios y productos ahora solo están disponibles en la [Adobe Admin Console](https://helpx.adobe.com/es/enterprise/using/admin-console.html), las funciones administrativas de transferir recursos de un usuario a otro, así como establecer una fecha de caducidad para una cuenta de usuario, solo están disponibles en el área de Administración de Adobe Analytics. | [Transferir recursos de usuario o establecer caducidades de cuenta](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/user-product-management/users-assets.html?lang=en) |
   | Migración de ID de usuario | La migración de ID de usuarios de Analytics permite a los administradores migrar fácilmente las cuentas de usuario de Administración de usuarios de Analytics a Admin Console de Adobe. | [Migración de usuarios de Analytics a Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/user-product-management/migrate-users/c-migration-tool.html?lang=es) |
   | Inicio de administración de usuarios (heredado) | La administración de usuarios y productos se ha trasladado a Adobe Admin Console. Utilice Adobe Admin Console para empezar a administrar permisos de usuario para usuarios de Adobe Analytics. | [Analytics en Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/home.html?lang=es) |
   | Grupos (heredados) | La administración de grupos se ha trasladado a Adobe Admin Console. Utilice Adobe Admin Console para empezar a administrar grupos para Adobe Analytics. | [Analytics en Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/home.html?lang=es) |
   | Acceso al grupo de informes | El método para conceder acceso a las herramientas del grupo de informes se ha trasladado a Adobe Admin Console. Utilice Adobe Admin Console para conceder acceso al grupo de informes a los usuarios de Adobe Analytics. | [Permisos de perfil de productos para las herramientas de grupo de informes](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/report-suite-tools.html?lang=en) |
   | Inicio de Herramientas de administración |  |  |
   | Grupos de informes | Permite definir las reglas que rigen el modo en que se procesan los datos en un grupo de informes. | [Administrador del grupo de informes](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/report-suites-admin.html?lang=en) |
   | Usuarios y recursos de Analytics | La administración de usuarios y recursos se ha trasladado a Adobe Admin Console. Utilice Adobe Admin Console para empezar a administrar permisos de usuario para usuarios de Adobe Analytics. | [Analytics en Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/home.html?lang=es) |
   | Importador de clasificaciones | Utilice el importador para cargar clasificaciones en Adobe Analytics. También puede exportar los datos para actualizarlos antes de importarlos. | [Resumen del importador de clasificaciones](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/c-working-with-saint.html?lang=en) |
   | Clasificación del generador de reglas | En lugar de mantener y cargar clasificaciones cada vez que cambien sus códigos de seguimiento, puede crear clasificaciones automáticas basadas en reglas y aplicarlas en varios grupos de informes. | [Flujo de trabajo del generador de reglas de clasificación](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-rulebuilder/classification-rule-builder.html?lang=en) |
   | Fuentes de datos | Utilice el administrador de fuentes de datos para crear, editar o desactivar fuentes de datos. También puede utilizar esta interfaz para realizar un seguimiento del estado de los archivos cargados en las ubicaciones FTP de las fuentes de datos. | [Administración de fuentes de datos](https://experienceleague.adobe.com/docs/analytics/import/data-sources/manage.html?lang=en) |
   | Administrador de códigos | El administrador de códigos le permite descargar códigos de recopilación de datos para plataformas web y móviles | [Administrador de códigos](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/code-manager-admin.html?lang=es) |
   | Administración del tráfico | La página Administración del tráfico permite especificar los cambios esperados en el volumen del tráfico. Esta configuración permite a Adobe asignar los recursos adecuados para garantizar un seguimiento y procesamiento adecuados del tráfico. | [Resumen de administración de tráfico](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/traffic-management/traffic-management.html?lang=en) |
   | Uso de llamadas de servidor | Una llamada al servidor, también conocida como “visita individual” o “solicitud de imagen” es una instancia en la que se envían datos a servidores de Adobe para su procesamiento. Hay disponible un panel Uso de llamadas al servidor que rastrea los datos de consumo de llamadas al servidor y lo compara con su límite contractual. Puede configurar alertas para evitar sobrecargas. | [Resumen de Uso de llamadas al servidor](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-call-usage/overage-overview.html?lang=en) |
   | Registros | Los archivos de registro ayudan a ver cuándo los usuarios inician la sesión, su uso, los accesos, los grupos de informes y los cambios del administrador. | [Registros](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/logs.html?lang=es) |
   | Advertising Analytics | Configure Adobe Analytics para que muestre todos los datos de búsqueda de pago de Google y Bing uno al lado del otro. | [Configuración de Advertising Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/advertising-analytics-config.html?lang=en) |
   | Fuentes de datos | Las fuentes de datos son una forma eficaz de obtener datos sin procesar de Adobe Analytics. Estos datos sin procesar se pueden utilizar en otras plataformas fuera de Adobe para su uso según convenga a su organización. | [Resumen de la fuente de datos de Analytics](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-overview.html?lang=es) |
   | Excluir por dirección IP | Se pueden excluir datos de las direcciones IP específicas, por ejemplo, las actividades de sitio web internas, las pruebas del sitio y el uso por parte de los empleados, de los informes. La exclusión de datos elimina los datos de las direcciones IP para conseguir mayor precisión en los informes. También es posible eliminar datos de ataques de negación de servicio u otros eventos dañinos que pueden distorsionar los datos de los informes. Puede configurar la exclusión o utilizar el cortafuegos. | [Excluir por dirección IP](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/exclude-ip.html?lang=en) |
   | Widgets de publicación |  |  |
   | Administrador de actividades de creación de informes | El Administrador de actividades de creación de informes le permite ver la capacidad de creación de informes de cada grupo de informes de su organización. Proporciona una visibilidad detallada del consumo de creación de informes y le ayuda a diagnosticar y corregir problemas de capacidad fácilmente durante las horas de mayor actividad de la creación de informes. | [Administrador de actividades de creación de informes](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/reporting-activity.html?lang=en) |
   | Etiquetado de privacidad de administración de datos | Al etiquetar los datos de los grupos de informes, se asignan etiquetas de identidad, confidencialidad y administración de datos a cada variable de un grupo de informes determinado. | [Etiquetado de datos de grupos de informes](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/data-governance/data-labels/gdpr-setup-reportsuite.html?lang=en) |
   | Inicio de configuración de empresa | La página Configuración de la empresa permite configurar opciones que se aplican a todos los grupos de informes que gestiona la organización. | [Resumen de configuración de empresa](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/company-settings/c-company-settings.html?lang=en) |
   | Administrador de seguridad | El Administrador de seguridad permite controlar el acceso a los datos de informes. Las opciones incluyen contraseñas seguras, caducidad de las contraseñas, restricciones de inicio de sesión de direcciones IP y restricciones de dominio de correo electrónico. | [Administrador de seguridad](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/company-settings/security-manager.html?lang=en) |
   | Información sobre asistencia | La página Información de asistencia administra la información de asistencia que se muestra en Reports &amp; Analytics. Reports &amp; Analytics. <p>A partir del 31 de diciembre de 2023, Adobe tiene la intención de descatalogar Reports &amp; Analytics, y sus informes y funciones correspondientes. Más información acerca del [Anuncio del final de la vida útil](https://www.adobe.com/go/analytics_rnaeol_es) de Reports &amp; Analytics.</p> |  |
   | Servicios Web | Las API de servicios web proporcionan acceso mediante programación a los informes de marketing y a otros servicios de Suite que permiten duplicar y aumentar la funcionalidad disponible a través de la interfaz de Analytics. | [Servicios web](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/company-settings/web-services-admin.html?lang=en) |
   | Informes de Report Builder | Administre la licencia asignada a los usuarios de Report Builder. | [Informes del Report Builder](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/company-settings/report-builder-reports-admin.html?lang=en) |
   | Servicio de inicio de sesión único | El inicio de sesión único de Adobe Experience Cloud se implementa desde Admin Console. | [Analytics en Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/home.html?lang=es) |
   | Promoción conjunta de marca con Adobe Experience Cloud | La página Administrar imagen de promoción conjunta de marca le permite mostrar el logotipo de su empresa en los informes descargados y los paneles heredados de Reports &amp; Analytics. La promoción conjunta de marca no se utiliza en Analysis Workspace.<p>A partir del 31 de diciembre de 2023, Adobe tiene la intención de descatalogar Reports &amp; Analytics, y sus informes y funciones correspondientes. Más información acerca del [Anuncio del final de la vida útil](https://www.adobe.com/go/analytics_rnaeol_es) de Reports &amp; Analytics.</p> | [Promoción conjunta de marca](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/company-settings/co-branding-admin.html?lang=en) |
   | Ocultamiento de grupos de informes | Le permite ocultar grupos de informes en la interfaz de usuario de Adobe Analytics si ya no desea que haya un grupo de informes disponible para usted y los usuarios. | [Ocultar grupos de informes](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/company-settings/c-hide-report-suites.html?lang=en) |  |

   {style="table-layout:auto"}

+++

+++Analysis Workspace

Analysis Workspace le permite crear análisis rápidamente para recopilar información y luego compartirlas con otros. Mediante la interfaz del explorador arrastrar y soltar, puede crear su análisis, añadir visualizaciones para que los datos cobren vida, depurar un conjunto de datos, compartir y programar proyectos con cualquier persona de su organización.

En la siguiente imagen y en la tabla adjunta se explican algunas de las áreas principales de Analysis Workspace.

Para obtener una descripción general más detallada de Analysis Workspace, consulte [Información general de Analysis Workspace](/help/analyze/analysis-workspace/home.md).

![Información general de Analysis Workspace](assets/analysis-workspace-overvew.png)

| Ubicación en la imagen | Nombre y función |
|---------|----------|
| A | **Carril extremo izquierdo:** contiene pestañas para añadir paneles, visualizaciones y componentes a Analysis Workspace. También contiene el icono de Diccionario de datos que se utiliza para abrir el diccionario de datos. |
| B | **Carril izquierdo:** en función de la pestaña seleccionada en el carril del extremo izquierdo, esta área contiene paneles, visualizaciones o componentes individuales. |
| C | **Lienzo:** es el área principal donde se arrastra contenido desde los carriles izquierdos para crear el proyecto. El proyecto se actualiza dinámicamente a medida que se añaden paneles, visualizaciones y componentes al lienzo. |
| D | **Menú desplegable de grupo de informes:** para cada panel de Analysis Workspace, el menú desplegable del grupo de informes le permite elegir el grupo de informes que desea utilizar como fuente de datos. |

+++

## Introducción para administradores, analistas, usuarios finales y desarrolladores

Existen tres tipos de usuarios de Adobe Analytics en una organización típica: administradores, analistas y usuarios finales.

Los administradores implementan y configuran Adobe Analytics, los analistas configuran proyectos y crean análisis con Analysis Workspace y los usuarios finales obtienen perspectivas procesables sobre sus clientes, ya sea creando sus propios análisis o trabajando con los analistas para crearlos.

Expanda las secciones siguientes para conocer cómo cada uno de estos usuarios puede empezar a usar Adobe Analytics.

### Introducción para administradores

Los administradores de Analytics son responsables de elegir el método de implementación más adecuado para su organización.

Una vez implementado Adobe Analytics, los administradores deben realizar varias tareas de configuración para garantizar que los analistas y los usuarios finales obtengan todo el valor de Adobe Analytics. Los administradores también deben monitorizar regularmente su entorno de Analytics para garantizar que el sistema se esté ejecutando de forma eficaz.

#### Determinar los tipos de datos que se deben recopilar

Adobe Analytics le permite recopilar datos de varios tipos de canales y reunirlos para ofrecer perspectivas de clientes significativas en tiempo real.

A continuación se indican algunos de los canales admitidos para recopilar datos:

* Teléfonos móviles

* El Internet de las cosas

* TV

* Asistentes de voz

* Coches conectados

* Y más (regularmente se añaden nuevos canales admitidos)

El [método de implementación](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=es) usted elige determina el tipo de datos que se pueden recopilar.

#### Implementación de Adobe Analytics

Hay varios métodos de implementación disponibles al implementar Adobe Analytics en el sitio web o la aplicación móvil.

Para obtener información sobre cada método disponible, consulte [Implementación de Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=es).

| | Métodos de implementación |
|---------|---------|
| **Sitios web** | <ul><li>Extensión del SDK web (recomendada)</li><li>SDK web</li><li>Extensión de Analytics</li><li>JavaScript heredado</li></ul> |
| **Aplicaciones móviles** | <ul><li>Extensión del SDK móvil (recomendada)</li><li>Extensión de Analytics</li></ul> |

{style="table-layout:auto"}

#### Configuración de Adobe Analytics

Los administradores de Analytics deben completar las siguientes tareas antes de poner Adobe Analytics a disposición de los usuarios de la organización:

| Tarea | Uso previsto | Más información |
|---------|----------|---------|
| Definición de funciones de administrador | Adobe Analytics admite varios tipos de administradores | [Funciones de administrador en Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/admin-roles-in-analytics.html?lang=en) |
| Definición de permisos | Los administradores de Analytics deben asignar perfiles de producto en el Admin Console para Adobe Analytics, Herramientas de grupos de informes y Herramientas de Analytics. | [Permisos de Analytics en Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/summary-tables.html?lang=es) |
| Configure grupos de informes y defina la configuración para su empresa | Un grupo de informes es un silo de datos que Adobe Analytics utiliza para generar informes.<p>Los administradores también pueden configurar [grupos de informes virtuales](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=es) para segmentar más datos.</p> | <ul><li>[Crear un grupo de informes](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/c-new-report-suite/t-create-a-report-suite.html?lang=en)</li><li>[Información general de configuración de empresa](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/company-settings/c-company-settings.html?lang=en)</li></ul> |
| Importar datos | Las fuentes de datos de Adobe Analytics le permiten importar datos adicionales en línea o sin conexión para crear informes. | [Resumen de fuentes de datos](https://experienceleague.adobe.com/docs/analytics/import/data-sources/overview.html?lang=en) |
| Clasificar datos con clasificaciones | Las clasificaciones permiten clasificar los datos para utilizar mejor las variables, lo que permite incluir más contenido en una sola variable. | |
| Administrar componentes | Utilice el diccionario de datos y las áreas de administración para cada tipo de componente para definir qué componentes están disponibles en la implementación de Analytics, así como cuáles están aprobados para su organización.<p>Debe ser una actividad continua para garantizar que los componentes se utilizan correctamente en su organización. </p> | <ul><li>[Información general del diccionario de datos](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.html?lang=es)</li><li>[Administrador de métricas calculadas](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager.html?lang=en)</li><li>[Administración de segmentos](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-manage.html?lang=es)</li><li>[Crear intervalos de fechas](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html?lang=es)</li></ul> |
| Detección de anomalías | La Detección de anomalías constituye un método estadístico para determinar el cambio experimentado en una métrica determinada respecto a los datos anteriores. | [Resumen de la Detección de anomalías](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html?lang=es) |
| Análisis de contribución | Análisis de contribución descubre patrones ocultos en sus datos para explicar las anomalías estadísticas e identificar correlaciones tras acciones de cliente inesperadas, valores que sobrepasan el límite y picos o caídas repentinos de métricas seleccionadas en segmentos de audiencia convergentes. | [Resumen de los análisis de contribución](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.html?lang=es) |
| Segmentación de Analytics | Le permite generar, administrar, compartir y aplicar a sus informes poderosos segmentos centrados en la audiencia utilizando las funcionalidades de Analytics, Adobe Experience Cloud, Adobe Target y otros productos de Adobe integrados. | [Segmentación de Analytics](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html?lang=es) |
| Publicar audiencias en el Audience Manager | | |
| Integraciones | Puede obtener información de otras aplicaciones en Adobe Analytics. <p>A continuación se indican algunas integraciones comunes:</p><ul><li><a href="https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html?lang=en">Analytics for Target</a></li><li><a href="https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html?lang=es">Media Analytics</a></li> | |

{style="table-layout:auto"}

#### Monitorización de Adobe Analytics

Hay varias funciones disponibles para ayudarle a monitorizar su entorno de Adobe Analytics.

Los administradores de Analytics deben tener en cuenta las siguientes funciones disponibles para ayudarle a monitorizar aspectos importantes de su entorno de Analytics:

| Tarea | Uso previsto | Más información |
|---------|----------|---------|
| Administrador de actividades de creación de informes | El Administrador de actividades de creación de informes le permite ver la capacidad de creación de informes de cada grupo de informes de su organización. Proporciona una visibilidad detallada del consumo de creación de informes y le ayuda a diagnosticar y corregir problemas de capacidad fácilmente durante las horas de mayor actividad de la creación de informes. | [Administrador de actividades de creación de informes](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/reporting-activity.html?lang=en) |
| Uso de llamadas de servidor | Una llamada al servidor, también conocida como “visita individual” o “solicitud de imagen” es una instancia en la que se envían datos a servidores de Adobe para su procesamiento. Hay disponible un panel Uso de llamadas al servidor que rastrea los datos de consumo de llamadas al servidor y lo compara con su límite contractual. Puede configurar alertas para evitar sobrecargas. | [Resumen de Uso de llamadas al servidor](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-call-usage/overage-overview.html?lang=en) |
| Archivos de registro | Los archivos de registro ayudan a ver cuándo los usuarios inician la sesión, su uso, los accesos, los grupos de informes y los cambios del administrador. | [Registros](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/logs.html?lang=es) |

{style="table-layout:auto"}

### Introducción para analistas

Aunque cualquier persona de una organización puede utilizar Adobe Analytics para obtener perspectivas procesables sobre el comportamiento de los clientes en sitios web y aplicaciones, Adobe Analytics se ha diseñado teniendo en cuenta a los analistas de datos.

A continuación se indican las tareas y funciones clave con las que los analistas deben estar familiarizados para aprovechar toda la potencia de Adobe Analytics y Analysis Workspace.

| Funcionalidad | Uso previsto | Más información |
|---------|----------|---------|
| Generar y compartir proyectos en Analysis Workspace | Analysis Workspace es una herramienta de navegador flexible que le permite crear análisis y compartir perspectivas rápidamente. Mediante la interfaz de arrastrar y soltar, puede crear su análisis, agregar visualizaciones para dar vida a los datos, depurar un conjunto de datos, compartir y programar proyectos con cualquier persona de su organización.<p>Los analistas de datos suelen ser responsables de crear proyectos en Analysis Workspace para usuarios dentro de su organización.</p><p>Una vez creados los proyectos, los analistas los comparten con el [usuarios finales](#end-users)(no analistas) en sus organizaciones que solicitaron los datos y les ayudan a comprender cómo interpretarlos.</p> | <ul><li>[Crear proyectos](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md)</li><li>[Compartir proyectos](/help/analyze/analysis-workspace/curate-share/share-projects.md)</li></ul> |
| Atribución | Los analistas pueden personalizar la forma en que los elementos de dimensión obtienen crédito por los eventos de éxito empleando varios modelos de atribución y ventanas retrospectivas en Analysis Workspace.<p>Los modelos de atribución lineal dan el mismo crédito a cada punto de contacto que conduce a una conversión, mientras que Primer contacto da crédito total al primer punto de contacto. Hay muchos otros modelos de atribución disponibles, incluido el modelo algorítmico, que utiliza técnicas estadísticas para determinar dinámicamente la asignación óptima de crédito. </p> | [Modelos de atribución y ventanas retroactivas](/help/analyze/analysis-workspace/attribution/models.md) |
| Detección de anomalías | El modelado estadístico en Analysis Workspace encuentra automáticamente tendencias inesperadas en los datos analizando métricas y determinando un límite inferior, límite superior y rango esperado de valores. Cuando hay un pico o una caída inesperados, el sistema le alerta en el informe. | [Resumen de la Detección de anomalías](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) |
| Análisis de contribución | Utilice Analysis Workspace para descubrir patrones ocultos en los datos a fin de explicar las anomalías estadísticas e identificar correlaciones tras acciones de cliente inesperadas, valores que sobrepasan el límite y caídas o picos repentinos de métricas entre segmentos de audiencia. | [Resumen de los análisis de contribución](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.md) |
| Alertas inteligentes | Crear y administrar alertas basadas en anomalías de datos y alertas &quot;apiladas&quot; que capturan varias métricas en una sola alerta. | [Resumen de las alertas inteligentes](/help/analyze/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md) |
| Exportación de datos | Las fuentes de datos y Data Warehouse le permiten exportar datos a varios destinos de nube, como Google Cloud Platform, Azure RBAC, Azure SAS y Amazon S3. | [Guía de exportación de Analytics](https://experienceleague.adobe.com/docs/analytics/export/home.html?lang=es) |
| Activity Map | Activity Map es una aplicación de Adobe Analytics diseñada para clasificar la actividad de los vínculos usando superposiciones visuales y que ofrece un tablero de análisis en tiempo real para supervisar la participación de la audiencia en las páginas web.<p>Activity Map permite configurar distintas vistas para identificar visualmente la aceleración de la actividad del cliente, cuantificar las iniciativas de marketing y responder a las necesidades y los comportamientos de la audiencia.</p> | [Activity Map](https://experienceleague.adobe.com/docs/analytics/analyze/activity-map/activity-map.html?lang=es) |
| Report Builder | El Report Builder es un complemento para Microsoft Excel. Report Builder permite crear solicitudes personalizadas a partir de datos de Adobe Analytics que se insertan en hojas de cálculo de Excel. Las solicitudes pueden hacer referencia de forma dinámica a las celdas de las hojas de cálculo y es posible actualizar y personalizar el modo en el que Report Builder presenta los datos. | [Report Builder](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/home.html?lang=es) |

{style="table-layout:auto"}

<!-- * Realtime reporting? -->

### Introducción para usuarios finales

Los usuarios finales que no son analistas profesionales pueden trabajar con analistas de su organización para aprovechar todo el poder de Adobe Analytics y Analysis Workspace, o pueden aprender los conceptos básicos de Analysis Workspace para empezar a obtener perspectivas procesables sobre sus clientes.

#### Trabajo con analistas

Normalmente, los usuarios de una organización interesados en obtener más información sobre el comportamiento de los clientes en sus distintos sitios no son analistas profesionales.

Lo ideal es que estos usuarios trabajen con [analistas](#analysts) dentro de una organización para:

1. Defina los requisitos para los análisis explicando al analista lo que espera aprender acerca de los clientes.

1. Revise los análisis para asegurarse de que cumplen los objetivos.

1. Analizar los datos obtenidos de los análisis.

1. Modifique los análisis según sea necesario a lo largo del tiempo.

#### Creación de análisis en Analysis Workspace

No es necesario ser analista de datos para obtener perspectivas procesables de Adobe Analytics.

A algunos usuarios les puede resultar útil trabajar con un analista de datos para configurar un proyecto en Analysis Workspace y explicar cómo interpretar los datos, tal como se describe en [Trabajo con analistas](#work-with-analysts); otros usuarios podrían sentirse cómodos creando el proyecto e interpretando los datos ellos mismos.

Analysis Workspace le permite crear análisis rápidamente para recopilar información y luego compartirlas con otros. Mediante la interfaz del explorador arrastrar y soltar, puede crear su análisis, añadir visualizaciones para que los datos cobren vida, depurar un conjunto de datos, compartir y programar proyectos con cualquier persona de su organización.

Para obtener información sobre cómo crear análisis en Analysis Workspace, consulte [Información general de Analysis Workspace](/help/analyze/analysis-workspace/home.md).

### Introducción para desarrolladores

[Las API de Analytics le permiten llamar directamente a los servidores de Adobe para realizar casi cualquier acción que pueda hacer en la interfaz de usuario.](https://developer.adobe.com/analytics-apis/docs/2.0/)

Puede crear informes para explorar, obtener perspectivas o responder a preguntas importantes acerca de sus datos. También puede administrar componentes de Adobe Analytics, como la creación de segmentos o métricas calculadas.

## Información general del vídeo

Para obtener más información sobre los conceptos básicos de Adobe Analytics, consulte esto *Introducción a Adobe Analytics: Seminario web de Skills Builder* vídeo. El vídeo le explica cómo se capturan los datos, cómo se envían a Adobe Analytics y qué capacidades de visualización puede utilizar en Adobe Analytics. El vídeo proporciona una base para crear, implementar, recopilar e interpretar los datos, lo que le permite proporcionar perspectivas procesables y recomendaciones basadas en los datos recopilados.

>[!VIDEO](https://video.tv.adobe.com/v/27429/?quality=12)

Si tiene preguntas acerca de qué herramienta utilizar, consulte [¿Qué herramienta de Adobe Analytics debo usar?](https://experienceleague.adobe.com/docs/analytics/analyze/admin-overview/which-analytics-tool.html?lang=es).

## Ir más allá con el Customer Journey Analytics

Customer Journey Analytics es una solución de análisis de próxima generación que le permite utilizar la potencia de Analysis Workspace con los datos de Adobe Experience Platform. Puede desglosar, filtrar, consultar y visualizar datos de años, y se combina con la capacidad de Platform de albergar todo tipo de esquemas y tipos de datos.

A continuación se indican algunas de las ventajas de Customer Journey Analytics sobre Adobe Analytics:

* **Eventos y variables ilimitadas**: los conceptos de eVars, props y eventos ya no existen. Los datos se centran principalmente en dimensiones y métricas. Los conjuntos de datos pueden tener un número ilimitado de dimensiones y métricas únicas.

* **Valores únicos ilimitados**: Adobe Experience Platform no se limita a ninguna limitación única.

* **Modificar datos históricos**: con Adobe Experience Platform, los datos se pueden eliminar o corregir.

* **Datos de grupos de informes múltiples**: las implementaciones existentes de varios conjuntos de datos se pueden combinar en Platform.

Para obtener más información, consulte [Introducción al Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=es).


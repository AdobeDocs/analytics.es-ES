---
title: Últimas notas de la versión de Analytics
description: Vea las notas de la versión actuales de Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: c29515da8c74ad3332aa9797db9de505af7fe3aa
workflow-type: ht
source-wordcount: '1070'
ht-degree: 100%

---

# Notas de la versión actuales de Adobe Analytics (abril de 2022)

**Última actualización**: 28 de abril de 2022

## Recursos relacionados

* [Notas de la versión anteriores de 2022](/help/release-notes/2022.md)
* [Notas de la versión de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=es)
* [Notas de la versión de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
* Las últimas actualizaciones de la versión para los [productos de Adobe Experience Cloud](https://business.adobe.com/es/products/adobe-experience-cloud-products.html)

## Funciones nuevas en Adobe Analytics

| Función | Descripción | [Fecha objetivo](releases.md) |
| ----------- | ---------- | ------- |
| Actualizaciones de la página de aterrizaje de Adobe Analytics | Actualizaciones de la página de aterrizaje conjunta de Analysis Workspace/Reports &amp; Analytics que mejora la facilidad de uso y navegación. [Más información](/help/analyze/landing.md) | 20 de abril de 2022 |
| [!UICONTROL Elemento siguiente] o [!UICONTROL Elemento anterior] Panel de espacio de trabajo | El panel [!UICONTROL Elemento siguiente o anterior] permite explorar elementos que siguen o preceden a un elemento de dimensión de su elección. Por ejemplo, utilícelo si desea ver las páginas siguientes o anteriores de una página de producto, un canal de marketing o incluso un tipo de dispositivo específicos. Este panel va más allá de la creación de informes anteriores o siguientes, ya que le permite ver cualquier dimensión y no requiere ninguna implementación nueva para obtener información. [Más información](/help/analyze/analysis-workspace/c-panels/next-previous.md) | 20 de abril de 2022 |
| [!UICONTROL Resumen de página] Panel de espacio de trabajo | El panel [!UICONTROL Resumen de página] proporciona un análisis en profundidad para una página de su elección. Proporciona los mismos detalles que el informe del [!UICONTROL Resumen de página] de Reports &amp; Analytics heredados, más mucho más. [Más información](/help/analyze/analysis-workspace/c-panels/page-summary.md) | 20 de abril de 2022 |
| Se ha eliminado el requisito del encabezado `x-proxy-global-company-id` para llamadas a la API 2.0 | Las API de Adobe Analytics 2.0 ya no requieren el encabezado `x-proxy-global-company-id`, ya que esta información forma parte de la dirección URL del punto de conexión. Puede seguir incluyendo este encabezado, pero ya no recibirá ningún error si falta. | 20 de abril de 2022 |

{style=&quot;table-layout:auto&quot;}

## Correcciones en Adobe Analytics

* Se ha corregido un problema en Fuentes de datos por el cual las fechas de inicio y finalización cambiaban automáticamente después de guardar la fuente de datos al crearla desde la interfaz de usuario de la fuente de datos. Las fechas se estaban actualizando por un día. (AN-281262)
* Se ha corregido un problema que impedía la renovación de proyectos programados mediante un vínculo de correo electrónico. (AN-283622)
* Se ha corregido un problema que provocaba que las versiones recientes de Apple Safari y Microsoft Edge no se identificaran correctamente en la tabla de búsqueda para el tipo de explorador de Adobe. Al igual que cuando [se actualizan las versiones de los exploradores](/help/components/dimensions/browser.md), las actualizaciones de las tablas de búsqueda para el tipo de explorador solo corrigen los datos en adelante. Las tablas de búsqueda para la versión del explorador se actualizaron el 20 de abril y las tablas de búsqueda para el tipo de explorador, el 28 de abril. (AN-284872; AN-285753; AN-286257)

### Correcciones adicionales en Adobe Analytics

AN-274486; AN-279258; AN-279995; AN-280918; AN-281423; AN-282084; AN-282435; AN-283508; AN-283517; AN-283706; AN-283762; AN-283921; AN-284195; AN-284663; AN-284573; AN-284721; AN-284790; AN-284867; AN-284870; AN-284872; AN-284884; AN-284914; AN-284930; AN-284933; AN-284967; AN-284970; AN-285187; AN-285328; AN-285337; AN-285375; AN-285447; AN-285724; AN-285753; AN-285761

## Avisos importantes para los administradores de Adobe Analytics

| Aviso | Fecha de incorporación o actualizada | Descripción |
| ----------- | ---------- | ---------- |
| **Derechos de Analytics entre dispositivos (CDA)** | 13 de abril de 2022 | A partir del **1 de mayo de 2022**, cualquier nueva implementación de [análisis multidispositivo](/help/components/cda/overview.md) se limitará a un máximo de tres ID de grupo de informes (RSID) por cliente. |
| **Cambio del modo en que Adobe Analytics gestiona los datos de A4T recopilados mediante Experience Edge** | 31 de marzo de 2022 | El 7 de marzo de 2022, Analytics cambió la forma en que gestiona algunas llamadas procedentes de Experience Edge que incluyen contenido de Target destinado a la creación de informes en Analytics for Target (A4T). A partir del 7 de marzo, todas las visitas con contenido de creación de informes de A4T se modificaron para que no se trataran como eventos de vista de página o de vínculo. A partir del **31 de marzo de 2022**, la lógica es más selectiva, de modo que los eventos estándar de vista de página y clics no se modifiquen. En adelante, los únicos eventos que se modifican son las llamadas de solo personalización que únicamente tengan contenido de A4T. |
| **Actualización de los métodos de cifrado del explorador admitidos para determinados clientes** | 28 de marzo de 2022 | Adobe ofrece dos niveles de seguridad de cifrado para satisfacer las distintas necesidades de seguridad de los clientes en la recopilación de datos de origen. El **23 de junio de 2022** se eliminará la compatibilidad con ciertos algoritmos de codificación HTTPS, conocidos como cifrados, para clientes con su nivel de seguridad establecido en Alto. Esta acción significa que algunos sistemas operativos antiguos ya no podrán enviar datos a Analytics porque no son compatibles con los métodos de cifrado modernos. Los clientes que utilicen la configuración predeterminada de seguridad de cifrado Estándar no se ven afectados. Ya se ha contactado directamente con todos los clientes que actualmente usan la configuración “Alta”. Aquí puede encontrar una lista detallada de las cifras afectadas por este cambio. |
| **Pausa de informes programados antiguos** | 12 de abril de 2022 | A partir del **20 de abril de 2022**, Adobe tiene la intención de poner en pausa todos los informes programados que tengan una fecha de creación mayor de dos años (creados antes del 31 de enero de 2020). No se eliminan informes ni datos. Solo los informes identificados como anteriores a dos años se pausan y no se envían informes programados adicionales. Más información |
| **Actualizaciones de región ISO 2022** | 11 de marzo de 2021 | Adobe planea llevar a cabo actualizaciones de la zona ISO 2022 el **10 de junio de 2022**. Es de esperar que se produzcan pequeñas actualizaciones de la información geográfica tras este lanzamiento. |
| **Pausa de tareas de Report Builder programadas más antiguas** | 12 de abril de 2022 | A partir del **20 de abril de 2022**, Adobe tiene la intención de poner en pausa todas las tareas de Report Builder programadas que se crearon hace más de dos años. En concreto, esta pausa se aplica a cualquier tarea creada antes del 31 de enero de 2020. No se eliminan tareas, libros ni datos. Sin embargo, las tareas identificadas como anteriores a dos años se pausan y no se envían tareas programadas adicionales. Más información |
| **Caducidad de la extensión EOL de la inclusión en la lista de permitidos para integraciones heredadas de Analytics OAuth/JWT** | 14 de enero de 2022 | El **25 de mayo de 2022** caducan la extensión de lista de permitidos de [API de Analytics 1.3, API de SOAP 1.4 y EOL de OAuth/JWT de Analytics heredado](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/APIEOL.md). Se ofreció para proporcionar a los clientes que usan las credenciales de OAuth/JWT de [!DNL Adobe Analytics] más tiempo para migrar sus integraciones de cliente a las [credenciales de IMS de Adobe](https://developer.adobe.com/console). Esta caducidad afecta a clientes [!DNL Adobe Analytics Livestream] y [!DNL Adobe Campaign] (entre otros) que no hayan completado las migraciones de IMS requeridas. Los clientes que actualmente utilizan las credenciales de OAuth/JWT de [!DNL Analytics] heredado a través de la extensión de inclusión en la lista de permitidos, y que no hayan completado su migración a las credenciales de IMS antes del 25 de mayo de 2022, pierden el acceso a los servicios de Adobe. Los clientes de Livestream pueden consultar estas [instrucciones](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) al migrar sus aplicaciones cliente a credenciales de IMS. [!DNL Campaign] clientes pueden ponerse en contacto con el equipo de su cuenta de Adobe para actualizar a la última versión de [!DNL Campaign]. |
| **EOL para [!DNL Reports & Analytics]** | 4 de enero de 2022 | A partir del **31 de diciembre de 2023**, Adobe tiene la intención de descatalogar [!DNL Reports & Analytics] y sus informes y funciones correspondientes. Los informes, las visualizaciones y la tecnología subyacente que alimentan [!DNL Reports & Analytics] ya no cumplen los estándares tecnológicos de Adobe. La mayoría de las funciones de [!DNL Reports & Analytics] están disponibles en [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=es). Desde el lanzamiento de Analysis Workspace en 2015, las funcionalidades y capacidades de [!DNL Reports & Analytics] se han trasladado a Analysis Workspace y se ha alcanzado un umbral de paridad de flujo de trabajo. [Este aviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) explica el proceso de finalización de la vida útil. |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement {#appm}

Para obtener las últimas actualizaciones de las versiones de AppMeasurement (2.22.4), consulte las [notas de la versión de AppMeasurement para JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=es).

>[!MORELIKETHIS]
>[[!DNL Customer Journey Analytics] Notas de la versión](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=es)

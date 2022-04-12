---
title: Últimas notas de la versión de Analytics
description: Vea las notas de la versión actuales de Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 1e8aa373bcb2714c6b2c7605e1ea7c7c462b89e7
workflow-type: tm+mt
source-wordcount: '1166'
ht-degree: 45%

---

# Notas de la versión actual de Adobe Analytics (marzo de 2022)

**Última actualización: 12 de abril de 2022**

* Para ver las notas de la versión de febrero de 2022, vaya [here](/help/release-notes/2022.md).
* Para obtener las notas de la versión de Customer Journey Analytics, vaya a [here](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=es)
* Para ver las notas de la versión de Media Analytics, vaya a [here](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=en)
* Obtenga información sobre las últimas actualizaciones de la versión para [productos de Adobe Experience Cloud](https://business.adobe.com/es/products/adobe-experience-cloud-products.html). Obtenga la documentación de autoayuda más reciente, tutoriales y cursos sobre Experience League.

## Funciones nuevas en Adobe Analytics {#aa-features}

| Función | Descripción | [Fecha objetivo](releases.md) |
| ----------- | ---------- | ------- |
| Anotaciones en Workspace | Las anotaciones en Workspace le permiten comunicar de forma eficaz los matices y perspectivas de datos contextuales a su organización. [Más información](/help/analyze/analysis-workspace/components/annotations/overview.md) | La implementación gradual comienza el 23 de marzo de 2022. Disponibilidad general: 11 de abril de 2022 |
| Actualizaciones de la página de aterrizaje de Adobe Analytics | Actualizaciones de la página de aterrizaje conjunta de Workspace/Reports &amp; Analytics que mejora la facilidad de uso y navegación. [Más información](/help/analyze/landing.md) | 20 de abril de 2022 |
| [!UICONTROL Elemento siguiente] o [!UICONTROL Elemento anterior] Panel de Workspace | La variable [!UICONTROL Elemento siguiente o anterior] permite explorar elementos que siguen o preceden a un elemento de dimensión de su elección. Por ejemplo, utilícelo si desea ver las páginas siguientes o anteriores de una página de producto, un canal de marketing o incluso un tipo de dispositivo específicos. Este panel va más allá de los informes anteriores o siguientes, ya que le permite ver cualquier dimensión y no requiere ninguna implementación nueva para obtener información. | 20 de abril de 2022 |
| [!UICONTROL Resumen de página] Panel de Workspace | La variable [!UICONTROL Resumen de página] proporciona un análisis en profundidad para una página de su elección. Proporciona los mismos detalles que los informes y análisis heredados [!UICONTROL Resumen de página] informe, más mucho más. | 20 de abril de 2022 |

{style=&quot;table-layout:auto&quot;}

## Correcciones en Adobe Analytics

* Se ha corregido un problema que provocaba un error al intentar acceder al Activity Map. (AN-267177)
* Se ha corregido un problema por el que las transferencias de recursos de usuario no se realizaban correctamente. (AN-279813)
* Se han corregido problemas con el panel Espacio de trabajo de A4T. (AN-281594; AN-282418)
* Se ha corregido un problema por el que algunos usuarios no podían acceder a Adobe Analytics. (AN-282776)
* Se han corregido problemas con algunos grupos de informes recién creados que no recopilaban datos. (AN-283114, AN-283311)
* Se han corregido problemas con los correos electrónicos de fuentes de datos enviados incorrectamente. (AN-280255; AN-282051)

### Correcciones adicionales en Adobe Analytics

AN-256929; AN-270937; AN-272158; AN-275130; AN-277830; AN-278635; AN-279066; AN-279683; AN-279899; AN-280504; AN-280617; AN-280663; AN-281423; AN-281523; AN-281608; AN-281671; AN-281963; AN-282027; AN-282218; AN-282593; AN-282605; AN-282632; AN-282654; AN-282694; AN-282744; AN-282756; AN-282804; AN-282838; AN-282862; AN-282903; AN-282937; AN-282892; AN-283315; AN-283338; AN-283388; AN-283417; AN-283474; AN-283511; AN-283691, AN-283895; AN-283943; AN-283957; AN-284030; AN-284100; AN-284142; AN-284162

## Avisos importantes para los administradores de Adobe Analytics

| Aviso | Fecha de incorporación o actualizada | Descripción |
| ----------- | ---------- | ---------- |
| Cambio en la forma en que Analytics gestiona los datos de A4T recopilados mediante Experience Edge | 31 de marzo de 2022 | Activado **7 de marzo de 2022**, hemos cambiado la forma de gestionar algunas llamadas procedentes de Experience Edge que incluyen contenido de Target destinado a la creación de informes en Analytics for Target (A4T). A partir del 7 de marzo, todas las visitas con contenido de informes de A4T se modificaron para que no se trataran como eventos de vista de página o de vínculo. **A partir del 31 de marzo de 2022**, hemos cambiado nuestra lógica para que sea más selectiva, de modo que los eventos estándar de vista de página y clics no se modifiquen. En adelante, los únicos eventos que se modificarán serán las llamadas de solo personalización que solo tengan contenido de A4T. |
| Actualización de los métodos de cifrado del navegador admitidos para determinados clientes | 28 de marzo de 2022 | Adobe ofrece dos niveles de seguridad de cifrado para satisfacer las distintas necesidades de seguridad de los clientes en la recopilación de datos de origen. Activado **23 de junio de 2022** se eliminará la compatibilidad con ciertos algoritmos de codificación HTTPS, conocidos como cifrados, para clientes con su nivel de seguridad establecido en &quot;Alto&quot;. Esto significa que algunos sistemas operativos antiguos ya no podrán enviar datos a Analytics porque no son compatibles con los métodos de cifrado modernos. Los clientes que utilicen la configuración predeterminada de seguridad de cifrado &quot;Estándar&quot; no se verán afectados. Ya se ha contactado directamente con todos los clientes que actualmente usan la configuración &quot;Alta&quot;. Puede encontrar una lista detallada de las cifras afectadas por este cambio [here](/help/technotes/rdc/encryption-algos.md). |
| Pausa de informes programados más antiguos | 12 de abril de 2022 | Efectivo **21 de abril de 2022**, Adobe tiene la intención de poner en pausa todos los informes programados que tengan una fecha de creación buena de dos años (creados antes del 31 de enero de 2020). No se eliminarán informes ni datos. Solo se pausarán los informes identificados como de más de dos años y no se enviarán informes programados adicionales. Cualquier informe con una fecha de creación inferior a dos años sin fecha de caducidad (o con una fecha de caducidad superior a dos años) tendrá aplicada una fecha de caducidad predeterminada de 9 meses. [Más información](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| Actualizaciones de región ISO 2022 | 11 de marzo de 2021 | Adobe realizará actualizaciones de la región ISO 2022 en **10 de junio de 2022**. Después de esta versión se esperan actualizaciones menores de la información geográfica. |
| Pausa de tareas de Report Builder programadas más antiguas | 12 de abril de 2022 | **A partir del 21 de abril de 2022**, Adobe tiene la intención de poner en pausa todas las tareas de Report Builder programadas que se crearon hace más de dos años. En concreto, esta pausa se aplica a cualquier tarea creada antes del 31 de enero de 2020. No se eliminarán tareas, libros ni datos. Sin embargo, las tareas identificadas como anteriores a dos años se pausarán y no se enviarán tareas programadas adicionales. [Más información](/help/analyze/report-builder/r-arb-scheduled-reports.md) |
| Caducidad de la extensión EOL de la lista de permitidos para integraciones heredadas de Analytics OAuth/JWT | 14 de enero de 2022 | El **25 de mayo de 2022**, la extensión de lista de permitidos de [API de Analytics 1.3, API de SOAP 1.4 y EOL de OAuth/JWT de Analytics heredado](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/APIEOL.md) caducará. Se ofreció para proporcionar a los clientes que usan las credenciales de OAuth/JWT de [!DNL Adobe Analytics] más tiempo para migrar sus integraciones de cliente a las [credenciales de IMS de Adobe](https://developer.adobe.com/console). Esta caducidad afecta a clientes [!DNL Adobe Analytics Livestream] y [!DNL Adobe Campaign] (entre otros) que no hayan completado las migraciones de IMS requeridas. Clientes que actualmente utilizan las credenciales de la versión heredada [!DNL Analytics] OAuth/JWT a través de la extensión de la lista de permitidos y que no hayan completado su migración a las credenciales de IMS antes del 25 de mayo de 2022 perderán acceso a los servicios de Adobe. Los clientes de Livestream pueden consultar estas [instrucciones](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) al migrar sus aplicaciones cliente a credenciales de IMS. [!DNL Campaign] clientes pueden ponerse en contacto con el equipo de su cuenta de Adobe para actualizar a la última versión de [!DNL Campaign]. |
| Actualización de servicios del Protocolo seguro de transferencia de archivos (SFTP) | 3 de marzo de 2022 | El **15 de mayo de 2022**, [!DNL Adobe Analytics] actualizará sus servicios de Protocolo seguro de transferencia de archivos (SFTP) para proporcionar una seguridad mejorada para las transferencias de archivos. Con este cambio, algunas configuraciones de cliente SFTP ya no serán compatibles. También añadiremos algunas opciones de conexión que estarán disponibles el **1 de marzo de 2022**. Esto solo afecta a los datos enviados o recuperados de Adobe Analytics mediante SFTP. El protocolo FTP no se ve afectado. Para evitar interrupciones en el servicio, asegúrese de que sus clientes SFTP (código, herramientas y servicios) estén de acuerdo con los cambios detallados [aquí](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=es). |
| EOL para [!DNL Reports & Analytics] | 4 de enero de 2022 | A partir del **31 de diciembre de 2023**, Adobe tiene la intención de descatalogar [!DNL Reports & Analytics] y sus informes y funciones correspondientes. Los informes, las visualizaciones y la tecnología subyacente que alimentan [!DNL Reports & Analytics] ya no cumplen los estándares tecnológicos de Adobe. La mayoría de las funciones de [!DNL Reports & Analytics] están disponibles en [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=es). Desde el lanzamiento de Analysis Workspace en 2015, las funcionalidades y capacidades de [!DNL Reports & Analytics] se han trasladado a Analysis Workspace y se ha alcanzado un umbral de paridad de flujo de trabajo. [Este aviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) explica el proceso de finalización de la vida útil. |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement {#appm}

Para obtener las últimas actualizaciones de las versiones de AppMeasurement (2.22.4), consulte las [notas de la versión de AppMeasurement para JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=es).

>[!MORELIKETHIS]
>[[!DNL Customer Journey Analytics] Notas de la versión](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=en)

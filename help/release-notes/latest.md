---
title: Últimas notas de la versión de Analytics
description: Vea las notas de la versión actuales de Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 31387d369428727a486a19b986bf9d891a36e714
workflow-type: tm+mt
source-wordcount: '877'
ht-degree: 86%

---

# Notas de la versión actual de Adobe Analytics (mayo de 2022)

**Última actualización**: 17 de mayo de 2022

>[!NOTE]
>
>Esta página contiene información previa al lanzamiento y está sujeta a cambios.

## Recursos relacionados

* [Notas de la versión anteriores de 2022](/help/release-notes/2022.md)
* [Notas de la versión de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=es)
* [Notas de la versión de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
* Las últimas actualizaciones de la versión para los [productos de Adobe Experience Cloud](https://business.adobe.com/es/products/adobe-experience-cloud-products.html)

## Funciones nuevas en Adobe Analytics

| Función | Descripción | [Fecha objetivo](releases.md) |
| ----------- | ---------- | ------- |
| No hay nuevas funciones este mes | N/A | N/D |

{style=&quot;table-layout:auto&quot;}

### Correcciones en Adobe Analytics

(Correcciones para varios clientes)

N/D

### Correcciones adicionales en Adobe Analytics

(Correcciones para clientes individuales)

AN-274429; AN-279640; AN-280918; AN-280945; AN-282884; AN-283565; AN-284785; AN-284814; AN-284854; AN-284989; AN-285244; AN-285253; AN-285432; AN-285528; AN-285535; AN-285710; AN-286255; AN-286340; AN-286434; AN-286454; AN-286630; AN-286716; AN-286854; AN-286911

### Avisos importantes para los administradores de Adobe Analytics

| Aviso | Fecha de incorporación o actualizada | Descripción |
| ----------- | ---------- | ---------- |
| **Actualización de SFTP** | 9 de mayo de 2022 | Anteriormente, habíamos comunicado que el Adobe actualizaría sus servicios de Protocolo seguro de transferencia de archivos (SFTP) en mayo de 2022 para proporcionar una seguridad mejorada para la transferencia de archivos. Hemos pospuesto esta actualización hasta el verano de 2022. Cuando se realice este cambio, ya no se admitirán determinadas configuraciones de cliente SFTP. Esto solo afecta a los datos enviados o recuperados de Adobe Analytics mediante SFTP. El protocolo FTP no se ve afectado. Para evitar interrupciones en el servicio, asegúrese de que sus clientes SFTP (código, herramientas y servicios) estén de acuerdo con los cambios detallados [aquí](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=es). |
| **Derechos de Analytics entre dispositivos (CDA)** | 13 de abril de 2022 | Efectivo **1 de mayo de 2022**, cualquier implementación nueva de [CDA](/help/components/cda/overview.md) están limitadas a un máximo de tres ID de grupos de informes (RSID) por cliente. |
| **Cambio del modo en que Adobe Analytics gestiona los datos de A4T recopilados mediante Experience Edge** | 31 de marzo de 2022 | El 7 de marzo de 2022, Analytics cambió la forma en que gestiona algunas llamadas procedentes de Experience Edge que incluyen contenido de Target destinado a la creación de informes en Analytics for Target (A4T). A partir del 7 de marzo, todas las visitas con contenido de creación de informes de A4T se modificaron para que no se trataran como eventos de vista de página o de vínculo. A partir del **31 de marzo de 2022**, la lógica es más selectiva, de modo que los eventos estándar de vista de página y clics no se modifiquen. En adelante, los únicos eventos que se modifican son las llamadas de solo personalización que únicamente tengan contenido de A4T. |
| **Actualización de los métodos de cifrado del explorador admitidos para determinados clientes** | 28 de marzo de 2022 | Adobe ofrece dos niveles de seguridad de cifrado para satisfacer las distintas necesidades de seguridad de los clientes en la recopilación de datos de origen. El **23 de junio de 2022** se eliminará la compatibilidad con ciertos algoritmos de codificación HTTPS, conocidos como cifrados, para clientes con su nivel de seguridad establecido en Alto. Esta acción significa que algunos sistemas operativos antiguos ya no podrán enviar datos a Analytics porque no son compatibles con los métodos de cifrado modernos. Los clientes que utilicen la configuración predeterminada de seguridad de cifrado Estándar no se ven afectados. Ya se ha contactado directamente con todos los clientes que actualmente usan la configuración “Alta”. Aquí puede encontrar una lista detallada de las cifras afectadas por este cambio. |
| **Pausa de informes programados antiguos** | 12 de abril de 2022 | A partir del **20 de abril de 2022**, Adobe tiene la intención de poner en pausa todos los informes programados que tengan una fecha de creación mayor de dos años (creados antes del 31 de enero de 2020). No se eliminan informes ni datos. Solo los informes identificados como anteriores a dos años se pausan y no se envían informes programados adicionales. Más información |
| **Actualizaciones de región ISO 2022** | 11 de marzo de 2021 | Adobe planea llevar a cabo actualizaciones de la zona ISO 2022 el **10 de junio de 2022**. Es de esperar que se produzcan pequeñas actualizaciones de la información geográfica tras este lanzamiento. |
| **Pausa de tareas de Report Builder programadas más antiguas** | 12 de abril de 2022 | A partir del **20 de abril de 2022**, Adobe tiene la intención de poner en pausa todas las tareas de Report Builder programadas que se crearon hace más de dos años. En concreto, esta pausa se aplica a cualquier tarea creada antes del 31 de enero de 2020. No se eliminan tareas, libros ni datos. Sin embargo, las tareas identificadas como anteriores a dos años se pausan y no se envían tareas programadas adicionales. Más información |
| **Caducidad de la extensión EOL de la inclusión en la lista de permitidos para integraciones heredadas de Analytics OAuth/JWT** | 14 de enero de 2022 | El **25 de mayo de 2022** caducan la extensión de lista de permitidos de [API de Analytics 1.3, API de SOAP 1.4 y EOL de OAuth/JWT de Analytics heredado](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/APIEOL.md). Se ofreció para proporcionar a los clientes que usan las credenciales de OAuth/JWT de [!DNL Adobe Analytics] más tiempo para migrar sus integraciones de cliente a las [credenciales de IMS de Adobe](https://developer.adobe.com/console). Esta caducidad afecta a clientes [!DNL Adobe Analytics Livestream] y [!DNL Adobe Campaign] (entre otros) que no hayan completado las migraciones de IMS requeridas. Los clientes que actualmente utilizan las credenciales de OAuth/JWT de [!DNL Analytics] heredado a través de la extensión de inclusión en la lista de permitidos, y que no hayan completado su migración a las credenciales de IMS antes del 25 de mayo de 2022, pierden el acceso a los servicios de Adobe. Los clientes de Livestream pueden consultar estas [instrucciones](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) al migrar sus aplicaciones cliente a credenciales de IMS. [!DNL Campaign] clientes pueden ponerse en contacto con el equipo de su cuenta de Adobe para actualizar a la última versión de [!DNL Campaign]. |
| **EOL para [!DNL Reports & Analytics]** | 4 de enero de 2022 | A partir del **31 de diciembre de 2023**, Adobe tiene la intención de descatalogar [!DNL Reports & Analytics] y sus informes y funciones correspondientes. Los informes, las visualizaciones y la tecnología subyacente que alimentan [!DNL Reports & Analytics] ya no cumplen los estándares tecnológicos de Adobe. La mayoría de las funciones de [!DNL Reports & Analytics] están disponibles en [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=es). Desde el lanzamiento de Analysis Workspace en 2015, las funcionalidades y capacidades de [!DNL Reports & Analytics] se han trasladado a Analysis Workspace y se ha alcanzado un umbral de paridad de flujo de trabajo. [Este aviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) explica el proceso de finalización de la vida útil. |

{style=&quot;table-layout:auto&quot;}

### AppMeasurement

Para obtener las últimas actualizaciones de las versiones de AppMeasurement (2.22.4), consulte las [notas de la versión de AppMeasurement para JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=es).


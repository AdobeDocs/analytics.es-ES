---
title: Últimas notas de la versión de Analytics
description: Ver las notas de la versión actuales de Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 945a495dfea2f4564d39457528a185b6b75c7d17
workflow-type: tm+mt
source-wordcount: '839'
ht-degree: 76%

---

# Notas de la versión actuales de Adobe Analytics (febrero de 2022)

**Última actualización**: 3 de marzo de 2022

Obtenga información sobre las últimas actualizaciones de la versión para [productos de Adobe Experience Cloud](https://business.adobe.com/es/products/adobe-experience-cloud-products.html). Obtenga la documentación de autoayuda más reciente, tutoriales y cursos sobre Experience League.

## Funciones nuevas en Adobe Analytics {#aa-features}

| Función | Descripción | [Fecha objetivo](releases.md) |
| ----------- | ---------- | ------- |
| Modo de vista previa del proyecto del cuadro de resultados móvil | Inicie una vista previa del aspecto que tendrá su cuadro de resultados móvil en la aplicación de paneles de Analytics, directamente desde el generador de cuadros de resultados. El modo de vista previa permite que los usuarios interactúen con filtros y gráficos del mismo modo que lo harían en la aplicación, lo que les permite obtener una vista previa de la experiencia antes de guardar y compartir el cuadro de resultados. Los usuarios también pueden utilizar el selector de dispositivos en el modo de vista previa para ver el aspecto que tendrá su cuadro de resultados en distintos dispositivos. [Más información](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/create-scorecard.html?lang=es#preview) | 16 de febrero de 2022 |
| Punto de conexión de proyectos de API | Añada, edite o elimine proyectos de Analysis Workspace mediante la API . [Más información](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/projects/) | 1 de febrero de 2022 |

{style=&quot;table-layout:auto&quot;}

## Correcciones en Adobe Analytics

* Se han corregido varios problemas con el [!UICONTROL Uso de llamadas al servidor]. (AN-279134, AN-279878, AN-280802, AN-279097, AN-191284, AN-269720)
* Se ha corregido un problema que hacía que Data Warehouse exportara archivos .csv vacíos. (AN-280291)
* Se ha corregido un problema que provocaba que los nombres de audiencia no se rellenaran para segmentos recientes. (AN-279715)
* Se ha corregido un problema con los tiempos de creación de informes lentos. (AN-280055)
* Se han corregido problemas con Clasificaciones por los que no clasificaban todos los elementos de dimensión. (AN-280031)

### Correcciones adicionales en Adobe Analytics

AN-268093, AN-273820, AN-274435, AN-274904, AN-275356, AN-275947, AN-276160, AN-276258, AN-276705, AN-277051, AN-277957, AN-278693, AN-278882, AN-279000, AN-279046, AN-279362, AN-279460, AN-279488, AN-279554, AN-279572, AN-279663, AN-279755, AN-279825, AN-280002, AN-280013, AN-280019, AN-280033, AN-280086, AN-280232, AN-280264, AN-280288, AN-280342, AN-280347, AN-280360, AN-280370, AN-280724, AN-280830, AN-280941, AN-281353, AN-281424, AN-281533

## Avisos importantes para los administradores de [!DNL Analytics]

**Actualizado el 3 de marzo de 2022**

| Aviso | Fecha de incorporación o actualizada | Descripción |
| ----------- | ---------- | ---------- |
| Cambio del modo en que Analytics gestiona los datos de A4T recopilados mediante Experience Edge | 25 de febrero de 2022 | Activado **7 de marzo de 2022**, cambiaremos la forma en que administramos algunos datos relacionados con Target enviados a Adobe Analytics a través de Experience Edge. Al utilizar el SDK web de Adobe Experience Platform con Analytics y Target, se contabilizaban algunos eventos de personalización en [!DNL Adobe Analytics] como [!UICONTROL Vistas de páginas]. Esto condujo a recuentos de vistas de página inflados y llamadas al servidor adicionales. Con el cambio, se ignorarán las llamadas de personalización sin contenido de Analytics. Las llamadas de personalización con datos de A4T registrarán los datos de A4T, pero no se registrarán como llamadas al servidor facturables, ni afectarán a las vistas de página ni a las métricas de eventos de vínculo. |
| Pausa de tareas de Report Builder programadas más antiguas | 24 de febrero de 2022 | **En vigor a partir del 15 de abril de 2022**, Adobe tiene la intención de poner en pausa todas las tareas de Report Builder programadas que se crearon hace más de dos años. En concreto, esta pausa se aplica a cualquier tarea creada antes del 31 de enero de 2020. No se eliminarán tareas, libros ni datos. Sin embargo, las tareas identificadas como anteriores a dos años se pausarán y no se enviarán tareas programadas adicionales. [Más información](/help/analyze/report-builder/r-arb-scheduled-reports.md) |
| Caducidad de la extensión EOL de la lista de permitidos para integraciones heredadas de Analytics OAuth/JWT | 14 de enero de 2022 | El **25 de mayo de 2022**, la extensión de lista de permitidos de [API de Analytics 1.3, API de SOAP 1.4 y EOL de OAuth/JWT de Analytics heredado](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/APIEOL.md) caducará. Se ofreció para proporcionar a los clientes que usan las credenciales de OAuth/JWT de [!DNL Adobe Analytics] más tiempo para migrar sus integraciones de cliente a las [credenciales de IMS de Adobe](https://developer.adobe.com/console). Esta caducidad afecta a clientes [!DNL Adobe Analytics Livestream] y [!DNL Adobe Campaign] (entre otros) que no hayan completado las migraciones de IMS requeridas. Clientes que actualmente utilizan las credenciales de la versión heredada [!DNL Analytics] OAuth/JWT a través de la extensión de la lista de permitidos y que no hayan completado su migración a las credenciales de IMS antes del 25 de mayo de 2022 perderán acceso a los servicios de Adobe. Los clientes de Livestream pueden consultar estas [instrucciones](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) al migrar sus aplicaciones cliente a credenciales de IMS. [!DNL Campaign] clientes pueden ponerse en contacto con el equipo de su cuenta de Adobe para actualizar a la última versión de [!DNL Campaign]. |
| EOL para [!DNL Reports & Analytics] | 4 de enero de 2022 | A partir del **31 de diciembre de 2023**, Adobe tiene la intención de descatalogar [!DNL Reports & Analytics] y sus informes y funciones correspondientes. Los informes, las visualizaciones y la tecnología subyacente que alimentan [!DNL Reports & Analytics] ya no cumplen los estándares tecnológicos de Adobe. La mayoría de las funciones de [!DNL Reports & Analytics] están disponibles en [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=es). Desde el lanzamiento de Analysis Workspace en 2015, las funcionalidades y capacidades de [!DNL Reports & Analytics] se han trasladado a Analysis Workspace y se ha alcanzado un umbral de paridad de flujo de trabajo. [Este aviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) explica el proceso de finalización de la vida útil. |
| Actualización de servicios del Protocolo seguro de transferencia de archivos (SFTP) | 3 de marzo de 2022 | El **15 de mayo de 2022**, [!DNL Adobe Analytics] actualizará sus servicios de Protocolo seguro de transferencia de archivos (SFTP) para proporcionar una seguridad mejorada para las transferencias de archivos. Con este cambio, algunas configuraciones de cliente SFTP ya no serán compatibles. También añadiremos algunas opciones de conexión que estarán disponibles el **1 de marzo de 2022**. Esto solo afecta a los datos enviados o recuperados de Adobe Analytics mediante SFTP. El protocolo FTP no se ve afectado. Para evitar interrupciones en el servicio, asegúrese de que sus clientes SFTP (código, herramientas y servicios) estén de acuerdo con los cambios detallados [aquí](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=es). |

## AppMeasurement {#appm}

Para obtener las últimas actualizaciones de las versiones de AppMeasurement (2.22.4), consulte las [notas de la versión de AppMeasurement para JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=es).

>[!MORELIKETHIS]
>[[!DNL Customer Journey Analytics] Notas de la versión](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=es)

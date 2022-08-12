---
title: Últimas notas de la versión de Analytics
description: Vea las notas de la versión actuales de Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 7c6ef22322a67e671ac32d2b7be4a182bb3a2df7
workflow-type: tm+mt
source-wordcount: '1011'
ht-degree: 83%

---

# Notas de la versión actual de Adobe Analytics (agosto de 2022)

**Última actualización**: 12 de agosto de 2022

## Recursos relacionados

* [Notas de la versión anteriores de 2022](/help/release-notes/2022.md)
* [Notas de la versión de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=es)
* [Notas de la versión de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
* Las últimas actualizaciones de la versión para los [productos de Adobe Experience Cloud](https://business.adobe.com/es/products/adobe-experience-cloud-products.html)

## Funciones nuevas o actualizadas en Adobe Analytics

| Función | Descripción | [Fecha objetivo](releases.md) |
| ----------- | ---------- | ------- |
| No hay nuevas funciones este mes |  |  |

{style=&quot;table-layout:auto&quot;}

## Correcciones en Adobe Analytics

* Se han corregido varios problemas relacionados con las fuentes de datos. (AN-297264, AN-297295 y AN-297449)

**Correcciones para clientes individuales**:

AN-280956; AN-285670; AN-288176; AN-289221; AN-289665; AN-289768; AN-294632; AN-294970; AN-295078; AN-295233; AN-295482; AN-295549; AN-295633; AN-295712; AN-295749; AN-295963; AN-295977; AN-296094; AN-296153; AN-296167; AN-296177; AN-296297; AN-296383; AN-296394; AN-296414; AN-296431; AN-296459; AN-296486; AN-296510; AN-296514; AN-296540; AN-296734; AN-296840; AN-296841; AN-296977; AN-296987; AN-297002; AN-297141; AN-297267; AN-297396;

## Avisos importantes para los administradores de Adobe Analytics

| Aviso | Fecha de incorporación o actualizada | Descripción |
| ----------- | ---------- | ---------- |
| **Actualización de SFTP** | 12 de agosto de 2022 | Anteriormente, habíamos comunicado que Adobe actualizaría sus servicios de Protocolo seguro de transferencia de archivos (SFTP) en mayo de 2022 para proporcionar una seguridad mejorada para la transferencia de archivos. Hemos pospuesto esta actualización a **7 de septiembre de 2022**. Cuando se realice este cambio, ya no se admitirán determinadas configuraciones del cliente SFTP. Esto solo afecta a los datos enviados o recuperados de Adobe Analytics mediante SFTP. El protocolo FTP no se ve afectado. Para evitar interrupciones en el servicio, asegúrese de que sus clientes SFTP (código, herramientas y servicios) estén de acuerdo con los cambios detallados [aquí](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=es). |
| **Actualización de la nueva base de datos de portadores de NetAcuity** | 11 de julio de 2022 | **A partir de octubre de 2022**, información relacionada con el operador de telefonía almacenada en la variable `carrier` en Data Warehouse de Adobe Analytics y las fuentes de datos de Analytics cambiarán. Históricamente, el formato de datos de esa columna se ha `<domain>:<ISP>`. Adobe ha mantenido una tabla de búsqueda interna para asignarlas `<domain>:<ISP>` en nombres de operadores para la creación de informes en herramientas de informes de Adobe Analytics (Analysis Workspace, Reports &amp; Analytics, API de informes, Data Warehouse, LiveStream, etc.). El archivo de búsqueda (`carrier.tsv`) también se proporciona con Fuentes de datos para que pueda usar las mismas asignaciones.<p>Esta actualización del estado mejora nuestras asignaciones de operadores mediante el uso de una base de datos de operadores más precisa de NetAcuity. El formato de los datos de la columna de portador de las fuentes de datos cambiará en adelante. En lugar de `<domain>:<ISP>`, contendrá un nombre de operador. Adobe seguirá utilizando la tabla de búsqueda para mantener la mayor continuidad posible con los informes anteriores. Herramientas de creación de informes donde Adobe aplica las búsquedas (Analysis Workspace, Reports &amp; Analytics, API de informes, Data Warehouse, LiveStream, etc.) se beneficiarán de asignaciones más precisas. Algunas asignaciones, especialmente para dominios internacionales e ISP, cambiarán más que otras cuando adoptemos la nueva base de datos. El archivo de búsqueda del operador de telefonía de fuentes de datos (`carrier.tsv`) mantendrá las asignaciones antiguas y agregará las nuevas asignaciones.<p>El conector de origen de Analytics no asigna actualmente el campo de operador, por lo que los informes de operador no están disponibles actualmente en AEP, CJA, etc. Por lo tanto, el uso de la nueva base de datos de operadores no afectará a nada en AEP que se base en los datos proporcionados por el Conector de origen de Analytics. |
| **Asignación de IP a geolocalización mejorada** | 11 de julio de 2022 | Nuestro proveedor de búsquedas de IP, Digital Element, está actualizando a un nuevo conjunto de datos mejorado (NetAcuity Pulse) para la asignación de IP a geolocalización. Adobe Analytics adoptará este nuevo conjunto de datos en el periodo de tiempo de **octubre de 2022**. La nueva base de datos será más precisa que las versiones anteriores. Algunas asignaciones de IP a regiones cambiarán o mejorarán cuando se adopte la nueva base de datos.<p>Todas las herramientas de Adobe Analytics (Analysis Workspace, Reports &amp; Analytics, API de informes, Data Warehouse, LiveStream, fuentes de datos, etc.) aprovechará automáticamente las nuevas asignaciones mejoradas. No habrá cambios en el formato de los datos en las fuentes de datos. Los datos de CJA proporcionados a través del conector de origen de Analytics también aprovecharán automáticamente las nuevas asignaciones. |
| **Pausa de informes programados en Reports &amp; Analytics** | 8 de junio de 2022 | El 21 de abril de 2022, anunciamos la desaprobación de varias funciones específicas de los informes programados como preparación para el fin de vida útil anunciado anteriormente para Reports &amp; Analytics. Estas funciones incluían la capacidad de programar nuevos informes, así como nuevos extractos de datos.<p>En respuesta a las solicitudes de los clientes que buscan una extensión y para facilitar la transición desde Reports and Analytics, hemos decidido ampliar el acceso a estas funciones hasta **31 de enero de 2023**. Tenga en cuenta que los plazos de caducidad para los informes y los extractos de datos seguirán estando limitados a nueve meses; la entrega de informes y extracciones de datos se pausará al final de este periodo a menos que se reactive la programación.<p>Para reiterar, estas funciones quedarán obsoletas el 31 de enero de 2023. Antes de esta fecha, debe migrar los informes programados a uno de los demás mecanismos disponibles en Adobe Analytics. Para obtener más información o ayuda, póngase en contacto con el Servicio de atención al cliente de Adobe. [Más información](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| **Pausa de tareas programadas en el Report Builder** | 8 de junio de 2022 | El 21 de abril de 2022, implementamos cambios en las tareas programadas en Report Builder como parte de nuestros esfuerzos de optimización de rendimiento y entrega. Estos cambios incluían la eliminación de la capacidad de que los envíos programados “terminen después de x incidencias”. En respuesta a varias solicitudes de clientes que buscan más tiempo para explorar e implementar alternativas, hemos decidido restaurar esta opción de forma limitada hasta el **31 de enero de 2023**.<p>Puede continuar programando tareas de Report Builder por hora y hacer que finalicen después de un máximo de 99 incidencias. Tenga en cuenta que la reversión solo se aplica a tareas por hora; el evento “terminen después de x incidencias” permanecerá no disponible para todos los demás intervalos de entrega (diario, semanal, mensual y anual). Tenga en cuenta que esta opción quedará obsoleta el 31 de enero de 2023. Para obtener más información o ayuda, póngase en contacto con el Servicio de atención al cliente de Adobe. [Más información](/help/analyze/report-builder/r-arb-scheduled-reports.md) |
| **EOL para [!DNL Reports & Analytics]** | 4 de enero de 2022 | A partir del **31 de diciembre de 2023**, Adobe tiene la intención de descatalogar [!DNL Reports & Analytics] y sus informes y funciones correspondientes. Los informes, las visualizaciones y la tecnología subyacente que alimentan [!DNL Reports & Analytics] ya no cumplen los estándares tecnológicos de Adobe. La mayoría de las funciones de [!DNL Reports & Analytics] están disponibles en [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=es). Desde el lanzamiento de Analysis Workspace en 2015, las funcionalidades y capacidades de [!DNL Reports & Analytics] se han trasladado a Analysis Workspace y se ha alcanzado un umbral de paridad de flujo de trabajo. [Este aviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) explica el proceso de finalización de la vida útil. |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement

Para obtener las últimas actualizaciones de las versiones de AppMeasurement (2.22.4), consulte las [notas de la versión de AppMeasurement para JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=es).


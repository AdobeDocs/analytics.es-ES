---
title: Últimas notas de la versión de Analytics
description: Vea las notas de la versión actuales de Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: cf291c4d46a6bff9e1c61804ca7e897ee1d4e4d5
workflow-type: tm+mt
source-wordcount: '984'
ht-degree: 49%

---

# Notas de la versión actual de Adobe Analytics (junio de 2022)

>[!NOTE]
>
>Esta página contiene información previa al lanzamiento y está sujeta a cambios.

**Última actualización**: 10 de junio de 2022

## Recursos relacionados

* [Notas de la versión anteriores de 2022](/help/release-notes/2022.md)
* [Notas de la versión de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=es)
* [Notas de la versión de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
* Las últimas actualizaciones de la versión para los [productos de Adobe Experience Cloud](https://business.adobe.com/es/products/adobe-experience-cloud-products.html)

## Funciones nuevas en Adobe Analytics

| Función | Descripción | [Fecha objetivo](releases.md) |
| ----------- | ---------- | ------- |
| Nueva interfaz de usuario de visualización de flujo | Proporciona funcionalidad adicional a nuestra visualización de flujo para hacerla más potente y capaz. [Más información](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/flow/create-flow.html?lang=en) | 15 de junio de 2022 |
| Compartir anotaciones en informes de valoración de Mobile | Puede mostrar anotaciones creadas en Workspace en informes de valoración móviles. Esto le permite compartir matices de datos contextuales y perspectivas sobre su organización y campañas directamente dentro de proyectos de informes de valoración móviles, visibles en la aplicación móvil de paneles de Analytics . Más información (a continuación) | 15 de junio de 2022 |
| Compatibilidad con la versión de sintaxis del producto de Variables de comercialización con la colección Edge | Ahora puede establecer variables de comercialización utilizando el equivalente de la sintaxis del producto estableciendo los campos XDM relevantes. Obtenga más información sobre la sintaxis del producto para las variables de comercialización [here](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/merchandising-evars.html?lang=es). Consulte las asignaciones para la sintaxis del producto [here](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=en#aep-edge). | 15 de junio de 2022 |
| Rellenado de dimensiones y métricas de Ciclo vital mediante Experience Edge | Los datos del Ciclo de vida móvil enviados mediante Experience Edge ahora aparecerán en los informes de Analytics. Consulte la documentación para obtener detalles sobre qué campos XDM se asignan a los informes de ciclo de vida móviles existentes. [Más información](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) | 27 de mayo de 2022 |
| Nueva experiencia de clasificaciones: Fase 1 | Esta versión por fases de la nueva experiencia del usuario del conjunto de clasificaciones mejora significativamente la visibilidad de los datos de clasificación de propiedad del cliente. Se estima que la Asamblea General se celebrará a principios de 2023. | Las pruebas limitadas comienzan el 15 de junio de 2022 |

{style=&quot;table-layout:auto&quot;}

### Correcciones en Adobe Analytics

AN-251686; AN-283542; AN-286572; AN-286945; AN-286784; AN-286944; AN-287012; AN-287319; AN-287333; AN-287348; AN-287429; AN-288238; AN-288281; AN-288660; AN-288769; AN-288798; AN-288871; AN-288872; AN-288941; AN-288951; AN-288952; AN-288956; AN-289062; AN-289340; AN-289346; AN-289488; AN-289562; AN-289580; AN-289861; AN-289892;

### Avisos importantes para los administradores de Adobe Analytics

| Aviso | Fecha de incorporación o actualizada | Descripción |
| ----------- | ---------- | ---------- |
| **Pausa de informes programados en Reports &amp; Analytics** | 8 de junio de 2022 | El 21 de abril de 2022, anunciamos la desaprobación de varias funciones específicas de los informes programados como preparación para el fin de vida útil anunciado anteriormente para Reports &amp; Analytics. Estas funciones incluían la capacidad de programar nuevos informes, así como nuevos extractos de datos.<p>En respuesta a las solicitudes de los clientes que buscan una extensión y para facilitar la transición desde Reports and Analytics, hemos decidido ampliar el acceso a estas funciones hasta **31 de enero de 2023**. Tenga en cuenta que los plazos de caducidad para los informes y los extractos de datos seguirán estando limitados a nueve meses; la entrega de informes y extracciones de datos se pausará al final de este periodo a menos que se reactive la programación.<p>Para reiterar, estas funciones quedarán obsoletas el 31 de enero de 2023. Antes de esta fecha, debe migrar los informes programados a uno de los demás mecanismos disponibles en Adobe Analytics. Para obtener más información o ayuda, póngase en contacto con el Servicio de atención al cliente de Adobe. [Más información](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| **Pausa de tareas programadas en el Report Builder** | 8 de junio de 2022 | El 21 de abril de 2022, implementamos cambios en las tareas programadas en Report Builder como parte de nuestros esfuerzos de optimización de rendimiento y envío. Estos cambios incluían la eliminación de la capacidad de que los envíos programados &quot;terminen después de x ocurrencias&quot;. En respuesta a varias solicitudes de clientes que buscan más tiempo para explorar e implementar alternativas, hemos decidido restaurar esta opción de forma limitada hasta **31 de enero de 2023**.<p>Puede continuar programando tareas de Report Builder por hora y hacer que finalicen después de un máximo de 99 incidencias. Tenga en cuenta que la reversión solo se aplica a tareas por hora; el evento &quot;end after x occurrences&quot; permanecerá no disponible para todos los demás intervalos de entrega (diario, semanal, mensual y anual). Tenga en cuenta que esta opción quedará obsoleta el 31 de enero de 2023. Para obtener más preguntas o asistencia, póngase en contacto con el Servicio de atención al cliente de Adobe. [Más información](/help/analyze/report-builder/r-arb-scheduled-reports.md) |
| **Actualización de SFTP** | 9 de mayo de 2022 | Anteriormente, habíamos comunicado que Adobe actualizaría sus servicios de Protocolo seguro de transferencia de archivos (SFTP) en mayo de 2022 para proporcionar una seguridad mejorada para la transferencia de archivos. Hemos pospuesto esta actualización a **verano de 2022**. Cuando se realice este cambio, ya no se admitirán determinadas configuraciones del cliente SFTP. Esto solo afecta a los datos enviados o recuperados de Adobe Analytics mediante SFTP. El protocolo FTP no se ve afectado. Para evitar interrupciones en el servicio, asegúrese de que sus clientes SFTP (código, herramientas y servicios) estén de acuerdo con los cambios detallados [aquí](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=es). |
| **Actualización de los métodos de cifrado del explorador admitidos para determinados clientes** | 28 de marzo de 2022 | Adobe ofrece dos niveles de seguridad de cifrado para satisfacer las distintas necesidades de seguridad de los clientes en la recopilación de datos de origen. El **23 de junio de 2022** se eliminará la compatibilidad con ciertos algoritmos de codificación HTTPS, conocidos como cifrados, para clientes con su nivel de seguridad establecido en Alto. Esta acción significa que algunos sistemas operativos antiguos ya no podrán enviar datos a Analytics porque no son compatibles con los métodos de cifrado modernos. Los clientes que utilicen la configuración predeterminada de seguridad de cifrado Estándar no se ven afectados. Ya se ha contactado directamente con todos los clientes que actualmente usan la configuración “Alta”. Una lista detallada de las cifras afectadas por esta |
| **Actualizaciones de región ISO 2022** | 11 de marzo de 2021 | Adobe realizó actualizaciones de la región ISO 2022 en **10 de junio de 2022**. Es de esperar que se produzcan pequeñas actualizaciones de la información geográfica tras este lanzamiento. |
| **EOL para [!DNL Reports & Analytics]** | 4 de enero de 2022 | A partir del **31 de diciembre de 2023**, Adobe tiene la intención de descatalogar [!DNL Reports & Analytics] y sus informes y funciones correspondientes. Los informes, las visualizaciones y la tecnología subyacente que alimentan [!DNL Reports & Analytics] ya no cumplen los estándares tecnológicos de Adobe. La mayoría de las funciones de [!DNL Reports & Analytics] están disponibles en [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=es). Desde el lanzamiento de Analysis Workspace en 2015, las funcionalidades y capacidades de [!DNL Reports & Analytics] se han trasladado a Analysis Workspace y se ha alcanzado un umbral de paridad de flujo de trabajo. [Este aviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) explica el proceso de finalización de la vida útil. |

{style=&quot;table-layout:auto&quot;}

### AppMeasurement

Para obtener las últimas actualizaciones de las versiones de AppMeasurement (2.22.4), consulte las [notas de la versión de AppMeasurement para JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=es).


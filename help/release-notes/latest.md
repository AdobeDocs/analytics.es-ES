---
title: Notas de la versión de Adobe Analytics actual
description: Ver las notas de la versión actuales de Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 084a9e9d2794ece4ddbb4296eee107bbdb451813
workflow-type: tm+mt
source-wordcount: '1216'
ht-degree: 58%

---

# Notas de la versión actuales de Adobe Analytics (octubre de 2023)

**Última actualización**: 4 de octubre de 2023

Las notas de la versión de octubre abarcan el período de lanzamiento del 4 de octubre de 2023 al 24 de octubre de 2023. Las versiones de Adobe Analytics funcionan con un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funcionalidades. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Nuevas funciones o mejoras {#features}

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Nuevas columnas disponibles al administrar componentes** | Las siguientes columnas nuevas ya están disponibles al administrar componentes:<ul><li>Utilizado en<p>Esta columna está disponible en la variable [Administrador de métricas calculadas](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md) y el [Administrador de segmentos](/help/components/segmentation/segmentation-workflow/seg-manage.md).</p></li><li>Último uso<p>Esta columna está disponible en la variable [Administrador de métricas calculadas](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md), el [Administrador de segmentos](/help/components/segmentation/segmentation-workflow/seg-manage.md), y el [Administrador de alertas](/help/components/c-alerts/alert-manager.md).</p></li></ul><p>Esta información puede ayudarle a determinar si un componente es valioso para los usuarios de su organización, dónde se utiliza y si debe eliminarse o modificarse. Puede utilizar el diccionario de datos junto con esta información para ayudarle a realizar un seguimiento y comprender mejor cómo se utilizan los componentes en su organización.</p> | 20 de septiembre de 2023 | 4 de octubre de 2023 |
| **Mejoras del Administrador de actividades de creación de informes** | El Administrador de actividades de creación de informes le permite ver la capacidad de creación de informes de cada grupo de informes de su organización.  Proporciona a los administradores una visibilidad detallada del consumo de creación de informes para diagnosticar y corregir fácilmente los problemas de capacidad durante las horas de mayor actividad de la creación de informes. A continuación se indican algunas de las mejoras que ahora están disponibles en el Administrador de actividades de creación de informes: <ul><li>Restringir solicitudes posteriores: además de cancelar las solicitudes actuales, los administradores ahora pueden restringir las solicitudes durante un período de tiempo definido. Los administradores pueden restringir las solicitudes por solicitud, proyecto y usuario.</li><li>Además de las métricas de Utilización y Capacidad, el Administrador de actividades de creación de informes ahora incluye más datos sobre la actividad de creación de informes: columna Complejidad, columna Usuario y columna Conexión.</li><li>Todas las cancelaciones y restricciones realizadas en el administrador de actividades de creación de informes ahora están visibles en el registro de auditoría. Los administradores pueden utilizar el registro de auditoría para ver lo que se ha cancelado actualmente. Las cancelaciones no se pueden revertir en el Administrador de actividades de creación de informes ni en el Registro de auditoría.</li></ul>Más información (próximamente) | 17 de octubre de 2023 | 23 de octubre de 2023 |
| **Mejoras del Data Warehouse** | Al crear una solicitud de Data Warehouse, ahora puede configurar una cuenta de la nube para usarla como destino del informe. Los siguientes tipos de cuenta de nube están disponibles para enviar datos:<ul><li>Amazon S3</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li><li>Correo electrónico (esta opción estaba disponible anteriormente)</li></ul>FTP, SFTP, Azure Blob y S3 siguen estando disponibles como destinos de informe, pero ya no se recomiendan.<p>También se ha mejorado la experiencia del usuario al crear y administrar solicitudes de Data Warehouse. Para obtener más información, consulte [Creación de una solicitud de Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md) y [Administrar solicitudes de Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-requests-manage.html?lang=es). | 12 de septiembre de 2023 | 25 de octubre de 2023 |
| **Migrar proyectos de Adobe Analytics y cualquier componente incluido a Customer Journey Analytics** | Ahora puede migrar sus proyectos de Adobe Analytics a Customer Journey Analytics. Este proceso simplifica la transición de Adobe Analytics a Customer Journey Analytics. Al migrar proyectos a Customer Journey Analytics, los recursos se asignan de un grupo de informes de Adobe Analytics a una vista de datos de Customer Journey Analytics. [Más información](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration.html) | N/A | 4 de octubre de 2023 |

{style="table-layout:auto"}

## Correcciones en Adobe Analytics

* Se han corregido problemas en los que los informes de A4T no aparecían en la interfaz de usuario de Target/Analytics. (AN-329375, AN-329745, AN-330026)

AN-313983; AN-324189; AN-325095; AN-325677; AN-325886; AN-326068; AN-326360; AN-326458; AN-327290 AN-327315 AN-AN-327505 AN-AN; AN-AN-AN; AN-AN; AN-AN; AN-AN;-AN; Y-AN-AN; Y-AN-327589; AN-AN; Y-AN-AN; Y-AN-AN; Y-AN-AN-AN; Y-AN-AN-AN; Y-AN-AN; Y-327353; AN-; AN-; AN-327609; AN-327922; AN-328110; AN-328222; AN-AN; AN-AN-AN; AN-AN-AN; AN-AN-AN; AN-AN-AN; AN-AN-AN; AN-AN-AN; AN-AN; AN-AN; AN-AN; AN-AN; AN-AN; AN-AN; AN-AN; AN-AN; AN-AN; AN-AN; AN-AN; AN-AN; AN-AN; AN-328261;-AN;-AN;-328496;-AN;-AN-328577; AN-; AN-328629; AN-328736; AN-328888; AN-328899; AN-328902; AN-328921; AN-328958; AN-329208; AN-329277; AN-329332; AN-329334; AN-329335; AN-329336; AN-329357; AN-329385; AN-329387; AN-329397; AN-329463; AN-329501; AN-329504 329505 329515 329524 329526 329534 329539 329541 329543 329545 329564 329570 329623 329624 329636 329646 329647 329668 329701 329737 329741 329751 329812 329813 329821 329824 329833 329848 329852 329861 329863 329874 329882 329911 329917 329942 329954 329968 329971 329982 330044 330052 330131 330132 330230 330352 330367 330541 330599

## Avisos importantes para los administradores de Adobe Analytics {#admin}

| Aviso | Fecha de incorporación o actualizada | Descripción |
| ----------- | ---------- | ---------- |
| **Confusión de IP completa para visitas de Adobe Experience Edge** | 27 de septiembre de 2023 | La confusión de IP para las visitas procedentes de Experience Edge se actualizará más adelante en octubre de 2023. En abril, Experience Edge agregó la capacidad de proteger las direcciones IP. En ese momento, Adobe Analytics solo admitía la ofuscación parcial de direcciones IP, debido a la forma en que Analytics procesa las visitas de Experience Edge. Cuando los clientes eligieron la ofuscación completa para Experience Edge, Analytics solo recibía direcciones IP parcialmente ofuscadas. Cuando se implemente este cambio, Analytics recibirá la IP totalmente oculta. |
| **Adobe Analytics Livestream: API de Analytics 2.0** | 27 de septiembre de 2023 | Los clientes ahora pueden acceder a [Guía de extremo de Adobe Analytics Livestream](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/) en las API de Adobe Analytics 2.0 en lugar de en su ubicación anterior, con las API 1.4. Tenga en cuenta que los clientes que utilizan credenciales de JWT de Adobe I/O deben migrar a las credenciales de servidor a servidor de OAuth de Adobe I/O antes del 1 de enero de 2025. (Consulte los detalles en los avisos de fin de vida más abajo). |

{style="table-layout:auto"}

## Avisos de final de la vida útil {#eol}

| Final de la vida útil de producto o función | Fecha de incorporación o actualización | Descripción |
| --- | --- | --- |
| **Migración a las credenciales de servidor a servidor de Adobe I/O OAuth** | 11 de mayo de 2023 | Los clientes de la API de Adobe Analytics y Livestream que utilizan las credenciales de JWT de Adobe I/O deben migrar a las credenciales de servidor a servidor de Adobe I/O OAuth de forma predeterminada el **1 de enero de 2025**. Adobe I/O no permitirá que se creen nuevas credenciales de JWT a partir del 1 de mayo de 2024. Los clientes que utilizan JWT deben crear una nueva credencial de servidor a servidor OAuth o migrar su credencial JWT existente a una credencial de servidor a servidor OAuth. Los clientes también deben actualizar sus aplicaciones cliente para utilizar las nuevas credenciales de servidor a servidor de OAuth. <ul><li>[Migración de credenciales de cuenta de servicio (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guía de implementación para aplicaciones nuevas y antiguas con OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Uso de las nuevas credenciales de servidor a servidor de OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Preguntas frecuentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **EOL para [!DNL Reports & Analytics]** | 7 de marzo de 2023 | A partir del **31 de diciembre de 2023**, Adobe tiene la intención de descatalogar [!DNL Reports & Analytics] y sus informes y funciones correspondientes. Los informes, las visualizaciones y la tecnología subyacente que alimentan [!DNL Reports & Analytics] ya no cumplen los estándares tecnológicos de Adobe. La mayoría de las funciones de [!DNL Reports & Analytics] están disponibles en [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=es). Desde el lanzamiento de Analysis Workspace en 2015, las funcionalidades y capacidades de [!DNL Reports & Analytics] se han trasladado a Analysis Workspace y se ha alcanzado un umbral de paridad de flujo de trabajo. [Este aviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) explica el proceso de finalización de la vida útil.<p>El 31 de diciembre de 2023, finalizaremos muchas de las funciones de Reports &amp; Analytics asociadas, incluidas, entre otras, las siguientes: Informes programados, Extractos de datos e Informes DL. A partir del 31 de diciembre de 2023, ya no se enviarán los informes programados. En **abril de 2023**, cualquier informe que estuviera programado para caducar después del 31 de diciembre de 2023 se actualizará automáticamente y se revertirá para que caduque el 31 de diciembre de 2023. Además, ya no puede programar informes futuros después del 31 de diciembre de 2023. |
| **Funcionalidad del final de vida útil de las [!UICONTROL Listas de publicación]** | 29 de septiembre de 2022 | Como parte del final de la vida útil de Reports &amp; Analytics, las [!UICONTROL Listas de publicación] están programadas para llegar al final de su vida útil en **diciembre de 2023**. No podrá crear [!UICONTROL Listas de publicación] nuevas ni acceder a las existentes para enviar o programar proyectos de [!UICONTROL Analysis Workspace]. |
| **Fin de la vida útil para Data Workbench** | 14 de septiembre de 2022 | Adobe tiene planeado el fin de la vida útil de Data Workbench con fecha de aplicación el **31 de diciembre de 2023**. Consulte [Anuncio del fin de la vida útil de Data Workbench](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=es) para obtener más información. Póngase en contacto con el Administrador de cuentas de Adobe de su organización si tiene alguna pregunta. |

{style="table-layout:auto"}

## AppMeasurement

Para obtener las últimas actualizaciones de las versiones de AppMeasurement (2.25.0), consulte las [notas de la versión de AppMeasurement para JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=es).


## Recursos relacionados

* [Notas de la versión anteriores de 2022](/help/release-notes/2022.md)
* [Notas de la versión de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=es)
* [Notas de la versión de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
* Las últimas actualizaciones de la versión para los [productos de Adobe Experience Cloud](https://business.adobe.com/es/products/adobe-experience-cloud-products.html)

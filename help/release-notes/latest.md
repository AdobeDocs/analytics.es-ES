---
title: Notas de la versión de Adobe Analytics actual
description: Ver las notas de la versión actuales de Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 84f6bf068f56b9502a53ab17e71dca00356804d9
workflow-type: tm+mt
source-wordcount: '1134'
ht-degree: 66%

---

# Notas de la versión actuales de Adobe Analytics (octubre/noviembre de 2023)

**Última actualización**: 25 de octubre de 2023

Estas notas de la versión abarcan el periodo de lanzamiento del 23 de octubre de 2023 a finales de noviembre de 2023. Las versiones de Adobe Analytics funcionan con un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funcionalidades. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Nuevas funciones o mejoras {#features}

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Mejoras del Administrador de actividades de creación de informes** | El Administrador de actividades de creación de informes le permite ver la capacidad de creación de informes de cada grupo de informes de su organización.  Proporciona a los administradores una visibilidad detallada del consumo de creación de informes para diagnosticar y corregir fácilmente los problemas de capacidad durante las horas de mayor actividad de creación de informes. A continuación se indican algunas de las mejoras que ahora están disponibles en el Administrador de actividades de creación de informes: <ul><li>Restringir solicitudes posteriores: además de cancelar las solicitudes actuales, los administradores ahora pueden restringir las solicitudes durante un período de tiempo definido. Los administradores pueden restringir las solicitudes por solicitud, proyecto y usuario.</li><li>Además de las métricas de Utilización y Capacidad, el Administrador de actividades de creación de informes ahora incluye más datos sobre la actividad de creación de informes: columna Complejidad, columna Usuario y columna Conexión.</li><li>Todas las cancelaciones y restricciones realizadas en el administrador de actividades de creación de informes ahora están visibles en el registro de auditoría. Los administradores pueden utilizar el registro de auditoría para ver lo que se ha cancelado actualmente. Las cancelaciones no se pueden revertir en el Administrador de actividades de creación de informes ni en el Registro de auditoría.</li></ul><p>Para obtener más información, consulte [Información general del Administrador de actividades de creación de informes](/help/admin/admin/reporting-activity-manager/reporting-activity-overview.md)</p> | 17 de octubre de 2023 | 24 de octubre de 2023 |
| **Mejoras del Data Warehouse** | Al crear una solicitud de Data Warehouse, ahora puede configurar una cuenta de la nube para usarla como destino del informe. Los siguientes tipos de cuenta de nube están disponibles para enviar datos:<ul><li>Amazon S3</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li><li>Correo electrónico (esta opción estaba disponible anteriormente)</li></ul>FTP, SFTP, Azure Blob y S3 siguen estando disponibles como destinos de informe, pero ya no se recomiendan.<p>También se ha mejorado la experiencia del usuario al crear y administrar solicitudes de Data Warehouse. Para obtener más información, consulte [Creación de una solicitud de Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md) y [Administrar solicitudes de Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-requests-manage.html?lang=es). | 12 de septiembre de 2023 | El 8 de noviembre de 2023 o antes |

{style="table-layout:auto"}

## Correcciones en Adobe Analytics

* Estos cambios del motor de procesamiento y creación de informes de Analytics se implementarán durante la última semana de octubre: se solucionará un problema por el que las etiquetas de las dimensiones Página o Vínculo se mostraban incorrectamente como `Unknown`. Antes de la corrección, la variable `Unknown` Es posible que las etiquetas se hayan mostrado incorrectamente cuando no se pasó un Nombre de página o un Nombre de vínculo en una visita, de forma predeterminada [!UICONTROL URL de página] y [!UICONTROL URL de vínculo], respectivamente. Estas dimensiones se configuraron para que no distinguen entre mayúsculas y minúsculas. Con esta corrección, los informes a partir de ahora serán correctos. Sin embargo, en el caso de los informes con datos históricos, es posible que algunos resultados de informes se etiqueten incorrectamente como `Unknown`. (AN-328030)

### Otras correcciones

-315676; AN-; AN-323398; AN-326209; AN-328178; AN-328261; AN-328395; AN-328671; AN-329282; AN-329330; AN-329355; AN-329506; AN-329516; AN-329738; AN-329769; AN-329771; AN-329816; AN-329877; AN-329928; AN-329957; AN-329962; AN-329966; AN-330023; AN-330081; AN-330083; AN-330105; AN-330138; AN-330140; AN-330165; AN-330241; AN-330359; AN-330366; AN-330427; AN-330438; AN-330442; AN-330534; AN-330616; AN-330654; AN-330783; AN-330879; AN-330881; AN-330883; AN-330887; AN-330888; AN-330955; AN-330979; AN-331031; AN-331053; AN-331068; AN-331071; AN-331074; AN-331075; AN-331076; AN-331078; AN-331085; AN-331093; AN-331167; AN-331171; AN-331181; AN-331196; AN-331226; AN-331258; AN-331260; AN-331279; AN-331286; AN-331290; AN-331365; AN-331375; AN-331376; AN-331454; AN-331519; AN-331570; AN-331590; AN-331593; AN-331603; AN-331751; AN-331816; AN-331897; AN-331900; AN-331906; AN-331926; AN-331929; AN-332031; AN-332067; AN-332101; AN-332114; AN-332156; AN-332201; AN-332225; AN-332253; AN-332277; AN-332361; AN-332370; AN-332386

## Avisos importantes para los administradores de Adobe Analytics {#admin}

| Aviso | Fecha de incorporación o actualizada | Descripción |
| ----------- | ---------- | ---------- |
| **Confusión de IP completa para visitas de Adobe Experience Edge** | 27 de septiembre de 2023 | La confusión de IP para las visitas procedentes de Experience Edge se actualizará más adelante en octubre de 2023. En abril de 2023, Experience Edge agregó la capacidad de proteger las direcciones IP. En ese momento, Adobe Analytics solo admitía la ofuscación parcial de direcciones IP, debido a la forma en que Analytics procesa las visitas de Experience Edge. Cuando los clientes eligieron la ofuscación completa para Experience Edge, Analytics solo recibía direcciones IP parcialmente ofuscadas. Cuando se implemente este cambio, Analytics recibirá la IP totalmente oculta. |
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

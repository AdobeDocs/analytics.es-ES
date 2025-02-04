---
title: Notas de la versión de Adobe Analytics actual
description: Ver las notas de la versión actuales de Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: d7beee25af3551426eb905f0e727545de068b2d9
workflow-type: tm+mt
source-wordcount: '882'
ht-degree: 71%

---

# Notas de la versión actual de Adobe Analytics (versión de enero de 2025)

**Última actualización**: 22 de enero de 2024

Estas notas de la versión abarcan el periodo de lanzamiento de 15 de enero a mitad de febrero de 2025.  Las versiones de Adobe Analytics funcionan con un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funcionalidades. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Nuevas funciones o mejoras {#features}

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Programación en el nuevo Report Builder** | La programación no solo le permite programar los nuevos libros de Report Builder. También le permite recuperar los metadatos de tareas programadas antiguas al convertir libros heredados. De este modo, cuando convierte libros heredados en libros nuevos y los programa, los enviará a los mismos correos electrónicos y con la misma regularidad que los libros heredados. [Más información](/help/analyze/report-builder/schedule-reportbuilder.md) |  | 22 de enero de 2025 |
| **Mejoras en los informes (también conocidos como plantillas) en Analysis Workspace** | Ya hay varias mejoras disponibles para los informes (también conocidos como plantillas):<ul><li>Ahora se denominan [!UICONTROL Plantillas] (no [!UICONTROL Informes]).</li><li>Se ha mejorado la experiencia del usuario para ver y buscar plantillas, incluida la opción de ver plantillas en vista de columna o en vista de tarjeta.</li><li>Ubicación nueva y más intuitiva para las plantillas de compañía (ubicadas en **[!UICONTROL Espacio de trabajo]** > **[!UICONTROL Plantillas]**).</li><li>Anteriormente, se tenía acceso a las plantillas de compañía al crear un proyecto desde el cuadro de diálogo.</li><li>Hay más plantillas generadas previamente disponibles.</li></ul>[Más información](https://experienceleague.adobe.com/es/docs/analytics/analyze/analysis-workspace/templates/use-templates).<p>Los administradores pueden crear plantillas personalizadas y guardarlas para que otros usuarios de su compañía las utilicen en la misma sesión. [Más información](https://experienceleague.adobe.com/es/docs/analytics/analyze/analysis-workspace/templates/create-templates) | 15 de enero de 2025 | 30 de enero de 2025 |
| **Período de retención del ID de transacción** | El periodo de retención del ID de transacción de 90 días se ampliará a 25 meses en febrero de 2025. La variable `transactionID` identifica de forma exclusiva una transacción para que la visita se pueda enlazar a los datos cargados a través de las fuentes de datos. (Vínculos a la documentación próximamente) |  | 11 de febrero de 2025 |

## Correcciones en Adobe Analytics

**A4T**: AN-355602; AN-365988
**Activity Map**: AN-365320
**Admin Console**: AN-363884
**Herramientas de administración**: AN-356747; AN-358776
**Advertising Analytics**: AN-355488
**Analysis Workspace**: AN-345318; AN-354801; AN-357052; AN-358975; AN-362886; AN-363831; AN-364124; AN-365257; AN-365319; AN-365462; AN-366194
**API de Analytics 1.4**: AN-358059
**Clasificaciones**: AN-360049; AN-360424; AN-360745; AN-362208; AN-362345; AN-362560; AN-362576; AN-362633; AN-362653 AN-362815; AN-AN-AN; AN-362881; AN-362885; AN-AN; AN-363860; AN-AN; AN-364239; AN-364480; AN-364451; AN-362973; AN-363343; AN-363558; AN-364528; AN-364548; AN-AN; AN-362762;-AN;-AN;-364552;-AN;-364585 364598 364643 364715 364912 364997 365081 365189 365197 365203 365431 365647 365794 366546; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-
**Migración de componentes**: AN-362236; AN-365429
**Análisis de contribución**: AN-360146
**Fuentes de datos**: AN-356997; AN-362470; AN-362498; AN-362775; AN-363323; AN-363413; AN-363569; AN-364063; AN-364142; AN-364294; AN-364298; AN-364325; AN-364367; AN-364594; AN-364995; AN-365127; AN-365272; AN-365519; AN-365760; AN-366152;
**API de reparación de datos**: AN-362773; AN-362874
**Fuentes de datos**: AN-360745; AN-362202; AN-364566
**Data Warehouse**: AN-361447; AN-362616; AN-364524; AN-365108
**Aplicación móvil**: AN-362856; AN-365270
**Alertas de uso adicional**: AN-355594; AN-364547
**Plataforma**: AN-358914; AN-360205; AN-362990; AN-364550; AN-365454; AN-365485
**Report Builder**: AN-363478; AN-364433; AN-365610
**Administrador de actividades de creación de informes**: AN-362440
**Segmentación**: AN-359921
**Reglas de VISTA**: AN-362927

## Avisos importantes para los administradores de Adobe Analytics {#admin}

| Aviso | Fecha de incorporación o actualización | Descripción |
| ----------- | ---------- | ---------- |
| **Los clientes que no sean de Campaign perderán acceso a Triggers** | 16 de octubre de 2023 | El 30 de enero de 2025, los clientes de Adobe Analytics que no tengan una licencia de Adobe Campaign perderán acceso a la capacidad de configurar y utilizar [Triggers](https://experienceleague.adobe.com/es/docs/core-services/interface/services/triggers). Los clientes deben adquirir Campaign o planear dejar de utilizar Triggers, o buscar otras herramientas de Adobe que ofrezcan las funcionalidades de Triggers. |

## Avisos de final de la vida útil {#eol}

| Final de la vida útil de producto o función | Fecha de incorporación o actualización | Descripción |
| --- | --- | --- |
| **Migración a las credenciales de servidor a servidor de Adobe I/O OAuth** | 17 de enero de 2025 | Los clientes de la API de Adobe Analytics y Livestream que utilizan las credenciales de JWT de Adobe I/O deben migrar a las credenciales de servidor a servidor de Adobe I/O OAuth de forma predeterminada el **30 de junio de 2025**. Adobe I/O no permitirá que se creen nuevas credenciales de JWT a partir del 1 de mayo de 2024. Los clientes que utilizan JWT deben crear una nueva credencial de servidor a servidor OAuth o migrar su credencial JWT existente a una credencial de servidor a servidor OAuth. Los clientes también deben actualizar sus aplicaciones cliente para utilizar las nuevas credenciales de servidor a servidor de OAuth. <ul><li>[Migración de credenciales de cuenta de servicio (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guía de implementación para aplicaciones nuevas y antiguas con OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Uso de las nuevas credenciales de servidor a servidor de OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Preguntas frecuentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **Final de la vida útil de la API de Adobe Analytics (versión 1.4)** | 17 de julio de 2024 | El **12 de agosto de 2026**, los siguientes servicios de la API heredada de Analytics llegarán al final de su vida útil y se cerrarán, y las integraciones actuales creadas con estos servicios dejarán de funcionar:<ul><li>API de Adobe Analytics (versión 1.4)</li><li>Autenticación WSSE de Adobe Analytics</li></ul><p>Las integraciones que usan la API de Adobe Analytics (versión 1.4) deben migrarse a la [API de Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/), mientras que las integraciones de WSSE deben migrarse a un protocolo de autenticación basado en OAuth en [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Consulte las [preguntas frecuentes sobre el final de la vida útil de la API de Adobe Analytics 1.4](/help/admin/c-admin-api/c-admin-14-api-eol.md) para obtener respuestas a dudas comunes y más indicaciones.</p> |


## AppMeasurement

Para obtener las últimas actualizaciones de las versiones de AppMeasurement (2.26.0), consulte las [notas de la versión de AppMeasurement para JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=es).


## Recursos relacionados

* [Notas de la versión anteriores de 2024](/help/release-notes/2024.md)
* [Notas de la versión de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=es)
* [Notas de la versión de la colección de medios de streaming](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
* Las últimas actualizaciones de la versión para los [productos de Adobe Experience Cloud](https://business.adobe.com/es/products/adobe-experience-cloud-products.html)

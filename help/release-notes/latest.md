---
title: Notas de la versión de Adobe Analytics actual
description: Ver las notas de la versión actuales de Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 04a6b5ac6e60f1cc2d1579306581a1025eb83230
workflow-type: tm+mt
source-wordcount: '767'
ht-degree: 93%

---

# Notas de la versión actuales de Adobe Analytics (versión de 23 de octubre de 2024)

**Última actualización**: 23 de octubre de 2024

Estas notas de la versión abarcan el periodo comprendido desde el 16 de octubre de 2024 hasta finales del año 2024. Las versiones de Adobe Analytics funcionan con un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funcionalidades. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Nuevas funciones o mejoras {#features}

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Nuevo Report Builder para Adobe Analytics** | La nueva aplicación Report Builder supone una actualización importante para Adobe Analytics, pues incluye rendimiento mejorado, interfaz de usuario optimizada, compatibilidad con la API 2.0 y con Microsoft Excel en Mac, Windows y exploradores web. Esta aplicación se puede utilizar junto con la aplicación heredada, pero no en el mismo archivo. Se proporciona una función de actualización para actualizar los libros heredados a la nueva aplicación. [Más información](https://experienceleague.adobe.com/en/docs/analytics/analyze/report-builder/report-buider-overview) |  | 16 de octubre de 2024 |
| **Exportación de JSON para migrar la implementación de etiquetas a las etiquetas de SDK web** | Esta actualización de la extensión de etiquetas de Analytics está relacionada con la migración a SDK web. Puede utilizar esta actualización de la extensión de Adobe Analytics como parte del flujo de trabajo para volver a crear las configuraciones de extensión con la extensión de SDK web. En la extensión de etiquetas de Adobe Analytics, puede ver la configuración de variables eVar, props y eventos como JSON, que se puede exportar para su edición e inclusión en la extensión de SDK web. |  | 31 de octubre de 2024 |
| **Nueva información sobre los factores de solicitud en el rendimiento de Analysis Workspace** | Ahora hay disponible una nueva sección &quot;Factores de solicitud&quot; al analizar el rendimiento en Analysis Workspace. Para obtener más información sobre cómo se procesan las solicitudes y los diversos factores que influyen en los tiempos de procesamiento, consulte &quot;Factores de solicitud&quot; en [Optimizar el rendimiento de Analysis Workspace](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/workspace-faq/optimizing-performance). |  | miércoles, 01 de octubre de 2024 |

## Correcciones en Adobe Analytics

Analysis Workspace: AN-356287; AN-358435; AN-359456; AN-359826; AN-360215
Herramientas de administración: AN-342485; AN-347931; AN-348704; AN-357723; AN-358453; AN-358717; AN-359548; AN-360136
Clasificaciones: AN-359025; AN-359283; AN-359368; AN-359710; AN-359752; AN-359759; AN-359799; AN-359887; AN-360543; AN-360566; AN-360612; AN-360741; AN-360942; AN-360952
Analytics entre dispositivos: AN-359210
Atributos del cliente: AN-357897
Recopilación de datos: AN-351131; AN-351309; AN-355678; AN-359856
Fuentes de datos: AN-359699
API de reparación de datos: AN-360256
Fuentes de datos: AN-359290
Data Warehouse: AN-359820
Alertas de sobrecarga: AN-358132

## Avisos importantes para los administradores de Adobe Analytics {#admin}

| Aviso | Fecha de incorporación o actualización | Descripción |
| ----------- | ---------- | ---------- |
| **Los clientes que no sean de Campaign perderán acceso a Triggers** | 16 de octubre de 2023 | El 30 de enero de 2025, los clientes de Adobe Analytics que no tengan una licencia de Adobe Campaign perderán acceso a la capacidad de configurar y consumir Triggers. Los clientes deben adquirir Campaign o planear dejar de utilizar Triggers, o buscar otras herramientas de Adobe que ofrezcan las funcionalidades de Triggers. |
| **Campos XDM de detalle de implementación adicionales asignados automáticamente** | 11 de septiembre de 2024 | Al utilizar Adobe Experience Platform Edge Network para enviar datos a Adobe Analytics, los campos XDM `xdm.implementationdetails.name` y `xdm.implementationdetails.environment` ahora siempre se asignan a las variables de datos de contexto `c.a.x.implementationdetails.name` y `c.a.x.implementationdetails.environment`. Anteriormente, algunos escenarios evitaban que estos valores se rellenaran. Ajuste las reglas de procesamiento relevantes para considerar la disponibilidad de estos valores. |

## Avisos de final de la vida útil {#eol}

| Final de la vida útil de producto o función | Fecha de incorporación o actualización | Descripción |
| --- | --- | --- |
| **Final de la vida útil de la API de Adobe Analytics (versión 1.4)** | 17 de julio de 2024 | El **12 de agosto de 2026**, los siguientes servicios de la API heredada de Analytics llegarán al final de su vida útil y se cerrarán, y las integraciones actuales creadas con estos servicios dejarán de funcionar:<ul><li>API de Adobe Analytics (versión 1.4)</li><li>Autenticación WSSE de Adobe Analytics</li></ul><p>Las integraciones que usan la API de Adobe Analytics (versión 1.4) deben migrarse a la [API de Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/), mientras que las integraciones de WSSE deben migrarse a un protocolo de autenticación basado en OAuth en [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Consulte las [preguntas frecuentes sobre el final de la vida útil de la API de Adobe Analytics 1.4](/help/admin/c-admin-api/c-admin-14-api-eol.md) para obtener respuestas a dudas comunes y más indicaciones.</p> |
| **Migración a las credenciales de servidor a servidor de Adobe I/O OAuth** | 11 de mayo de 2023 | Los clientes de la API de Adobe Analytics y Livestream que utilizan las credenciales de JWT de Adobe I/O deben migrar a las credenciales de servidor a servidor de Adobe I/O OAuth de forma predeterminada el **1 de enero de 2025**. Adobe I/O no permitirá que se creen nuevas credenciales de JWT a partir del 1 de mayo de 2024. Los clientes que utilizan JWT deben crear una nueva credencial de servidor a servidor OAuth o migrar su credencial JWT existente a una credencial de servidor a servidor OAuth. Los clientes también deben actualizar sus aplicaciones cliente para utilizar las nuevas credenciales de servidor a servidor de OAuth. <ul><li>[Migración de credenciales de cuenta de servicio (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guía de implementación para aplicaciones nuevas y antiguas con OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Uso de las nuevas credenciales de servidor a servidor de OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Preguntas frecuentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |


## AppMeasurement

Para obtener las últimas actualizaciones de las versiones de AppMeasurement (2.26.0), consulte las [notas de la versión de AppMeasurement para JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=es).


## Recursos relacionados

* [Notas de la versión anteriores de 2024](/help/release-notes/2024.md)
* [Notas de la versión de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=es)
* [Notas de la versión del complemento de colección Streaming Media](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
* Las últimas actualizaciones de la versión para los [productos de Adobe Experience Cloud](https://business.adobe.com/products/adobe-experience-cloud-products.html?lang=es)

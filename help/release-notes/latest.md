---
title: Notas de la versión de Adobe Analytics actual
description: Ver las notas de la versión actuales de Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: ace906a4b5acf1ab667529af33dd5be1618863f2
workflow-type: tm+mt
source-wordcount: '697'
ht-degree: 100%

---

# Notas de la versión de Adobe Analytics actual (versión de febrero de 2025)

**Última actualización**: sábado, 21 de febrero de 2025

Estas notas de la versión abarcan el periodo de lanzamiento del 11 de febrero a mitad de marzo de 2025.  Las versiones de Adobe Analytics funcionan con un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funcionalidades. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Nuevas funciones o mejoras {#features}

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Período de retención del ID de transacción** | El período de retención del ID de transacción de 90 días se ha ampliado a 25 meses. La variable `transactionID` identifica de forma exclusiva una transacción para que la visita se pueda enlazar a los datos cargados a través de las fuentes de datos. Más información [aquí](https://experienceleague.adobe.com/es/docs/analytics/implementation/vars/page-vars/transactionid) y [aquí](https://experienceleague.adobe.com/es/docs/analytics/import/data-sources/transactionid). |  | 20 de febrero de 2025 |
| **Referencia de API de feeds de datos** | La [referencia](https://adobedocs.github.io/analytics-2.0-apis/?urls.primaryName=Data%20Feeds%20APIs) de la API de feeds de datos ya está disponible. |  | 30 de enero de 2025 |
| **API de Livestream: implementación de cliente** | Utilice la implementación del cliente de Livestream para consumir datos de Livestream. [Más información](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/clientcode/) |  | 18 de febrero de 2025 |
| **Actualización de la API de clasificaciones** | Ahora puede quitar campos de clasificación o claves individuales del servidor. Esto proporciona una alternativa a eliminar un conjunto de datos de clasificación completo con el método DELETE. [Más información](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/classifications/remove-values) |  | 18 de febrero de 2025 |
| **Actualizar al campo de datos de contexto de Analytics`a.locale`** | Una actualización programada cambiará la forma en que se establece el campo de datos de contexto `a.locale` de Analytics al recopilar datos mediante Experience Edge. Cuando se envían datos a Adobe Analytics mediante Experience Edge, los campos de Analytics se rellenan en función de una asignación de campos XDM. La asignación de `c.a.locale` hace referencia a un campo XDM no estándar, `xdm.environment.language`. Este campo se actualizará para hacer referencia al campo correcto, `xdm.environment._dc.language`.<p>La asignación seguirá haciendo referencia a `xdm.environment.language` de cara a la compatibilidad con versiones anteriores. Para mantener la continuidad, si se establecen ambos campos, `xdm.environment.language` tendrá prioridad. Puede ver la lista completa de asignaciones de XDM a campos estándar de Analytics [aquí](https://experienceleague.adobe.com/es/docs/analytics/implementation/aep-edge/xdm-var-mapping). | | 5 de marzo de 2025 |


## Correcciones en Adobe Analytics

**Analysis Workspace**: AN-359974; AN-366212; AN-368460
**Clasificaciones**: AN-367186; AN-367328; AN-368548
**Migración de componentes**: AN-364529; AN-366398; AN-367509;
**Feeds de datos**: AN-365685; AN-366745; AN-367256; AN-367349; AN-368363
**Data Warehouse**: AN-368178; AN-368331;
**Aplicación móvil**: AN-367137
**Plataforma**: AN-351924; AN-365540; AN-365866; AN-366898; AN-367856; AN-367933
**Report Builder**: AN-366456; AN-366655;
**Grupos de informes virtuales**: AN-367411
**Reglas de VISTA**: AN-365331

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

Para obtener las últimas actualizaciones de las versiones de AppMeasurement (2.27.0), consulte las [notas de la versión de AppMeasurement para JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=es).


## Recursos relacionados

* [Notas de la versión anteriores de 2024](/help/release-notes/2024.md)
* [Notas de la versión de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=es)
* [Notas de la versión de la colección de medios de streaming](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
* Las últimas actualizaciones de la versión para los [productos de Adobe Experience Cloud](https://business.adobe.com/es/products/adobe-experience-cloud-products.html?lang=es)

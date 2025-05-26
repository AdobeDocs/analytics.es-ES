---
title: Notas de la versión de Adobe Analytics actual
description: Ver las notas de la versión actuales de Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 9c6da2c1ed5bc2c016da16a5bb821f0064e1ae4f
workflow-type: ht
source-wordcount: '689'
ht-degree: 100%

---

# Notas de la versión actual de Adobe Analytics (versión de mayo de 2025)

**Última actualización:** 14 de mayo de 2025

Estas notas de la versión cubren el período comprendido entre el xx de abril y el 18 de junio de 2025. Las versiones de Adobe Analytics funcionan con un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funcionalidades. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Nuevas funciones o mejoras {#features}

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **El panel izquierdo de Analysis Workspace ya no se abre y se cierra al pasar el puntero por encima** | El panel izquierdo de Analysis Workspace se utiliza para añadir elementos como componentes, paneles y visualizaciones al proyecto. La opción para abrir temporalmente el panel izquierdo pasando el puntero por encima de uno de los iconos del extremo izquierdo ya no está disponible. En su lugar, simplemente haga clic en uno de estos iconos para mantener el panel abierto y, a continuación, haga clic en el mismo icono para cerrarlo. |  | 29 de mayo de 2025 |


## Correcciones en Adobe Analytics

**Alertas**: AN-378351
**Analysis Workspace**: AN-363521; AN-367366; AN-373575; AN-374238; AN-374295; AN-374382; AN-376938; AN-377176; AN-377467; AN-377942
**Transferencia de recurso**: AN-373381
**Clasificaciones**: AN-373166; AN-373479; AN-376074; AN-377337; AN-377505
**Componentes**: AN-314468
**Feed de datos**: AN-370241; AN-375267; AN-376940
**Fuentes de datos**: AN-375259
**Data Warehouse**: AN-370415; AN-372090;
**Plataforma**: AN-365681; AN-372306; AN-372616;
**Creación de informes en tiempo real**: AN-365681
**Report Builder**: AN-371395
**Segmentación**: AN-373576; AN-375858
**Grupos de informes virtuales**: AN-377948; AN-377952
**Reglas Vista**: AN-373292

## Avisos importantes para los administradores de Adobe Analytics {#admin}

| Aviso | Fecha de incorporación o actualización | Descripción |
| ----------- | ---------- | ---------- |
| **El panel izquierdo de Analysis Workspace ya no se abre y se cierra al pasar el puntero por encima** | El panel izquierdo de Analysis Workspace se utiliza para añadir elementos como componentes, paneles y visualizaciones al proyecto. La opción para abrir temporalmente el panel izquierdo pasando el puntero por encima de uno de los iconos del extremo izquierdo ya no está disponible. En su lugar, simplemente haga clic en uno de estos iconos para mantener el panel abierto y, a continuación, haga clic en el mismo icono para cerrarlo. |  | 29 de mayo de 2025 |


## Avisos de final de la vida útil {#eol}

| Final de la vida útil de producto o función | Fecha de incorporación o actualización | Descripción |
| --- | --- | --- |
| **Acceso a través de dominios heredados o a través de SSO heredado** | 10 de abril de 2025 | Adobe tiene previsto actualizar el modo en que los usuarios acceden a Adobe Analytics para mejorar la seguridad y optimizar el inicio de sesión. Como parte de este esfuerzo, el acceso a través de dominios heredados o a través del SSO heredado, incluido `my.omniture.com`, se suspenderá permanentemente el **2 de enero de 2026**. Después de esta fecha, las credenciales de inicio de sesión heredadas y el SSO heredado dejarán de funcionar. Se solicitará a todos los usuarios que inicien sesión a través de `experience.adobe.com` mediante sus ID de Adobe Experience. Si necesita ayuda con relación a su ID de Experience Cloud, póngase en contacto con el administrador de Adobe Analytics de su organización o con el [Servicio de atención al cliente de Adobe](https://helpx.adobe.com/es/contact.html?lang=es). |
| **Migración a las credenciales de servidor a servidor de OAuth para Adobe IO** | 17 de enero de 2025 | Los clientes de la API de Adobe Analytics y Livestream que utilizan las credenciales de JWT de Adobe I/O deben migrar a las credenciales de servidor a servidor de Adobe I/O OAuth de forma predeterminada el **30 de junio de 2025**. Adobe I/O no permitirá que se creen nuevas credenciales de JWT a partir del 1 de mayo de 2024. Los clientes que utilizan JWT deben crear una nueva credencial de servidor a servidor OAuth o migrar su credencial JWT existente a una credencial de servidor a servidor OAuth. Los clientes también deben actualizar sus aplicaciones cliente para utilizar las nuevas credenciales de servidor a servidor de OAuth. <ul><li>[Migración de credenciales de cuenta de servicio (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration)</li><li>[Guía de implementación para aplicaciones nuevas y antiguas con OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation)<li>[Uso de las nuevas credenciales de servidor a servidor de OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation)</li><li>[Preguntas frecuentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs)</li></ul> |
| **Final de la vida útil de la API de Adobe Analytics (versión 1.4)** | 17 de julio de 2024 | El **12 de agosto de 2026**, los siguientes servicios de la API heredada de Analytics llegarán al final de su vida útil y se cerrarán, y las integraciones actuales creadas con estos servicios dejarán de funcionar:<ul><li>API de Adobe Analytics (versión 1.4)</li><li>Autenticación WSSE de Adobe Analytics</li></ul><p>Las integraciones que usan la API de Adobe Analytics (versión 1.4) deben migrarse a la [API de Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/), mientras que las integraciones de WSSE deben migrarse a un protocolo de autenticación basado en OAuth en [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Consulte las [preguntas frecuentes sobre el final de la vida útil de la API de Adobe Analytics 1.4](/help/admin/c-admin-api/c-admin-14-api-eol.md) para obtener respuestas a dudas comunes y más indicaciones.</p> |


## AppMeasurement

Para obtener las últimas actualizaciones de las versiones de AppMeasurement, consulte las [notas de la versión de AppMeasurement](https://github.com/adobe/appmeasurement/releases).


## Recursos relacionados

* [Notas de la versión anteriores de 2025](/help/release-notes/2025.md)
* [Notas de la versión de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=es)
* [Notas de la versión de la colección de medios de streaming](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
* Las últimas actualizaciones de la versión para los [productos de Adobe Experience Cloud](https://business.adobe.com/products/adobe-experience-cloud-products.html?lang=es)

---
title: Notas de la versión de Adobe Analytics actual
description: Ver las notas de la versión actuales de Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: d81412790f5658d90890c48eca50548cd57b4b48
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Notas de la versión actual de Adobe Analytics (versión de marzo de 2025)

**Última actualización**: sábado, 11 de abril de 2025

Estas notas de la versión cubren el período comprendido entre el 5 de marzo de 2025 y mayo de 2025. Las versiones de Adobe Analytics funcionan con un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funcionalidades. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Nuevas funciones o mejoras {#features}

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Inventario de Analytics** | En esta página se ofrece información general completa sobre el entorno de Adobe Analytics, incluido el número de proyectos y componentes, grupos de informes, usuarios, etc. Al automatizar el proceso de inventario, puede comprender rápidamente el esfuerzo necesario para cambiar de Adobe Analytics a Customer Journey Analytics. Esto hará que la transición sea más fácil y rápida. [Más información](https://experienceleague.adobe.com/es/docs/analytics/admin/admin-tools/analytics-inventory) |  | 26 de marzo de 2025 |
| **Actualizar al campo de datos de contexto de Analytics`a.locale`** | Esta actualización cambia la forma en que se establece el campo de datos de contexto de Analytics `a.locale` al recopilar datos mediante Experience Edge. Cuando se envían datos a Adobe Analytics mediante Experience Edge, los campos de Analytics se rellenan en función de una asignación de campos XDM. La asignación de `c.a.locale` hace referencia a un campo XDM no estándar, `xdm.environment.language`. Este campo se actualizará para hacer referencia al campo correcto, `xdm.environment._dc.language`.<p>La asignación seguirá haciendo referencia a `xdm.environment.language` de cara a la compatibilidad con versiones anteriores. Para mantener la continuidad, si se establecen ambos campos, `xdm.environment.language` tendrá prioridad. Puede ver la lista completa de asignaciones de XDM a campos estándar de Analytics [aquí](https://experienceleague.adobe.com/es/docs/analytics/implementation/aep-edge/xdm-var-mapping). | | 5 de marzo de 2025 |
| **Guía de actualización de Customer Journey Analytics** | Le permite generar una guía paso a paso para actualizar de Adobe Analytics a Customer Journey Analytics. Esta guía está adaptada a su organización y tiene en cuenta su entorno Adobe Analytics actual, los usos previstos para Customer Journey Analytics y cualquier cambio que su organización desee hacer para ahorrar tiempo.<p>Para empezar a generar su guía personalizada, inicie sesión en [!DNL Customer Journey Analytics] y, a continuación, seleccione **[!UICONTROL Actualizar a Customer Journey Analytics]** en la pestaña **[!UICONTROL Workspace]**.<p>[Más información](https://experienceleague.adobe.com/es/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-recommendations#recommended-upgrade-steps-for-most-organizations) |  | 11 de marzo de 2025 |
| **Dimensiones de Data Warehouse solamente** | En función de los comentarios de los clientes, hemos decidido volver a evaluar. No lanzaremos la función automática solo para Data Warehouse como se anunció anteriormente. | | Por determinar |


## Correcciones de Adobe Analytics

**Activity Map**: AN-361038
**Herramientas de administración**: AN-362178; AN-369483
**API de Analytics 1.4**: AN-369615
**Analysis Workspace**: AN-353491; AN-363403; AN-367230; AN-367313; AN-368582; AN-369821; AN-370227;
**Clasificaciones**: AN-369848; AN-370196; AN-370226; AN-370437
**Fuentes de datos**: AN-366162; AN-368906; AN-369066; AN-369087; AN-369225; AN-369798
**Control de datos**: AN-365157
**Fuentes de datos**: AN-367550
**Plataforma**: AN-363931
**Report Builder**: AN-367460; AN-368975

## Avisos importantes para los administradores de Adobe Analytics {#admin}

| Aviso | Fecha de incorporación o actualización | Descripción |
| ----------- | ---------- | ---------- |
| N/A |  |  |

## Avisos de final de la vida útil {#eol}

| Final de la vida útil de producto o función | Fecha de incorporación o actualización | Descripción |
| --- | --- | --- |
| **Migración a las credenciales de servidor a servidor de Adobe I/O OAuth** | 17 de enero de 2025 | Los clientes de la API de Adobe Analytics y Livestream que utilizan las credenciales de JWT de Adobe I/O deben migrar a las credenciales de servidor a servidor de Adobe I/O OAuth de forma predeterminada el **30 de junio de 2025**. Adobe I/O no permitirá que se creen nuevas credenciales de JWT a partir del 1 de mayo de 2024. Los clientes que utilizan JWT deben crear una nueva credencial de servidor a servidor OAuth o migrar su credencial JWT existente a una credencial de servidor a servidor OAuth. Los clientes también deben actualizar sus aplicaciones cliente para utilizar las nuevas credenciales de servidor a servidor de OAuth. <ul><li>[Migración de credenciales de cuenta de servicio (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guía de implementación para aplicaciones nuevas y antiguas con OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Uso de las nuevas credenciales de servidor a servidor de OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Preguntas frecuentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **Final de la vida útil de la API de Adobe Analytics (versión 1.4)** | 17 de julio de 2024 | El **12 de agosto de 2026**, los siguientes servicios de la API heredada de Analytics llegarán al final de su vida útil y se cerrarán, y las integraciones actuales creadas con estos servicios dejarán de funcionar:<ul><li>API de Adobe Analytics (versión 1.4)</li><li>Autenticación WSSE de Adobe Analytics</li></ul><p>Las integraciones que usan la API de Adobe Analytics (versión 1.4) deben migrarse a la [API de Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/), mientras que las integraciones de WSSE deben migrarse a un protocolo de autenticación basado en OAuth en [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Consulte las [preguntas frecuentes sobre el final de la vida útil de la API de Adobe Analytics 1.4](/help/admin/c-admin-api/c-admin-14-api-eol.md) para obtener respuestas a dudas comunes y más indicaciones.</p> |


## AppMeasurement

Para obtener las últimas actualizaciones de las versiones de AppMeasurement, consulte las [notas de la versión de AppMeasurement](https://github.com/adobe/appmeasurement/releases).


## Recursos relacionados

* [Notas de la versión anteriores de 2025](/help/release-notes/2025.md)
* [Notas de la versión de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=es)
* [Notas de la versión de la colección de medios de streaming](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
* Las últimas actualizaciones de la versión para los [productos de Adobe Experience Cloud](https://business.adobe.com/products/adobe-experience-cloud-products.html?lang=es)

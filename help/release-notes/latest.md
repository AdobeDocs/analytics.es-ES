---
title: Notas de la versión de Adobe Analytics actual
description: Ver las notas de la versión actuales de Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 7a245e2c24e8763c93150aa5b9f3ac2d197f6f1f
workflow-type: tm+mt
source-wordcount: '1041'
ht-degree: 62%

---

# Notas de la versión actuales de Adobe Analytics (abril de 2026)

**Última actualización**: viernes, 09 de abril de 2026

Estas notas de la versión abarcan el período de la versión de abril de 2026. Las versiones de Adobe Analytics funcionan con un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funcionalidades. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Nuevas funciones o mejoras {#features}

| Función y descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ---- |
| **Servidores MCP para Adobe Analytics** <br/>Ahora puede vincular Adobe Analytics a sus flujos de trabajo agénticos existentes mediante MCP (Model Context Protocol). Puede solicitar informes y perspectivas utilizando lenguaje natural.<p>(Vínculo a la documentación a continuación).</p> | | Finales de abril de 2026 |
| **Servicios de medios de streaming: datos de programación de soporte** <br/>Ahora puede cargar datos programados de contenido de medios de streaming en vivo anteriores para rastrear la audiencia de manera más fácil y precisa.<p>Los siguientes son ejemplos de contenidos en directo compatibles con la carga de datos de programación:</p><ul><li>Plataformas FAST (Free Ad Supported TV)</li><li>Streams locales</li><li>Deportes en directo</li></ul><p>La carga de datos de programación le permite realizar un seguimiento de los datos del número de espectadores de los programas individuales que se emitieron durante el tiempo designado en el archivo de carga. Incluso puede recopilar datos del número de espectadores de temas específicos o segmentos de programa.</p><p>Estas funciones están disponibles independientemente de cómo haya implementado la recopilación de medios de streaming.</p><p>Anteriormente, era difícil vincular con precisión una sesión determinada a programas específicos cuando se analizaba contenido en directo, y no era posible vincular una sesión determinada a temas o segmentos de programa individuales.</p><p>Para obtener más información, consulte [Cargar datos de programación para realizar un seguimiento del contenido en directo](https://experienceleague.adobe.com/es/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 29 de octubre de 2025 | Primer semestre de 2026<p>(Originalmente planificado para su lanzamiento el 29 de octubre de 2025)</p> |
| **Formato de intervalo de fechas de API adicional**<br/> Ahora se admiten dos nuevos formatos para especificar intervalos de fechas en solicitudes de informes de API de Analytics 2.0. Esto incluye una fórmula de fecha y un formato mixto. [Más información](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/#date-range-field--supported-formats) | | Marzo de 2026 |
| **Dimensión opcional en solicitudes de informes de API**<br/> No se requiere un objeto de dimensión en las solicitudes de API de informes. Si no se especifica ninguna dimensión, la respuesta muestra los datos de un informe de totales. [Más información](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/#using-dimension-in-report-payload-requests) | | Marzo de 2026 |
| **Informe de API avanzada con tendencias por fecha**<br/> Nueva Guía de informes avanzados con tendencias por fecha de API de Adobe Analytics 2.0. Cree informes avanzados de API de tendencias por fecha utilizando comparaciones y segmentos de intervalos de fechas. [Más información](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/advanced/) | | Marzo de 2026 |

## Correcciones en Adobe Analytics

**Activity Map**:
**Analysis Workspace**: AN-442813, AN-442410, AN-441943, AN-441717, AN-434855, AN-431409, AN-429777, AN-429048, AN-428892, AN-428189, AN-425215
**Clasificaciones**: AN-443453, AN-443275, AN-443148, AN-442906, AN-442232, AN-442207, AN-442148, AN-442133, AN-441937, AN-441901, AN-441807, AN-441671, AN-441333, AN-441149, AN-441132, AN-441085, AN-441048, AN-440846, AN-440727, AN-441302, AN-440716, AN-440511, AN-440496, AN-432100, AN-, AN-, AN-, AN-, AN-
**Fuentes de datos y Data Warehouse**: AN-442211, AN-441719, AN-441183, AN-441011, AN-440625, AN-438953
**Migración**: AN-442467, AN-440380, AN-440357
**Exportaciones**:
**Report Builder**: AN-441136, AN-438147, AN-425150
**Informes**: AN-441506, AN-440919, AN-440545, AN-440300
**Grupos de informes**: AN-439429, AN-439423, AN-430988
**Informes programados**:
**Segmentación**:
**Otros**: AN-423359, AN-406242, AN-397985


## Avisos de final de la vida útil {#eol}

| Final de la vida útil de producto o función | Fecha de incorporación o actualización | Descripción |
| --- | --- | --- |
| **Mejoras en el procesamiento de Livestream** | jueves, 14 de enero de 2026 | Adobe planea realizar mejoras y cambios en el formato de las cargas útiles de LiveStream. Estas actualizaciones proporcionan una mejor paridad entre LiveStream y otras funciones de Adobe Analytics, como Analysis Workspace. Hay disponible un punto final de previsualización que le permite probar los cambios planeados. Consulte [Notas de la versión de LiveStream](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/release-notes/) para ver la lista completa de cambios y los detalles del punto final de previsualización. Adobe planea una transición definitiva al formato de carga útil actualizado el 13 de abril de 2026. |
| **Eliminación de grupos de cifrado TLS 1.2** | jueves, 11 de febrero de 2026 | Aviso a los administradores: Adobe planea eliminar la compatibilidad con los siguientes grupos de cifrados TLS 1.2 de los servidores de recopilación de datos de Adobe el 27 de mayo de 2026.<ul><li>`TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_GCM_SHA256`</li><li>`TLS_RSA_WITH_AES_256_GCM_SHA384`</li></ul><p>No se requiere ninguna acción del cliente para la mayoría de las implementaciones. Este cambio afecta principalmente a los datos de Analytics enviados desde aplicaciones nativas heredadas que utilizan bibliotecas TLS obsoletas, y a un pequeño número de visitantes web en navegadores o sistemas operativos obsoletos. Al eliminar la compatibilidad con estos grupos de cifrado, se mejora la seguridad y se alinea Adobe con los estándares de cifrado modernos. Actualmente, menos del 0,1 % del tráfico de recopilación de datos depende de estos grupos de cifrado.</p> |
| **Report Builder heredado** | 18 de junio de 2025 | El complemento heredado de Report Builder se eliminará en junio de 2026. Todos los usuarios deberían empezar a actualizar sus libros heredados al [nuevo Report Builder](/help/analyze/report-builder/rb-overview.md). El nuevo Report Builder está disponible para los clientes de Adobe Analytics y Customer Journey Analytics. Tiene [casi paridad de características](/help/analyze/report-builder/convert-workbooks.md#unsupported), además de muchas nuevas características convenientes y mejoras en la interfaz de usuario. Para facilitar el proceso de actualización, el nuevo Report Builder incluye una sencilla función de conversión de libros. El nuevo Report Builder solo está disponible como complemento en Microsoft Store. Muchas organizaciones requieren un proceso de aprobación interno para poder poner el complemento a disposición de los usuarios. Deje tiempo para este proceso y empiece a trabajar con su organización ahora para asegurarse de que dispone de tiempo suficiente para actualizar los libros antes de la fecha límite. |
| **Acceso a través de dominios heredados o a través de SSO heredado** | 10 de abril de 2025 | Adobe tiene previsto actualizar el modo en que los usuarios acceden a Adobe Analytics para mejorar la seguridad y optimizar el inicio de sesión. Como parte de este esfuerzo, el acceso a través de dominios heredados o a través del SSO heredado, incluido `my.omniture.com`, se suspenderá permanentemente el **2 de enero de 2026**. Después de esta fecha, las credenciales de inicio de sesión heredadas y el SSO heredado dejarán de funcionar. Se solicitará a todos los usuarios que inicien sesión a través de `experience.adobe.com` mediante sus ID de Adobe Experience. Si necesita ayuda con relación a su ID de Experience Cloud, póngase en contacto con el administrador de Adobe Analytics de su organización o con el [Servicio de atención al cliente de Adobe](https://helpx.adobe.com/contact.html?lang=es). |
| **API de Adobe Analytics (versión 1.4)** | 17 de julio de 2024 | El **12 de agosto de 2026**, los siguientes servicios de la API heredada de Analytics llegarán al final de su vida útil y se cerrarán, y las integraciones actuales creadas con estos servicios dejarán de funcionar:<ul><li>API de Adobe Analytics (versión 1.4)</li><li>Autenticación WSSE de Adobe Analytics</li></ul><p>Las integraciones que usan la API de Adobe Analytics (versión 1.4) deben migrarse a la [API de Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/), mientras que las integraciones de WSSE deben migrarse a un protocolo de autenticación basado en OAuth en [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Consulte las [preguntas frecuentes sobre el final de la vida útil de la API de Adobe Analytics 1.4](https://developer.adobe.com/analytics-apis/docs/1.4/guides/eol/) para obtener respuestas a dudas comunes y más indicaciones.</p> |


## AppMeasurement

Para obtener las últimas actualizaciones de las versiones de AppMeasurement, consulte las [notas de la versión de AppMeasurement](https://github.com/adobe/appmeasurement/releases).


## Recursos relacionados

* [Notas de la versión anteriores de 2025](/help/release-notes/2025.md)
* [Notas de la versión de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=es)
* [Notas de la versión de los servicios de medios de streaming](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
* Las últimas actualizaciones de la versión para los [productos de Adobe Experience Cloud](https://business.adobe.com/es/products/adobe-experience-cloud-products.html)

---
title: Notas de la versión de Adobe Analytics actual
description: Ver las notas de la versión actuales de Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 683e204b1cb316b9474dd22194b377ade1d23cf4
workflow-type: tm+mt
source-wordcount: '971'
ht-degree: 45%

---

# Notas de la versión actuales de Adobe Analytics (versión de junio de 2025)

**Última actualización**: jueves, 18 de junio de 2025

Estas notas de la versión abarcan el periodo de lanzamiento del 18 de junio al 15 de julio de 2025. Las versiones de Adobe Analytics funcionan con un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funcionalidades. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Nuevas funciones o mejoras {#features}

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Compatibilidad con destinos seguros en el nuevo Report Builder** | Se han agregado nuevos destinos de exportación al complemento de Report Builder. Se admiten los siguientes destinos de almacenamiento en la nube: <ul><li>Amazon S3 Role ARN</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li></ul> FTP ya no es compatible por motivos de seguridad. (Vínculo a la documentación a continuación) |  | 19 de junio de 2025 (originalmente el 18 de junio) |
| **Nueva experiencia de vista previa** | El panel de vista previa, utilizado para obtener una vista previa de segmentos, métricas calculadas, etc., ahora utiliza una visualización de barras horizontales en lugar de una visualización de anillo. |  | jueves, 18 de junio de 2025 |
| **Cuadro de diálogo del modelo de atribución modificado** | Ahora puede definir el contenedor y el período de tiempo por separado en el cuadro de diálogo del modelo de atribución. |  | Junio de 18,2025 |
| **Se ha actualizado la navegación a la IU de Atributos del cliente** | Ahora se puede acceder directamente a la interfaz de usuario de Atributos del cliente desde el selector de aplicaciones en Adobe Experience Cloud. |  | Por determinar |
| **Medios de streaming: datos de programación de soporte** | Ahora puede cargar datos programados de contenido de medios de streaming en directo anterior para rastrear la audiencia de forma más fácil y precisa. Los siguientes son ejemplos de contenido en directo compatible con la carga de datos programada:<ul><li>Plataformas FAST (TV compatible con anuncios gratuitos)</li><li>Flujos locales</li><li>Deportes en directo</li></ul>La carga de datos de programación permite realizar un seguimiento de los datos de audiencia de programas individuales que se ejecutaron durante el tiempo designado en el archivo de carga. Incluso puede recopilar datos de audiencia de temas específicos o segmentos de programa. Estas funciones están disponibles independientemente de cómo haya implementado la recopilación de medios de streaming.<p>Anteriormente, era difícil vincular con precisión una sesión determinada a programas específicos al analizar contenido en directo, y no era posible vincular una sesión determinada a temas o segmentos de programa individuales. Más información |  | jueves, 25 de junio de 2025 |
| **Compatibilidad con el procesamiento previo de Chrome** | Controle cómo se comportan las bibliotecas de recopilación de datos cuando Chrome preprocesa una página. (Vínculo a la documentación a continuación) |  | martes, 30 de junio de 2025 |

## Correcciones en Adobe Analytics

**A4T**: AN-379045
**Advertising Analytics**: AN-377338
**Alertas**: AN-377229
**Analysis Workspace**: AN-378891; AN-379589; AN-379604; AN-381270; AN-382264; AN-382414;
**API 1.4**: AN-380188
**API 2.0**: AN-373078; AN-379006; AN-381248
**Clasificaciones**: AN-379209; AN-379315; AN-379567; AN-379573; AN-379749; AN-379764; AN-379818; AN-380433; AN-381670; AN-381751; AN-381994; AN-382055; AN-382682; AN-383059; AN-383409
**Análisis de contribución**: AN-369822
**Fuentes de datos**: AN-365552; AN-367158; AN-378288; AN-379754; AN-380433; AN-380855; AN-380959; AN-381115; AN-381657; AN-381931
**Data Warehouse**: AN-379244
**Plataforma**: AN-375847
**Reglas de procesamiento**: AN-375157
**Report Builder**: AN-371395; AN-372174; AN-373815; AN-383194
**Llamadas al servidor**: AN-380930
**Registros de uso y acceso**: AN-372130; AN-382123
**Grupos de informes virtuales**: AN-382010


## Avisos de final de la vida útil {#eol}

| Final de la vida útil de producto o función | Fecha de incorporación o actualización | Descripción |
| --- | --- | --- |
| **Report Builder heredado** | jueves, 18 de junio de 2025 | El complemento heredado de Report Builder se eliminará en junio de 2026. Todos los usuarios deberían empezar a actualizar sus libros heredados a [la nueva Report Builder](https://experienceleague.adobe.com/es/docs/analytics/analyze/report-builder/rb-overview). El nuevo Report Builder está disponible para los clientes de Adobe Analytics y Customer Journey Analytics. Tiene [casi paridad de características](https://experienceleague.adobe.com/en/docs/analytics/analyze/report-builder/convert-workbooks#unsupported), además de muchas nuevas características convenientes y mejoras en la interfaz de usuario. Para facilitar el proceso de actualización, la nueva Report Builder incluye una sencilla función de conversión de libros. El nuevo Report Builder solo está disponible como complemento a través de Microsoft Store. Muchas organizaciones requieren un proceso de aprobación interno para poder poner el complemento a disposición de los usuarios. Deje tiempo para este proceso y empiece a trabajar con su organización ahora para asegurarse de que dispone de tiempo suficiente para actualizar los libros antes de la fecha límite. |
| **Acceso a través de dominios heredados o a través de SSO heredado** | 10 de abril de 2025 | Adobe tiene previsto actualizar el modo en que los usuarios acceden a Adobe Analytics para mejorar la seguridad y optimizar el inicio de sesión. Como parte de este esfuerzo, el acceso a través de dominios heredados o a través del SSO heredado, incluido `my.omniture.com`, se suspenderá permanentemente el **2 de enero de 2026**. Después de esta fecha, las credenciales de inicio de sesión heredadas y el SSO heredado dejarán de funcionar. Se solicitará a todos los usuarios que inicien sesión a través de `experience.adobe.com` mediante sus ID de Adobe Experience. Si necesita ayuda con relación a su ID de Experience Cloud, póngase en contacto con el administrador de Adobe Analytics de su organización o con el [Servicio de atención al cliente de Adobe](https://helpx.adobe.com/contact.html?lang=es). |
| **Migración a las credenciales de servidor a servidor de OAuth para Adobe IO** | 17 de enero de 2025 | Los clientes de la API de Adobe Analytics y Livestream que utilizan las credenciales de JWT de Adobe I/O deben migrar a las credenciales de servidor a servidor de Adobe I/O OAuth de forma predeterminada el **30 de junio de 2025**. Adobe I/O no permitirá que se creen nuevas credenciales de JWT a partir del 1 de mayo de 2024. Los clientes que utilizan JWT deben crear una nueva credencial de servidor a servidor OAuth o migrar su credencial JWT existente a una credencial de servidor a servidor OAuth. Los clientes también deben actualizar sus aplicaciones cliente para utilizar las nuevas credenciales de servidor a servidor de OAuth. <ul><li>[Migración de credenciales de cuenta de servicio (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration)</li><li>[Guía de implementación para aplicaciones nuevas y antiguas con OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation)<li>[Uso de las nuevas credenciales de servidor a servidor de OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation)</li><li>[Preguntas frecuentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs)</li></ul> |
| **API de Adobe Analytics (versión 1.4)** | 17 de julio de 2024 | El **12 de agosto de 2026**, los siguientes servicios de la API heredada de Analytics llegarán al final de su vida útil y se cerrarán, y las integraciones actuales creadas con estos servicios dejarán de funcionar:<ul><li>API de Adobe Analytics (versión 1.4)</li><li>Autenticación WSSE de Adobe Analytics</li></ul><p>Las integraciones que usan la API de Adobe Analytics (versión 1.4) deben migrarse a la [API de Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/), mientras que las integraciones de WSSE deben migrarse a un protocolo de autenticación basado en OAuth en [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Consulte las [preguntas frecuentes sobre el final de la vida útil de la API de Adobe Analytics 1.4](/help/admin/c-admin-api/c-admin-14-api-eol.md) para obtener respuestas a dudas comunes y más indicaciones.</p> |



## AppMeasurement

Para obtener las últimas actualizaciones de las versiones de AppMeasurement, consulte las [notas de la versión de AppMeasurement](https://github.com/adobe/appmeasurement/releases).


## Recursos relacionados

* [Notas de la versión anteriores de 2025](/help/release-notes/2025.md)
* [Notas de la versión de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=es)
* [Notas de la versión de la colección de medios de streaming](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
* Las últimas actualizaciones de la versión para los [productos de Adobe Experience Cloud](https://business.adobe.com/products/adobe-experience-cloud-products.html?lang=es)

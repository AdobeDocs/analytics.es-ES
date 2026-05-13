---
title: Notas de la versión de Adobe Analytics actual
description: Ver las notas de la versión actuales de Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
TQID: https://experienceleague.adobe.com/yw30Yij2NBaeuWFqxD4-VH1Hysf8dxOpxHUwsFCYEw8
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 7c04b33e94152be8826005cb9617cb49dadbdcb9
workflow-type: tm+mt
source-wordcount: 1340
ht-degree: 62%

---

# Notas de la versión actuales de Adobe Analytics (mayo de 2026)

**Última actualización**: 13 de mayo de 2026

Estas notas de la versión abarcan el periodo de lanzamiento de mayo de 2026. Las versiones de Adobe Analytics funcionan con un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funcionalidades. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Nuevas funciones o mejoras {#features}

| Función y descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ---- |
| **Servidores MCP para Adobe Analytics** <br/>Los servidores MCP (Model Context Protocol) de Analytics le permiten conectar un cliente MCP compatible a Adobe Analytics. Una vez conectado, el cliente de MCP puede invocar herramientas específicas del producto para recuperar datos, ejecutar consultas o realizar operaciones admitidas como parte de un flujo de trabajo LLM o agéntico. Para obtener más información, consulte [Servidores MCP de Analytics](https://developer.adobe.com/analytics-mcp/docs/).<p>Si ha utilizado estos servidores MCP durante el período beta, tenga en cuenta que hay diferentes direcciones URL entre los extremos beta y de producción. Asegúrese de que todos los flujos de trabajo agénticos creados durante el periodo beta se actualicen para utilizar los extremos de producción antes del 31 de mayo.</p> | | 5 de mayo de 2026 |
| **Lienzo de Recorrido en Adobe Analytics** <br/>El lienzo de Recorrido es una visualización en Analysis Workspace que le permite obtener información más detallada sobre un recorrido de usuario definido mediante el análisis de cómo las personas salen o se alejan del recorrido. Permite crear un gráfico flexible de nodos y flechas que representan cualquier combinación de eventos, elementos de dimensión y segmentos incluidos en el recorrido. Los datos se actualizan a medida que arrastra nodos al lienzo o reorganiza los eventos y las condiciones del recorrido.<p>Anteriormente, el lienzo de recorrido solo estaba disponible para Customer Journey Analytics.</p><p>(Vínculo a la documentación a continuación).<!--To learn more about Journey canvas in Adobe Analytics, see Journey canvas overview. To learn how to build a Journey canvas visualization in Adobe Analytics, see Configure Journey canvas.--></p> | 18 de mayo de 2026 | 5 de junio de 2026 |
| **Guía de informes de API del modelo de atribución** <br/>Hay disponible una nueva Guía de informes del modelo de atribución de API de Adobe Analytics 2.0. La guía explica cómo incluir los datos de objeto del modelo de atribución en los informes de API de Dimension.<p>Para obtener más información, consulte [Modelos de atribución de API de Dimension](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/dimensions/attmodel).</p> | | Mayo de 2026 |
| **Servicios de medios de streaming: compatibilidad con los datos programados** <br/>Ahora puede cargar datos programados de contenido de medios de streaming transmitidos en directo en el pasado para realizar un seguimiento más fácil y preciso del número de espectadores.<p>Los siguientes son ejemplos de contenidos en directo compatibles con la carga de datos de programación:</p><ul><li>Plataformas FAST (Free Ad Supported TV)</li><li>Streams locales</li><li>Deportes en directo</li></ul><p>La carga de datos de programación le permite realizar un seguimiento de los datos del número de espectadores de los programas individuales que se emitieron durante el tiempo designado en el archivo de carga. Incluso puede recopilar datos del número de espectadores de temas específicos o segmentos de programa.</p><p>Estas funciones están disponibles independientemente de cómo haya implementado la recopilación de medios de streaming.</p><p>Anteriormente, era difícil vincular con precisión una sesión determinada a programas específicos cuando se analizaba contenido en directo, y no era posible vincular una sesión determinada a temas o segmentos de programa individuales.</p><p>Para obtener más información, consulte [Cargar datos de programación para realizar un seguimiento del contenido en directo](https://experienceleague.adobe.com/es/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 29 de octubre de 2025 | Primer semestre de 2026<p>(Originalmente planificado para su lanzamiento el 29 de octubre de 2025)</p> |

{style="table-layout:auto"}

## Correcciones en Adobe Analytics

**Activity Map**:
**Analysis Workspace**: AN-446522, AN-445779, AN-445759, AN-444676, AN-442813, AN-441943, AN-441717, AN-441538, AN-441123, AN-440976, AN-440952, AN-440919, AN-440599, AN-439797, AN-434855, AN-429777, AN-429048, AN-428892, AN-428189, AN-425215
**Clasificaciones**: AN-447743, AN-447296, AN-447130, AN-446552, AN-446324, AN-446040, AN-445841, AN-445753, AN-444992, AN-444979, AN-444332, AN-444428, AN-443507, AN-442906, AN-442232, AN, AN-442133, AN-442207, AN-442035, AN-441901, AN-441807, AN-441671, AN-441333, AN-441302, AN-441267, AN-441132, AN-441085, AN-441048, AN-440846, AN-440727, AN-440716, AN-440496, AN-440429 432100
**Fuentes de datos y Data Warehouse**: AN-447344, AN-446654, AN-445126, AN-444492, AN-442802, AN-442211, AN-442048, AN-441719, AN-441534, AN-441300, AN-441183, AN-441011, AN-440625
**Migración**: AN-442467, AN-440380, AN-440357
**Exportaciones**:
**Report Builder**: AN-448697, AN-447128, AN-441148, AN-441136, AN-438147, AN-425150
**Informes**: AN-445123, AN-444869, AN-443453, AN-443275, AN-443148, AN-442464, AN-442148, AN-441811, AN-441506, AN-441149, AN-441119, AN-440545, AN-440511, AN-440300, AN-431409, AN-423359, AN-406242
**Grupos de informes**:
**Informes programados**:
**Segmentación**:
**Otros**: AN-449159, AN-444661, AN-439429, AN-439423, AN-430988, AN-397985


## Avisos de final de la vida útil {#eol}

| Final de la vida útil de producto o función | Fecha de incorporación o actualización | Descripción |
| --- | --- | --- |
| **Mejoras en el procesamiento de Livestream** | jueves, 14 de enero de 2026 | Adobe planea realizar mejoras y cambios en el formato de las cargas útiles de LiveStream. Estas actualizaciones proporcionan una mejor paridad entre LiveStream y otras funciones de Adobe Analytics, como Analysis Workspace. Hay disponible un punto final de previsualización que le permite probar los cambios planeados. Consulte [Notas de la versión de LiveStream](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/release-notes/) para ver la lista completa de cambios y los detalles del punto final de previsualización. Adobe planea una transición definitiva al formato de carga útil actualizado el 13 de abril de 2026. |
| **Eliminación de grupos de cifrado de TLS 1.2** | 11 de febrero de 2026 | Aviso a los administradores: Adobe tiene previsto eliminar la compatibilidad con los siguientes grupos de cifrado TLS 1.2 de los servidores de recopilación de datos de Adobe el 27 de mayo de 2026.<ul><li>`TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_GCM_SHA256`</li><li>`TLS_RSA_WITH_AES_256_GCM_SHA384`</li></ul><p>No se requiere ninguna acción del cliente para la mayoría de las implementaciones. Este cambio afecta principalmente a los datos de Analytics enviados desde aplicaciones nativas heredadas que utilizan bibliotecas TLS obsoletas, y a un pequeño número de visitantes web en exploradores o sistemas operativos obsoletos. La eliminación de la compatibilidad con estos grupos de cifrado mejora la seguridad y permite a Adobe cumplir con los estándares de cifrado modernos. Actualmente, menos del 0,1 % del tráfico de recopilación de datos depende de estos grupos de cifrado.</p> |
| **Report Builder heredado** | 18 de junio de 2025 | El complemento heredado de Report Builder se eliminará en junio de 2026. Todos los usuarios deberían empezar a actualizar sus libros heredados al [nuevo Report Builder](/help/analyze/report-builder/rb-overview.md). El nuevo Report Builder está disponible para los clientes de Adobe Analytics y Customer Journey Analytics. Tiene [casi paridad de características](/help/analyze/report-builder/convert-workbooks.md#unsupported), además de muchas nuevas características convenientes y mejoras en la interfaz de usuario. Para facilitar el proceso de actualización, el nuevo Report Builder incluye una sencilla función de conversión de libros. El nuevo Report Builder solo está disponible como complemento en Microsoft Store. Muchas organizaciones requieren un proceso de aprobación interno para poder poner el complemento a disposición de los usuarios. Deje tiempo para este proceso y empiece a trabajar con su organización ahora para asegurarse de que dispone de tiempo suficiente para actualizar los libros antes de la fecha límite. |
| **Acceso a través de dominios heredados o a través de SSO heredado** | 10 de abril de 2025 | Adobe tiene previsto actualizar el modo en que los usuarios acceden a Adobe Analytics para mejorar la seguridad y optimizar el inicio de sesión. Como parte de este esfuerzo, el acceso a través de dominios heredados o a través del SSO heredado, incluido `my.omniture.com`, se suspenderá permanentemente el **2 de enero de 2026**. Después de esta fecha, las credenciales de inicio de sesión heredadas y el SSO heredado dejarán de funcionar. Se solicitará a todos los usuarios que inicien sesión a través de `experience.adobe.com` mediante sus ID de Adobe Experience. Si necesita ayuda con relación a su ID de Experience Cloud, póngase en contacto con el administrador de Adobe Analytics de su organización o con el [Servicio de atención al cliente de Adobe](https://helpx.adobe.com/es/contact.html?lang=es). |
| **API de Adobe Analytics (versión 1.4)** | 17 de julio de 2024 | El **12 de agosto de 2026**, los siguientes servicios de la API heredada de Analytics llegarán al final de su vida útil y se cerrarán, y las integraciones actuales creadas con estos servicios dejarán de funcionar:<ul><li>API de Adobe Analytics (versión 1.4)</li><li>Autenticación WSSE de Adobe Analytics</li></ul><p>Las integraciones que usan la API de Adobe Analytics (versión 1.4) deben migrarse a la [API de Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/), mientras que las integraciones de WSSE deben migrarse a un protocolo de autenticación basado en OAuth en [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Consulte las [preguntas frecuentes sobre el final de la vida útil de la API de Adobe Analytics 1.4](https://developer.adobe.com/analytics-apis/docs/1.4/guides/eol/) para obtener respuestas a dudas comunes y más indicaciones.</p> |


## AppMeasurement

Para obtener las últimas actualizaciones de las versiones de AppMeasurement, consulte las [notas de la versión de AppMeasurement](https://github.com/adobe/appmeasurement/releases).


## Recursos relacionados

* [Notas de la versión anteriores de 2025](/help/release-notes/2025.md)
* [Notas de la versión de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=es)
* [Notas de la versión de medios de streaming](https://experienceleague.adobe.com/es/docs/media-analytics/using/release-notes/release-notes)
* Las últimas actualizaciones de la versión para los [productos de Adobe Experience Cloud](https://business.adobe.com/es/products/adobe-experience-cloud-products.html)

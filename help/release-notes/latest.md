---
title: Notas de la versión de Adobe Analytics actual
description: Ver las notas de la versión actuales de Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
TQID: 'https://experienceleague.adobe.com/yw30Yij2NBaeuWFqxD4-VH1Hysf8dxOpxHUwsFCYEw8'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
    internal-label: Integrations
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: d89ba969-e026-48bf-927e-e9df2f1e34f3
    internal-label: Release notes
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
source-git-commit: 2fc50d801b70ee14c66725cec554b57cd117c8ee
workflow-type: tm+mt
source-wordcount: '967'
ht-degree: 53%
---
# Notas de la versión actuales de Adobe Analytics (octubre de 2026)

**Última actualización**: 7 de octubre de 2026

Estas notas de la versión abarcan el periodo de lanzamiento de octubre de 2026. Las versiones de Adobe Analytics funcionan con un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funcionalidades. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Nuevas funciones o mejoras {#features}

| Función y descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ---- |
| **Permiso de solo lectura para el servidor MCP de Adobe Analytics**<br/> Los administradores ahora pueden dar a los usuarios acceso de solo lectura al servidor MCP de Adobe Analytics. El nuevo elemento de permiso [!UICONTROL Acceso de solo lectura MCP] proporciona a los usuarios acceso a todas las herramientas de solo lectura, sin permitirles crear proyectos, segmentos o métricas calculadas.<p>Se cambió el nombre del elemento de permiso [!UICONTROL MCP Access] actual a [!UICONTROL MCP Full Access]. Los usuarios con este permiso mantienen el acceso a todas las herramientas, incluidas las que crean, cambian o eliminan componentes.</p><p>Para obtener más información, consulte [Servidor MCP de Adobe Analytics](https://developer.adobe.com/analytics-mcp/docs/aa/).</p> | | 6 de octubre de 2026 |
| **Generar automáticamente descripciones de componentes** <br/>Ahora puede generar automáticamente descripciones para dimensiones, métricas, métricas calculadas, segmentos e intervalos de fechas. Esto ayuda a los usuarios de Workspace a comprender qué componentes utilizar, especialmente en organizaciones con bibliotecas de componentes grandes. <p>Puede generar una descripción para un solo componente o generar descripciones para muchos componentes al mismo tiempo.</p> <p>(Vínculo a la documentación a continuación).<!--For more information, see [Automatically generate descriptions](/help/components/add-component-descriptions.md#automatically-generate-descriptions).--></p> | | 28 de octubre de 2026 |
| **Integración de Adobe Brand Visibility**<br/> Conecte Adobe Brand Visibility con los datos de Adobe Analytics de su organización para que pueda medir cómo la detección impulsada por IA se traduce en participación real en el sitio web y resultados comerciales.<p>(Vínculo a la documentación a continuación).</p> | | Octubre de 2026 |
| **CX Enterprise Coworker: Analice los datos de Adobe Analytics en el chat de compañeros** <br/>Adobe CX Enterprise Coworker Chat ahora puede realizar análisis de datos avanzados que anteriormente solo eran posibles en Analysis Workspace. El chat de compañeros accede a los datos de sus grupos de informes de Adobe Analytics, lo que le permite explorar esos datos y obtener respuestas a las preguntas que se hacen en lenguaje natural.<p>(Vínculo a la documentación a continuación).</p> | 2 de octubre de 2026 | Por determinar<p>(Originalmente planificado para el 25 de septiembre de 2026)</p> |

### Correcciones en Adobe Analytics

**Activity Map**: AN-494609, AN-493182
**Analysis Workspace**: AN-495340, AN-494789, AN-493307, AN-468900
**Clasificaciones**: AN-498043, AN-496619, AN-496468, AN-496217, AN-496133, AN-495567, AN-494651, AN-494345, AN-494312, AN-494261, AN-493645, AN-493507, AN-493336, AN-492869, AN-492812, AN-492751, AN-492750, AN-492741, AN-491032, AN-490802, AN-490796, AN-467849, AN-, AN-, AN-, AN-, AN-
**Fuentes de datos y Data Warehouse**: AN-494937, AN-493065, AN-489796, AN-479109
**Migración**: AN-489850, AN-468014
**Exportaciones**: AN-494337, AN-486563
**Report Builder**: AN-496602, AN-494224, AN-493737, AN-493508, AN-493505, AN-492806, AN-468981, AN-454376
**Informes**: AN-493637, AN-461260
**Grupos de informes**: AN-496773, AN-495227, AN-494981, AN-494372, AN-494370, AN-493629
**Informes programados**: AN-491103
**Segmentación**:
**Otros**: AN-496398, AN-494453, AN-492494

### Avisos de final de la vida útil {#eol}

| Final de la vida útil de producto o función | Fecha de incorporación o actualización | Descripción |
| --- | --- | --- |
| **Report Builder heredado** | 18 de junio de 2025 | El complemento heredado de Report Builder se retiró en junio de 2026. Todos los usuarios deberían empezar a actualizar sus libros heredados al [nuevo Report Builder](/help/analyze/report-builder/rb-overview.md). El nuevo Report Builder está disponible para los clientes de Adobe Analytics y Customer Journey Analytics. Tiene [casi paridad de características](/help/analyze/report-builder/convert-workbooks.md#unsupported), además de muchas nuevas características convenientes y mejoras en la interfaz de usuario. Para facilitar el proceso de actualización, el nuevo Report Builder incluye una sencilla función de conversión de libros. El nuevo Report Builder solo está disponible como complemento en Microsoft Store. Muchas organizaciones requieren un proceso de aprobación interno para poder poner el complemento a disposición de los usuarios. Deje tiempo para este proceso y empiece a trabajar con su organización ahora para asegurarse de que dispone de tiempo suficiente para actualizar los libros antes de la fecha límite. |
| **API de Adobe Analytics (versión 1.4)** | 17 de julio de 2024 | El **31 de agosto de 2026**, los siguientes servicios de la API heredada de Analytics llegaron al final de su vida útil y se cerraron, y todas las integraciones creadas con estos servicios ya no funcionan:<ul><li>API de Adobe Analytics (versión 1.4)</li><li>Autenticación WSSE de Adobe Analytics</li></ul><p>Las integraciones que usan la API de Adobe Analytics (versión 1.4) deben migrarse a la [API de Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/), mientras que las integraciones de WSSE deben migrarse a un protocolo de autenticación basado en OAuth en [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Consulte las [preguntas frecuentes sobre el final de la vida útil de la API de Adobe Analytics 1.4](https://developer.adobe.com/analytics-apis/docs/1.4/guides/eol/) para obtener respuestas a dudas comunes y más indicaciones.</p> |

## AppMeasurement

Para obtener las últimas actualizaciones de las versiones de AppMeasurement, consulte las [notas de la versión de AppMeasurement](https://github.com/adobe/appmeasurement/releases).

## Funciones aplazadas

| Función y descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| -----------|-----------|-----------|
| **Servicios de medios de streaming: compatibilidad con los datos programados** <br/>Ahora puede cargar datos programados de contenido de medios de streaming transmitidos en directo en el pasado para realizar un seguimiento más fácil y preciso del número de espectadores.<p>Los siguientes son ejemplos de contenidos en directo compatibles con la carga de datos de programación:</p><ul><li>Plataformas FAST (Free Ad Supported TV)</li><li>Streams locales</li><li>Deportes en directo</li></ul><p>La carga de datos de programación le permite realizar un seguimiento de los datos del número de espectadores de los programas individuales que se emitieron durante el tiempo designado en el archivo de carga. Incluso puede recopilar datos del número de espectadores de temas específicos o segmentos de programa.</p><p>Estas funciones están disponibles independientemente de cómo haya implementado la recopilación de medios de streaming.</p><p>Anteriormente, era difícil vincular con precisión una sesión determinada a programas específicos cuando se analizaba contenido en directo, y no era posible vincular una sesión determinada a temas o segmentos de programa individuales.</p><p>Para obtener más información, consulte [Cargar datos de programación para rastrear contenido en vivo](https://experienceleague.adobe.com/es/docs/media-analytics/using/media-use-cases/track-schedule-data).</p> | 29 de octubre de 2025 | Por determinar<p>(Originalmente planificado para el 29 de octubre de 2025)</p> |


>[!MORELIKETHIS]
>
>* [Notas de la versión anteriores de 2026](/help/release-notes/2026.md)
>* [Notas de la versión de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=es)
>* [Notas de la versión de los servicios de medios de streaming](https://experienceleague.adobe.com/es/docs/media-analytics/using/release-notes/release-notes)
>* Últimas actualizaciones de la versión para [productos de Adobe CX Enterprise](https://business.adobe.com/es/products/adobe-experience-cloud-products.html)


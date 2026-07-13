---
title: Notas de la versión de Adobe Analytics actual
description: Ver las notas de la versión actuales de Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
TQID: 'https://experienceleague.adobe.com/yw30Yij2NBaeuWFqxD4-VH1Hysf8dxOpxHUwsFCYEw8'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7id: fd307ce7-56f5-4ee3-af68-a7833ff6e85eid: a421fb65-2c82-457a-921c-28c46b697a39
subfeature_v2: id: d89ba969-e026-48bf-927e-e9df2f1e34f3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d095671a-1355-40aa-8b5f-06c33c68080bid: d3cdead0-685a-4489-9250-4bb709942f66id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ded4f0b735c19457c63c80f5a0c52f6b306c7b6f
workflow-type: tm+mt
source-wordcount: 922
ht-degree: 61%

---

# Notas de la versión actuales de Adobe Analytics (julio de 2026)

**Última actualización**: 8 de julio de 2026

Estas notas de la versión abarcan el periodo de la versión de julio de 2026. Las versiones de Adobe Analytics funcionan con un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funcionalidades. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Nuevas funciones o mejoras {#features}

| Función y descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ---- |
| **Análisis de subvisitas** <br/>El análisis de subvisitas le permite analizar los datos de los productos con un nivel más granular que el nivel de la visita. En lugar de filtrar visitas individuales completas, puede segmentar productos individuales dentro de las visitas. <p>Por ejemplo, puede segmentar una categoría de producto específica sin incluir todos los demás productos comprados en el mismo pedido.</p><p>Para obtener más información, consulte [Análisis de subvisitas](/help/components/segmentation/sub-hit.md).</p> | Julio de 8 | Finales de julio de 2026 |
| **Extensión de Activity Map: actualización de la interfaz de usuario** <br/>La extensión de superposición de Activity Map tiene un aspecto y un funcionamiento actualizados, además de mejoras subyacentes que admiten futuras mejoras.<p>(Vínculo a la documentación a continuación).</p> | | Finales de julio de 2026 |
| **Guía de características de búsqueda de API AA 2.0** <br/>Use características de búsqueda para [devolver un subconjunto de elementos de dimensión en los informes](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/search-filters).<p>Para obtener más información, consulte [Características de búsqueda](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/search-filters) en la guía de extremo de informes en Adobe Developer. | | 1 de julio de 2026 |
| **Automatización de informes recurrentes con API de AA** <br/>Configure informes de Adobe Analytics recurrentes y automáticos para su canalización de datos con métricas nuevas en una programación con la API de informes. <p>Para obtener más información, consulte la [Guía de extremo de informes de Analytics recurrentes de automatización](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/recurring) en Adobe Developer.</p> | | 1 de julio de 2026 |
| **Nuevos parámetros de expansión para AA** <br/>Use nuevos parámetros de expansión de la API de Dimension para recuperar los campos de configuración de eVar para los tipos de asignación, caducidades, tipos de datos y comercialización. <p>Para obtener más información, consulte [Referencia de API](https://developer.adobe.com/analytics-apis/docs/2.0/apis/#operation/dimensions_getDimensions) y [Guía de extremo de dimensiones](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/dimensions/) en Adobe Developer.</p> | | 1 de julio de 2026 |

### Correcciones en Adobe Analytics

**Activity Map**:
**Analysis Workspace**: AN-449890, AN-457527, AN-451161, AN-459034, AN-458071, AN-458398
**Clasificaciones**: AN-453318, AN-456739, AN-455828, AN-455270, AN-460272, AN-459367, AN-459239, AN-458418, AN-458417
**Fuentes de datos y Data Warehouse**: AN-456945, AN-460700
**Migración**:
**Exportaciones**:
**Report Builder**: AN-457533, AN-453683
**Informes**: AN-447692, AN-451259, AN-455713
**Grupos de informes**:
**Informes programados**: AN-450715
**Segmentación**:
**Otros**: AN-453982, AN-455771

### Avisos de final de la vida útil {#eol}

| Final de la vida útil de producto o función | Fecha de incorporación o actualización | Descripción |
| --- | --- | --- |
| **Report Builder heredado** | 18 de junio de 2025 | El complemento heredado de Report Builder se eliminará en junio de 2026. Todos los usuarios deberían empezar a actualizar sus libros heredados al [nuevo Report Builder](/help/analyze/report-builder/rb-overview.md). El nuevo Report Builder está disponible para los clientes de Adobe Analytics y Customer Journey Analytics. Tiene [casi paridad de características](/help/analyze/report-builder/convert-workbooks.md#unsupported), además de muchas nuevas características convenientes y mejoras en la interfaz de usuario. Para facilitar el proceso de actualización, el nuevo Report Builder incluye una sencilla función de conversión de libros. El nuevo Report Builder solo está disponible como complemento en Microsoft Store. Muchas organizaciones requieren un proceso de aprobación interno para poder poner el complemento a disposición de los usuarios. Deje tiempo para este proceso y empiece a trabajar con su organización ahora para asegurarse de que dispone de tiempo suficiente para actualizar los libros antes de la fecha límite. |
| **API de Adobe Analytics (versión 1.4)** | 17 de julio de 2024 | El **12 de agosto de 2026**, los siguientes servicios de la API heredada de Analytics llegarán al final de su vida útil y se cerrarán, y las integraciones actuales creadas con estos servicios dejarán de funcionar:<ul><li>API de Adobe Analytics (versión 1.4)</li><li>Autenticación WSSE de Adobe Analytics</li></ul><p>Las integraciones que usan la API de Adobe Analytics (versión 1.4) deben migrarse a la [API de Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/), mientras que las integraciones de WSSE deben migrarse a un protocolo de autenticación basado en OAuth en [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Consulte las [preguntas frecuentes sobre el final de la vida útil de la API de Adobe Analytics 1.4](https://developer.adobe.com/analytics-apis/docs/1.4/guides/eol/) para obtener respuestas a dudas comunes y más indicaciones.</p> |

## AppMeasurement

Para obtener las últimas actualizaciones de las versiones de AppMeasurement, consulte las [notas de la versión de AppMeasurement](https://github.com/adobe/appmeasurement/releases).

## Funciones aplazadas

| Función y descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| -----------|-----------|-----------|
| **Servicios de medios de streaming: compatibilidad con los datos programados** <br/>Ahora puede cargar datos programados de contenido de medios de streaming transmitidos en directo en el pasado para realizar un seguimiento más fácil y preciso del número de espectadores.<p>Los siguientes son ejemplos de contenidos en directo compatibles con la carga de datos de programación:</p><ul><li>Plataformas FAST (Free Ad Supported TV)</li><li>Streams locales</li><li>Deportes en directo</li></ul><p>La carga de datos de programación le permite realizar un seguimiento de los datos del número de espectadores de los programas individuales que se emitieron durante el tiempo designado en el archivo de carga. Incluso puede recopilar datos del número de espectadores de temas específicos o segmentos de programa.</p><p>Estas funciones están disponibles independientemente de cómo haya implementado la recopilación de medios de streaming.</p><p>Anteriormente, era difícil vincular con precisión una sesión determinada a programas específicos cuando se analizaba contenido en directo, y no era posible vincular una sesión determinada a temas o segmentos de programa individuales.</p><p>Para obtener más información, consulte [Cargar datos de programación para realizar un seguimiento del contenido en directo](https://experienceleague.adobe.com/es/docs/media-analytics/using/media-use-cases/track-schedule-data) | 29 de octubre de 2025 | Por determinar<p>(Originalmente planificado para el 29 de octubre de 2025)</p> |


>[!MORELIKETHIS]
>
>* [Notas de la versión anteriores de 2026](/help/release-notes/2026.md)
>* [Notas de la versión de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=es)
>* [Notas de la versión de los servicios de medios de streaming](https://experienceleague.adobe.com/es/docs/media-analytics/using/release-notes/release-notes)
>* Últimas actualizaciones de la versión para [productos de Adobe CX Enterprise](https://business.adobe.com/es/products/adobe-experience-cloud-products.html)


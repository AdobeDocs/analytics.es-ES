---
title: Notas de la versión de Adobe Analytics actual
description: Ver las notas de la versión actuales de Adobe Analytics
feature: Release Notes
hold: true
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
TQID: 'https://experienceleague.adobe.com/yw30Yij2NBaeuWFqxD4-VH1Hysf8dxOpxHUwsFCYEw8'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
  - id: a421fb65-2c82-457a-921c-28c46b697a39
subfeature_v2:
  - id: d89ba969-e026-48bf-927e-e9df2f1e34f3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 6dd4e1e089cf72c03c8d2fd43ac87e919efa0602
workflow-type: tm+mt
source-wordcount: 1061
ht-degree: 49%

---

# Notas de la versión actuales de Adobe Analytics (septiembre de 2026)

**Última actualización**: 8 de septiembre de 2026

Estas notas de la versión abarcan el periodo de lanzamiento de septiembre de 2026. Las versiones de Adobe Analytics funcionan con un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funcionalidades. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Nuevas funciones o mejoras {#features}

| Función y descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ---- |
| **Limitar segmentos al intervalo de fechas del informe**<br/> Los datos de un informe de Workspace pueden extenderse más allá del intervalo de fechas del informe cuando un segmento incluye componentes de intervalo de fechas.<p>Ahora hay disponible una nueva opción que le permite limitar los resultados al intervalo de fechas de la creación de informes independientemente de cualquier componente de fecha incluido en el segmento.</p><p>Esta opción está disponible al crear o modificar un segmento cuyo contenedor de nivel superior sea Visitante.</p><p>Para obtener más información, consulte [Generar segmentos](/help/components/segmentation/segmentation-workflow/seg-build.md#components).</p> | 26 de agosto de 2026 | 9 de septiembre de 2026 |
| **Actualizaciones de detección de bots**<br/> Al utilizar la recopilación de datos de Edge con Web SDK, están disponibles las siguientes actualizaciones de detección de bots:<ul><li>Ahora puede crear reglas de detección de bots para identificar excepciones en el tráfico que, de lo contrario, se tratarían como generadas por bots. Las reglas existentes y futuras seguirán marcando de forma predeterminada el tráfico coincidente como generado por el bot.</li><li>Las reglas de bots personalizadas ahora se ejecutan antes que las reglas de detección de bots de IAB. Este cambio no afecta a las puntuaciones de bots, pero los nombres de reglas de bots asociados a un evento pueden cambiar.</li></ul><p>Nota: Esta actualización solo se aplica a las implementaciones de recopilación de datos de Edge que utilizan Web SDK. No se aplica a bibliotecas antiguas, como AppMeasurement.</p><p>(Vínculo a la documentación a continuación).</p> | | Principios de septiembre de 2026 |
| **Actualizaciones de API de conjuntos de clasificaciones**<br/> La documentación de API de conjuntos de clasificaciones ahora incluye información actualizada sobre parámetros y puntos de conexión para configurar solicitudes de API de conjuntos de clasificaciones.<p>Para obtener más información, consulte la [Guía de extremo de clasificaciones](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/classifications/).</p> | 5 de septiembre de 2026 | 30 de septiembre de 2026 |
| **Directrices de codificación de ItemId de fecha en las guías de informes de la API 2.0**<br/> Las guías de informes de tendencias de fecha de la API Adobe Analytics 2.0 ahora incluyen nuevas secciones que explican cómo se codifican los parámetros y valores de fecha `itemId`. Esto puede ayudarle a configurar y migrar a los servicios de API 2.0 desde las API 1.4, ahora obsoletas.<p>Para obtener más información, consulte la [guía de informes KPI](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/kpi) y la [guía de informes avanzados](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/advanced).</p> | 5 de septiembre de 2026 | 30 de septiembre de 2026 |

### Correcciones en Adobe Analytics

**Activity Map**: AN-488579, AN-487247
**Analysis Workspace**: AN-487374, AN-487119, AN-468907, AN-468810, AN-468363, AN-468096, AN-467414, AN-466986, AN-466982, AN-465073, AN-463571, AN-462373
**Clasificaciones**: AN-490825, AN-490802, AN-490549, AN-490472, AN-487782, AN-487286, AN-486531, AN-478859, AN-469929, AN-469033, AN-468944, AN-468827, AN-468326, AN-468592, AN-467115, AN-466995, AN-465636, AN-465616, AN-465380, AN-464911, AN-464338, AN-463677, AN-462729, AN-462577, AN-461040, AN-459316, AN-, AN-, AN-, AN-, AN-
**Fuentes de datos y Data Warehouse**: AN-487624, AN-487287, AN-479923, AN-479166, AN-479109, AN-468483
**Migración**:
**Exportaciones**: AN-467131
**Report Builder**: AN-487486, AN-478944, AN-470036, AN-468589, AN-468436, AN-456747, AN-456700, AN-442695
**Informes**: AN-468621, AN-465383, AN-463924
**Grupos de informes**: AN-468484, AN-468460, AN-465385
**Informes programados**:
**Segmentación**: AN-486561
**Otros**: AN-488549, AN-467426, AN-465265, AN-464645, AN-459714, AN-459323, AN-454514

### Avisos de final de la vida útil {#eol}

| Final de la vida útil de producto o función | Fecha de incorporación o actualización | Descripción |
| --- | --- | --- |
| **Report Builder heredado** | 18 de junio de 2025 | El complemento heredado de Report Builder se eliminará en junio de 2026. Todos los usuarios deberían empezar a actualizar sus libros heredados al [nuevo Report Builder](/help/analyze/report-builder/rb-overview.md). El nuevo Report Builder está disponible para los clientes de Adobe Analytics y Customer Journey Analytics. Tiene [casi paridad de características](/help/analyze/report-builder/convert-workbooks.md#unsupported), además de muchas nuevas características convenientes y mejoras en la interfaz de usuario. Para facilitar el proceso de actualización, el nuevo Report Builder incluye una sencilla función de conversión de libros. El nuevo Report Builder solo está disponible como complemento en Microsoft Store. Muchas organizaciones requieren un proceso de aprobación interno para poder poner el complemento a disposición de los usuarios. Deje tiempo para este proceso y empiece a trabajar con su organización ahora para asegurarse de que dispone de tiempo suficiente para actualizar los libros antes de la fecha límite. |
| **API de Adobe Analytics (versión 1.4)** | 17 de julio de 2024 | El **31 de agosto de 2026**, los siguientes servicios de la API heredada de Analytics llegaron al final de su vida útil y se cerraron, y todas las integraciones creadas con estos servicios ya no funcionan:<ul><li>API de Adobe Analytics (versión 1.4)</li><li>Autenticación WSSE de Adobe Analytics</li></ul><p>Las integraciones que usan la API de Adobe Analytics (versión 1.4) deben migrarse a la [API de Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/), mientras que las integraciones de WSSE deben migrarse a un protocolo de autenticación basado en OAuth en [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Consulte las [preguntas frecuentes sobre el final de la vida útil de la API de Adobe Analytics 1.4](https://developer.adobe.com/analytics-apis/docs/1.4/guides/eol/) para obtener respuestas a dudas comunes y más indicaciones.</p> |

## AppMeasurement

Para obtener las últimas actualizaciones de las versiones de AppMeasurement, consulte las [notas de la versión de AppMeasurement](https://github.com/adobe/appmeasurement/releases).

## Funciones aplazadas

| Función y descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| -----------|-----------|-----------|
| **Servicios de medios de streaming: compatibilidad con los datos programados** <br/>Ahora puede cargar datos programados de contenido de medios de streaming transmitidos en directo en el pasado para realizar un seguimiento más fácil y preciso del número de espectadores.<p>Los siguientes son ejemplos de contenidos en directo compatibles con la carga de datos de programación:</p><ul><li>Plataformas FAST (Free Ad Supported TV)</li><li>Streams locales</li><li>Deportes en directo</li></ul><p>La carga de datos de programación le permite realizar un seguimiento de los datos del número de espectadores de los programas individuales que se emitieron durante el tiempo designado en el archivo de carga. Incluso puede recopilar datos del número de espectadores de temas específicos o segmentos de programa.</p><p>Estas funciones están disponibles independientemente de cómo haya implementado la recopilación de medios de streaming.</p><p>Anteriormente, era difícil vincular con precisión una sesión determinada a programas específicos cuando se analizaba contenido en directo, y no era posible vincular una sesión determinada a temas o segmentos de programa individuales.</p><p>Para obtener más información, consulte [Cargar datos de programación para rastrear contenido en vivo](https://experienceleague.adobe.com/es/docs/media-analytics/using/media-use-cases/track-schedule-data). | 29 de octubre de 2025 | Por determinar<p>(Originalmente planificado para el 29 de octubre de 2025)</p> |


>[!MORELIKETHIS]
>
>* [Notas de la versión anteriores de 2026](/help/release-notes/2026.md)
>* [Notas de la versión de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=es)
>* [Notas de la versión de los servicios de medios de streaming](https://experienceleague.adobe.com/es/docs/media-analytics/using/release-notes/release-notes)
>* Últimas actualizaciones de la versión para [productos de Adobe CX Enterprise](https://business.adobe.com/es/products/adobe-experience-cloud-products.html)


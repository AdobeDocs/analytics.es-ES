---
title: Notas de la versión de Adobe Analytics actual
description: Ver las notas de la versión actuales de Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 4ed79fc004e27007e4591af3d0ee14ccfb0c0582
workflow-type: tm+mt
source-wordcount: '1287'
ht-degree: 52%

---

# Notas de la versión actuales de Adobe Analytics (marzo de 2026)

**Última actualización**: jueves, 11 de marzo de 2026

Estas notas de la versión abarcan el periodo de lanzamiento de marzo de 2026. Las versiones de Adobe Analytics funcionan con un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funcionalidades. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Nuevas funciones o mejoras {#features}

| Función y descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ---- |
| **Ordenar tablas por varias columnas** <br/>Ahora puede ordenar los datos de una tabla de forma libre por varias columnas en Analysis Workspace, ya sean dimensiones o métricas.<p>Al ordenar los datos de varias columnas, los datos se ordenan según la prioridad asignada a cada columna. La numeración de prioridad se muestra junto al icono de ordenación.</p><p>Para obtener más información, consulte [Filtrar y ordenar tablas de forma libre](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).</p> | jueves, 28 de enero de 2026 | jueves, 04 de marzo de 2026 <p>(Originalmente planificado para el 18 de febrero de 2026)</p> |
| **Report Builder: visibilidad del administrador para todos los libros programados**<br/> El complemento de Report Builder Excel incluye una nueva opción de filtro que permite a los administradores ver todos los libros programados para una organización determinada, independientemente de quién los programó. Esta opción de filtro solo está disponible para administradores de Analytics. Está disponible tanto en la pestaña Libro como en la pestaña Heredado al ver libros programados.<p>La capacidad de ver todos los libros programados resulta especialmente útil a la hora de migrar libros entre equipos distribuidos, ya que permite a los administradores localizar fácilmente todos los libros heredados antes de migrarlos.</p><p>Anteriormente, los administradores solo podían ver los libros que programaban, no los programados por otros usuarios.</p><p>Para obtener más información, vea [Libros programados administrados](/help/analyze/report-builder/manage-schedules-reportbuilder.md).</p> | | miércoles, 10 de marzo de 2026 |
| **Actualizar a la función Recuento distinto aproximado**<br/> El algoritmo probabilístico HLL utilizado en la función Recuento distinto aproximado se actualizará pronto. La salida resultante para números que utilizan esta función puede cambiar ligeramente con respecto a los números históricos, de la siguiente manera:</p><ul><li>Al contar cantidades muy pequeñas de valores únicos, los resultados se mejorarán para utilizar recuentos exactos en lugar de utilizar estimaciones.</li><li>Al contar cualquier cosa más grande, las estimaciones de recuento conservarán la misma precisión que antes de esta actualización (las estimaciones son precisas dentro del 5 por ciento del número exacto, el 95 por ciento del tiempo).</li></ul><p>Para obtener más información sobre la función Approximate Count Distinct, vea [Approximate Count Distinct](/help/components/calculated-metrics/cm-reference/cm-adv-functions.md#approximate-count-distinct) en [Funciones avanzadas](/help/components/calculated-metrics/cm-reference/cm-adv-functions.md)</p> | | miércoles, 10 de marzo de 2026 |
| **Tutorial práctico para Analysis Workspace**<br/> Ahora hay disponible un nuevo tutorial práctico para guiar a los nuevos usuarios a través de los conceptos básicos del uso de paneles, visualizaciones y componentes en Analysis Workspace. <p>(Vínculo a la documentación a continuación).<!--For more information, see "Learning paths" in "Customer Journey Analytics landing page".--></p> | | jueves, 18 de marzo de 2026 |
| **Aplicar un desglose a un panel**<br/> Ahora puede aplicar un desglose a un panel. Al aplicar un desglose en el nivel de panel, el desglose se aplica a todas las columnas de todas las tablas de forma libre dentro del panel. | Marzo de 2026 | Mayo de 2026 |
| **Servicios de medios de streaming: datos de programación de soporte** <br/>Ahora puede cargar datos programados de contenido de medios de streaming en vivo anteriores para rastrear la audiencia de manera más fácil y precisa.<p>Los siguientes son ejemplos de contenidos en directo compatibles con la carga de datos de programación:</p><ul><li>Plataformas FAST (Free Ad Supported TV)</li><li>Streams locales</li><li>Deportes en directo</li></ul><p>La carga de datos de programación le permite realizar un seguimiento de los datos del número de espectadores de los programas individuales que se emitieron durante el tiempo designado en el archivo de carga. Incluso puede recopilar datos del número de espectadores de temas específicos o segmentos de programa.</p><p>Estas funciones están disponibles independientemente de cómo haya implementado la recopilación de medios de streaming.</p><p>Anteriormente, era difícil vincular con precisión una sesión determinada a programas específicos cuando se analizaba contenido en directo, y no era posible vincular una sesión determinada a temas o segmentos de programa individuales.</p><p>Para obtener más información, consulte [Cargar datos de programación para realizar un seguimiento del contenido en directo](https://experienceleague.adobe.com/es/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 29 de octubre de 2025 | Primer semestre de 2026<p>(Originalmente planificado para su lanzamiento el 29 de octubre de 2025)</p> |

## Correcciones en Adobe Analytics

**Activity Map**:
**Analysis Workspace**: AN-440336, AN-440216, AN-440121, AN-438445, AN-438216, AN-437856, AN-437776, AN-437765, AN-437365, AN-432793, AN-432094, AN-431557, AN-431200, AN-429621, AN-429424, AN-427973, AN-426089, AN-425883, AN-424359
**Clasificaciones**: AN-440143, AN-439891, AN-439844, AN-438994, AN-438057, AN-438052, AN-437986, AN-437896, AN-435387, AN-435335, AN-435150, AN-433050, AN-432062, AN-431873, AN-429642
**Fuentes de datos y Data Warehouse**: AN-439441, AN-437086, AN-433064, AN-432121, AN-431755, AN-428239, AN-427049, AN-425036, AN-424972, AN-423509, AN-335417, AN-283958, AN-256948
**Migración**:
**Exportaciones**: AN-432030
**Report Builder**: AN-437895, AN-437083, AN-434288, AN-434209, AN-433224, AN-430622
**Informes**: AN-434545, AN-431206, AN-428043
**Informes programados**:
**Segmentación**:
**Otros**: AN-440076, AN-434783, AN-434542, AN-434233, AN-433368, AN-432138, AN-431322, AN-431012, AN-429067, AN-423285


## Avisos de final de la vida útil {#eol}

| Final de la vida útil de producto o función | Fecha de incorporación o actualización | Descripción |
| --- | --- | --- |
| **Mejoras en el procesamiento de Livestream** | jueves, 14 de enero de 2026 | Adobe planea realizar mejoras y cambios en el formato de las cargas útiles de LiveStream. Estas actualizaciones proporcionan una mejor paridad entre LiveStream y otras funciones de Adobe Analytics, como Analysis Workspace. Hay disponible un punto final de previsualización que le permite probar los cambios planeados. Consulte [Notas de la versión de LiveStream](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/release-notes/) para ver la lista completa de cambios y los detalles del punto final de previsualización. Adobe planea una transición definitiva al formato de carga útil actualizado el 13 de abril de 2026. |
| **Eliminación de grupos de cifrado TLS 1.2** | jueves, 11 de febrero de 2026 | Aviso a los administradores: Adobe planea eliminar la compatibilidad con los siguientes grupos de cifrados TLS 1.2 de los servidores de recopilación de datos de Adobe el 27 de mayo de 2026.<ul><li>`TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_256_CBC_SHA`</li></ul><p>No se requiere ninguna acción del cliente para la mayoría de las implementaciones. Este cambio afecta principalmente a los datos de Analytics enviados desde aplicaciones nativas heredadas que utilizan bibliotecas TLS obsoletas, y a un pequeño número de visitantes web en navegadores o sistemas operativos obsoletos. Al eliminar la compatibilidad con estos grupos de cifrado, se mejora la seguridad y se alinea Adobe con los estándares de cifrado modernos. Actualmente, menos del 0,1 % del tráfico de recopilación de datos depende de estos grupos de cifrado.</p> |
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

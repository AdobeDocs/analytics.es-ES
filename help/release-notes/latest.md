---
title: Notas de la versión de Adobe Analytics actual
description: Ver las notas de la versión actuales de Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 69aa42b1949944b59740222073635be72c4bd6ab
workflow-type: tm+mt
source-wordcount: '1225'
ht-degree: 49%

---

# Notas de la versión actuales de Adobe Analytics (enero de 2026)

**Última actualización**: jueves, 14 de enero de 2026

Estas notas de la versión abarcan el periodo de lanzamiento de enero de 2026. Las versiones de Adobe Analytics funcionan con un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funcionalidades. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Nuevas funciones o mejoras {#features}

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Generador de reglas de conjuntos de clasificaciones** | La funcionalidad del generador de reglas ya está disponible en los conjuntos de clasificaciones. Las reglas se definen en el contexto de un conjunto de clasificaciones. Las reglas se aplican (cuando se activan) a todos los grupos de informes y a las combinaciones de dimensiones clave suscritas al conjunto de clasificaciones.<p>(Vínculo a la documentación a continuación).</p> |  | sábado, 30 de enero de 2026 |
| **Fuentes de datos mejoradas** | Las siguientes mejoras ya están disponibles para las fuentes de datos:<ul><li>Experiencia del usuario mejorada.</li><li>Nueva experiencia para crear y administrar plantillas de columna.</li><li>Ahora puede elegir cuándo crear una plantilla de columna para reutilizarla en futuras fuentes de datos. También puede eliminar, editar y copiar plantillas.<br/>Anteriormente, cada fuente de datos creada tenía como resultado una nueva plantilla de columna, lo que generaba un gran número de plantillas de columna no utilizadas y ninguna forma de eliminarlas o administrarlas.</li><li>Añadir y filtrar por etiquetas.</li><li>Ver el historial de los trabajos de fuentes de datos. (Cuando comenzó el período de solicitud, cuando comenzó, terminó, etc.).</li><li>Reenviar o volver a procesar fuentes de datos. (Desde la página Historial de trabajos)</li><li>Permitir visitas que lleguen tarde. Ahora puede incluir datos que llegaron después de que el trabajo de fuente de datos terminara de procesar los datos dentro de la frecuencia de sistema de informes establecida.</li><li>Al elegir una fecha de finalización para una fuente de datos, la fecha de finalización que elija se incluye como el último día de la fuente de datos.<br/>Anteriormente, la fecha de finalización se excluía de la fuente de datos.</li><li>Ahora es posible exportar la frecuencia en 15 minutos, pero no está disponible de forma predeterminada. Para que esta opción esté disponible en su entorno, primero debe ponerse en contacto con el Servicio de atención al cliente de Adobe y solicitar que el grupo de informes esté configurado para admitir exportaciones de 15 minutos.</li></ul><p>**Nota:** Con estas mejoras, las direcciones URL de las páginas de fuentes de datos en Adobe Analytics también se están actualizando. Actualice los marcadores existentes para que apunten a las nuevas páginas de fuentes de datos antes del 30 de abril de 2026.</p>(Vínculo a la documentación a continuación).</p> | miércoles, 20 de enero de 2026 | miércoles, 10 de febrero de 2026 |
| **Ordenar tablas por varias columnas** | Ahora puede ordenar los datos de una tabla de forma libre por varias columnas en Analysis Workspace, ya sean dimensiones o métricas.<p>Al ordenar los datos de varias columnas, los datos se ordenan según la prioridad asignada a cada columna. La numeración de prioridad se muestra junto al icono de ordenación.</p><p>(Vínculo a la documentación a continuación).<!-- For more information, see "Filter and sort freeform tables". (need to move info to this article from "Include multiple dimension columns in a freeform table") --></p> | jueves, 28 de enero de 2026 | jueves, 18 de febrero de 2026 |
| **Servicios de medios de streaming: compatibilidad con datos de programación** | Ahora puede cargar datos programados de contenidos anteriores de medios de streaming en directo para realizar un seguimiento más fácil y preciso del número de espectadores.<p>Los siguientes son ejemplos de contenidos en directo compatibles con la carga de datos de programación:</p><ul><li>Plataformas FAST (Free Ad Supported TV)</li><li>Streams locales</li><li>Deportes en directo</li></ul><p>La carga de datos de programación le permite realizar un seguimiento de los datos del número de espectadores de los programas individuales que se emitieron durante el tiempo designado en el archivo de carga. Incluso puede recopilar datos del número de espectadores de temas específicos o segmentos de programa.</p><p>Estas funciones están disponibles independientemente de cómo haya implementado la recopilación de medios de streaming.</p><p>Anteriormente, era difícil vincular con precisión una sesión determinada a programas específicos cuando se analizaba contenido en directo, y no era posible vincular una sesión determinada a temas o segmentos de programa individuales.</p><p>Para obtener más información, consulte [Cargar datos de programación para realizar un seguimiento del contenido en directo](https://experienceleague.adobe.com/es/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 29 de octubre de 2025 | Primer semestre de 2026<p>(Originalmente planificado para su lanzamiento el 29 de octubre de 2025)</p> |

## Correcciones en Adobe Analytics

**Activity Map**:
**Analysis Workspace**: AN-423389, AN-422636, AN-422482, AN-422027, AN-421134, AN-420187, AN-406271, AN-406188, AN-405997, AN-405983, AN-405033, AN-405796, AN-404893, AN-404842, AN-404713, AN-404502, AN-404353, AN-404352, AN-404871, AN-404048, AN-402523, AN-396149, AN-390990, AN-390728, AN-390646, AN-383484, AN-376980, AN-371729, AN-347570, AN-, AN-, AN-, AN-, AN-, AN--, AN, AN-, AN-, AN--, AN-------, Y--, Y----, Y-----, Y-, Y-, Y-, Y, Y--, Y, Y-, Y-, Y-, Y-, Y-, Y-, Y, Y-, Y-, Y-, Y-, Y-, Y-, Y-, Y-, Y-, Y-, Y-
**Clasificaciones**: AN-423985, AN-423092, AN-423067, AN-422913, AN-422908, AN-422793, AN-422785, AN-422745, AN-422705, AN-422422, AN-422126, AN-422098, AN-422077, AN-422058, AN-421999, AN-421698, AN-421351, AN-406583, AN-406295, AN-406123, AN-406052, AN-404743, AN-404372, AN-, AN-, AN-, AN-, AN-, AN-, AN-, AN-, AN-
**Recopilación de datos**: AN-422488
**Fuentes de datos y Data Warehouse**: AN-423186, AN-422789, AN-422239, AN-421552, AN-421393, AN-421339, AN-421231, AN-420149, AN-406345, AN-406217, AN-405073, AN-404822, AN-404774, AN-389691
**Privacidad**:
**Report Builder**: AN-422120, AN-421937, AN-406296, AN-402951, AN-399748
**Informes**:
**Informes programados**: AN-423087, AN-422686
**Comparación de segmentos**:
**Otros**: AN-423401, AN-422819, AN-422775, AN-422626, AN-422238, AN-422160, AN-422071, AN-421687, AN-420045, AN-404891, AN-404608, AN-390912


## Avisos de final de la vida útil {#eol}

| Final de la vida útil de producto o función | Fecha de incorporación o actualización | Descripción |
| --- | --- | --- |
| **Mejoras en el procesamiento de Livestream** | jueves, 14 de enero de 2026 | Adobe planea realizar mejoras y cambios en el formato de las cargas útiles de LiveStream. Estas actualizaciones proporcionan una mejor paridad entre LiveStream y otras funciones de Adobe Analytics, como Analysis Workspace. Hay disponible un punto final de vista previa que le permite probar los cambios planeados. Consulte [Notas de la versión de LiveStream] para ver la lista completa de cambios y los detalles del punto final de vista previa. Adobe planea una migración brusca al formato de carga útil actualizado el 13 de abril de 2026. |
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

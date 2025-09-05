---
title: Notas de la versión de Adobe Analytics actual
description: Ver las notas de la versión actuales de Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: fcc165536d77284e002cb2ba6b7856be1fdb3e14
workflow-type: tm+mt
source-wordcount: '1145'
ht-degree: 100%

---

# Notas de la versión actual de Adobe Analytics (versión de agosto de 2025)

**Última actualización**: jueves, 13 de agosto de 2025

Estas notas de la versión abarcan el periodo de lanzamiento del 13 de agosto al 16 de septiembre de 2025. Las versiones de Adobe Analytics funcionan con un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funcionalidades. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Nuevas funciones o mejoras {#features}

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Analizar el tráfico de IA con un nuevo elemento de dimensión Tipo de referente** | En octubre, habrá disponible un nuevo elemento de dimensión Tipo de referente para ayudar a analizar el tráfico proveniente de las herramientas de IA. <p>Este nuevo elemento de dimensión Tipo de referente, denominado Herramientas de IA conversacional, agrupará los dominios de referencia de las principales herramientas de IA, lo que le permitirá observar las tendencias del grupo en su conjunto. La lista inicial de dominios de referencia en esta nueva categoría incluye (entre otros):</p><ul><li>chatgpt.com</li><li>claude.ai</li><li>m365.cloud.microsoft</li><li>grok.com</li><li>gemini.google.com</li><li>perplejidad.ai</li></ul><p>El nuevo elemento de dimensión estará disponible en todas las herramientas relacionadas con Adobe Analytics, incluidas Analysis Workspace, Report Builder, Data Warehouse, fuentes de datos, etc.</p><p>Tenga en cuenta lo siguiente al utilizar este nuevo elemento de dimensión:</p><ul><li>No siempre es posible distinguir el tráfico de referente proveniente de los resultados proporcionados en &quot;modo IA&quot; en un motor de búsqueda frente a aquellos que proceden de clics de resultados de búsqueda tradicionales.</li><li>El nuevo elemento de dimensión Herramientas de inteligencia artificial conversacional se centra en los proveedores principales con la mayor cantidad de tráfico. Una nueva tendencia revela un número creciente de sitios de suplantadores con dominios similares a los principales proveedores de herramientas de IA. Esto probablemente se deba a la facilidad con la que las personas o los grupos pueden crear sus propias herramientas de IA y alojarlas en Internet. Dado que este es un espacio de rápida evolución, póngase en contacto con el equipo de asistencia de Adobe si descubre que no se incluye un sitio popular.</li><li>La dimensión Tipo de referente, incluido el nuevo elemento de dimensión Herramientas de IA conversacional, solo está disponible para los datos que procesa Adobe Analytics. </li></ul><p>(Vínculo a la documentación a continuación).</p> |   | Octubre de 2025 |
| **Los proyectos descargados en formato PDF se descargan en su estación de trabajo** | Al descargar un proyecto en formato PDF, este se descarga en la carpeta de descargas de la estación de trabajo.  <p>Anteriormente, al descargar un proyecto en formato PDF, este se abría en una nueva pestaña del explorador con una dirección URL única. </p><p>Para obtener más información, consulte [Descargar proyectos y datos](/help/analyze/analysis-workspace/curate-share/download-send.md)</p> |  | martes, 25 de agosto de 2025 |
| **Los proyectos eliminados dejan de estar disponibles mediante URL de inmediato y se eliminan de las entregas programadas** | Los proyectos eliminados se eliminan inmediatamente de las entregas programadas y ya no son accesibles mediante su dirección URL.<p>Anteriormente, los proyectos se incluían en envíos programados y se podía acceder a ellos con su dirección URL durante 60 días después de eliminarse.</p><p>Para obtener más información sobre cómo eliminar proyectos, consulte [Descripción general de proyectos](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md).</p> | | Finales de agosto de 2025 |
| **Servicios de medios de streaming: campos XDM actualizados para recopilar datos de medios de streaming en Adobe Experience Platform** | Al recopilar datos de medios de streaming en Adobe Experience Platform, ya no se deben utilizar las rutas de campo XDM que se muestran en el encabezado de “Ruta de campo XDM” de la documentación de parámetros de medios de streaming. En su lugar, los clientes que implementaron el conector de origen de Analytics para recopilar datos de medios de streaming en Platform antes del 9 de mayo de 2025 deben migrar sus configuraciones existentes a las rutas de campo de creación de informes de medios, como se muestra en el encabezado “Ruta de campo XDM de creación de informes” de la documentación de parámetros de medios de streaming.<p> Estas rutas de campo se encuentran en las páginas siguientes y están marcadas como &quot;Obsoletas&quot;: [Parámetros de audio y vídeo](https://experienceleague.adobe.com/es/docs/media-analytics/using/implementation/variables/audio-video-parameters), [Parámetros de anuncios](https://experienceleague.adobe.com/es/docs/media-analytics/using/implementation/variables/ad-parameters), [Parámetros de capítulos](https://experienceleague.adobe.com/es/docs/media-analytics/using/implementation/variables/chapter-parameters), [Parámetros de estado del reproductor](https://experienceleague.adobe.com/es/docs/media-analytics/using/implementation/variables/player-state-parameters) y [Parámetros de calidad](https://experienceleague.adobe.com/es/docs/media-analytics/using/implementation/variables/quality-parameters). (No se requiere ninguna acción para los clientes que implementan el conector de origen de Analytics después del 9 de mayo de 2025 y que ya solo utilizan rutas XDM de creación de informes de medios).</p><p>La ingesta de datos en las rutas de campo XDM obsoletas seguirá hasta finales de octubre de 2025. Después de ese tiempo, las rutas de campo obsoletas se eliminarán por completo y ya no serán visibles en la interfaz de usuario de Adobe Experience Platform Schema, y los datos solo se enviarán utilizando las rutas de campo mediaReporting.</p><p>Para obtener más información, consulte [Migrar una implementación del conector de origen de Analytics a campos actualizados de medios de streaming XDM](https://experienceleague.adobe.com/es/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields).</p><p>Póngase en contacto con los servicios de Adobe Consulting o con el equipo de la cuenta para obtener ayuda sobre la migración.  </p> |  | Octubre de 2025 |

## Correcciones en Adobe Analytics

**Activity Map**: AN-389205; AN-384186
**Analysis Workspace**: AN-390102; AN-389066; AN-388841; AN-388687; AN-388478; AN-387089; AN-387044; AN-384560; AN-379213; AN-351639
**Clasificaciones**: AN-390442; AN-390385; AN-389953; AN-389703; AN-389321; AN-389116; AN-388833; AN-388717; AN-387987; AN-383329
**Recopilación de datos**: AN-389320
**Fuentes de datos y Data Warehouse**: AN-389702; AN-388136; AN-387779; AN-384369; AN-383075; AN-380307
**Privacidad**:
**Report Builder**: AN-389336; AN-382775
**Informes**: AN-390398
**Informes programados**:
**Comparación de segmentos**:
**Otros**: AN-388180; AN-383164; AN-366532


## Avisos de final de la vida útil {#eol}

| Final de la vida útil de producto o función | Fecha de incorporación o actualización | Descripción |
| --- | --- | --- |
| **Report Builder heredado** | 18 de junio de 2025 | El complemento heredado de Report Builder se eliminará en junio de 2026. Todos los usuarios deberían empezar a actualizar sus libros heredados al [nuevo Report Builder](/help/analyze/report-builder/rb-overview.md). El nuevo Report Builder está disponible para los clientes de Adobe Analytics y Customer Journey Analytics. Tiene [casi paridad de características](/help/analyze/report-builder/convert-workbooks.md#unsupported), además de muchas nuevas características convenientes y mejoras en la interfaz de usuario. Para facilitar el proceso de actualización, el nuevo Report Builder incluye una sencilla función de conversión de libros. El nuevo Report Builder solo está disponible como complemento en Microsoft Store. Muchas organizaciones requieren un proceso de aprobación interno para poder poner el complemento a disposición de los usuarios. Deje tiempo para este proceso y empiece a trabajar con su organización ahora para asegurarse de que dispone de tiempo suficiente para actualizar los libros antes de la fecha límite. |
| **Acceso a través de dominios heredados o a través de SSO heredado** | 10 de abril de 2025 | Adobe tiene previsto actualizar el modo en que los usuarios acceden a Adobe Analytics para mejorar la seguridad y optimizar el inicio de sesión. Como parte de este esfuerzo, el acceso a través de dominios heredados o a través del SSO heredado, incluido `my.omniture.com`, se suspenderá permanentemente el **2 de enero de 2026**. Después de esta fecha, las credenciales de inicio de sesión heredadas y el SSO heredado dejarán de funcionar. Se solicitará a todos los usuarios que inicien sesión a través de `experience.adobe.com` mediante sus ID de Adobe Experience. Si necesita ayuda con relación a su ID de Experience Cloud, póngase en contacto con el administrador de Adobe Analytics de su organización o con el [Servicio de atención al cliente de Adobe](https://helpx.adobe.com/es/contact.html?lang=es). |
| **API de Adobe Analytics (versión 1.4)** | 17 de julio de 2024 | El **12 de agosto de 2026**, los siguientes servicios de la API heredada de Analytics llegarán al final de su vida útil y se cerrarán, y las integraciones actuales creadas con estos servicios dejarán de funcionar:<ul><li>API de Adobe Analytics (versión 1.4)</li><li>Autenticación WSSE de Adobe Analytics</li></ul><p>Las integraciones que usan la API de Adobe Analytics (versión 1.4) deben migrarse a la [API de Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/), mientras que las integraciones de WSSE deben migrarse a un protocolo de autenticación basado en OAuth en [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Consulte las [preguntas frecuentes sobre el final de la vida útil de la API de Adobe Analytics 1.4](/help/admin/c-admin-api/c-admin-14-api-eol.md) para obtener respuestas a dudas comunes y más indicaciones.</p> |


## AppMeasurement

Para obtener las últimas actualizaciones de las versiones de AppMeasurement, consulte las [notas de la versión de AppMeasurement](https://github.com/adobe/appmeasurement/releases).


## Recursos relacionados

* [Notas de la versión anteriores de 2025](/help/release-notes/2025.md)
* [Notas de la versión de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=es)
* [Notas de la versión de los servicios de medios de streaming](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
* Las últimas actualizaciones de la versión para los [productos de Adobe Experience Cloud](https://business.adobe.com/products/adobe-experience-cloud-products.html?lang=es)

---
title: Últimas notas de la versión de Analytics
description: Vea las notas de la versión actuales de Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: feb6942a54f61850ce11e08008b5694c53436e6d
workflow-type: tm+mt
source-wordcount: '1098'
ht-degree: 38%

---

# Notas de la versión de Adobe Analytics actual (Febrero de 2023)

**Última actualización**: 17 de febrero de 2023

Las versiones de Adobe Analytics funcionan con un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funcionalidades. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Funciones nuevas o actualizadas en Adobe Analytics

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Interfaz de usuario actualizada para etiquetas de privacidad de datos** | La interfaz actualizada optimiza el proceso de creación, administración y edición de etiquetas de privacidad de datos para los componentes del grupo de informes. [Más información](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/data-labels/gdpr-setup-reportsuite.html?lang=en) | N/A | 8 de febrero de 2023 |
| **Ocultar intervalos de fechas de comparación en informes de valoración móviles** | Con los informes de valoración móviles, puede alternar la variable **[!UICONTROL Incluir fechas de comparación]** configuración para ver u ocultar fechas de comparación. | N/A | 8 de febrero de 2023 |
| **Actualizaciones de calendario en Workspace** | <ul><li>Fechas del panel de anclaje: Puede hacer que los componentes del intervalo de fechas sean relativos al calendario del panel. [Más información](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md#relative-panel-dates)</li><li>Actualizaciones de estilo del calendario: Los estilos de calendario de toda la interfaz de usuario se han actualizado para presentar un flujo de trabajo más coherente y fácil de usar.</li><li>Actualizaciones de la fórmula del calendario: Si utiliza fechas relativas, todas las fórmulas del calendario reflejarán el inicio del intervalo de fechas del panel. [Más información](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md#formula-relative-dates)</li></ul> | N/A | 8 de febrero de 2023 |
| **Actualizaciones del intervalo de fechas del panel** | En Workspace, se han añadido las siguientes mejoras:<ul><li>A partir de la versión de febrero, las vistas previas de componentes y datos se basarán en el intervalo de fechas del panel y no en los últimos 90 días. </li><li>Todos los componentes enumerados en el carril izquierdo estarán disponibles en función del intervalo de fechas del panel.</li><li>Todas las vistas previas de fechas del segmento y los creadores de métricas calculadas se basarán en el intervalo de fechas del panel (a menos que se acceda desde los administradores de componentes, que no tienen un panel asociado, se basarán en los últimos 90 días).</li><li>Cualquier vista previa de datos mostrará datos o componentes en función del intervalo de fechas del panel.</li></ul> | N/A | 8 de febrero de 2023 |
| **Filtrado de filas y columnas para la transmisión por secuencias del conector de origen de Adobe Analytics** | El conector de origen de Analytics en Adobe Experience Platform ahora permite filtrar los datos de Analytics que se usan para rellenar perfiles en [Perfil del cliente en tiempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=es). El filtrado a nivel de fila ayuda a reducir el número de eventos asociados a perfiles. El filtrado a nivel de columna ayuda a reducir la riqueza de los propios eventos, lo que permite optimizar el uso de derechos de perfil. Este filtrado solo se aplica a los datos enviados al Perfil del cliente en tiempo real y [Servicio de identidad](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=es). **El filtrado no afecta a los datos que se envían a Data Lake para su uso en aplicaciones como Customer Journey Analytics**. [Más información](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en#filtering-for-profile) | N/A | 22 de febrero de 2023 |

{style=&quot;table-layout:auto&quot;}

## Correcciones en Adobe Analytics 

-302282; AN-303127; AN-303541; AN-303550; AN-305282; AN-306504; AN-307351; AN-307496; AN-307530; AN-307947; AN-308497; AN-; AN-308610; AN-308777; AN-308994; AN-309143; AN-309404; AN-309414; AN-309445; AN-309575; AN-309630; AN-309658; AN-309690; AN-309742; AN-309861; AN-309967; AN-309973; AN-310059; AN-310132; AN-310168; AN-310238; AN-310241; AN-310301; AN-310318; AN-310324; AN-310335; AN-310338; AN-310460; AN-310500; AN-310684; AN-310690; AN-311010; AN-311022; AN-311043; AN-311125; AN-311250; AN-311370; AN-311458;

## Avisos importantes para los administradores de Adobe Analytics

| Aviso | Fecha de incorporación  o actualizada | Descripción |
| ----------- | ---------- | ---------- |
| **Actualización de las búsquedas de dispositivos debido a las sugerencias del cliente de Google** | 17 de febrero de 2023 | **El uso de sugerencias de clientes, planeado para el 16 de febrero de 2023, se pospuso para garantizar la calidad de las búsquedas de dispositivos usando sugerencias. En breve comunicaremos una nueva fecha de lanzamiento.** [Más información](/help/technotes/client-hints.md) |
| **Disponibilidad del conector de origen de Analytics** | 15 de febrero de 2023 | El 28 de febrero de 2023, el conector de origen de Analytics estará disponible en el nuevo centro de datos de Adobe Experience Platform ubicado en Canadá. |
| **Migración automática a la arquitectura del conjunto de clasificaciones** | 8 de febrero de 2023 | En los próximos meses, el Adobe planea migrar todas las clasificaciones de todas las organizaciones a la arquitectura de clasificación más reciente. Se estima que los últimos clientes en migrar se producirán en mayo de 2023. No se requiere ninguna acción por parte del cliente y no se espera tiempo de inactividad. Esta nueva arquitectura tiene muchas ventajas, entre ellas:<ul><li>Reducción significativa del tiempo de procesamiento (72 horas → 24 horas)</li><li>La capacidad de usar la variable [Conjuntos de clasificaciones](/help/components/classifications/sets/overview.md) IU</li><li>La opción de usar datos de clasificación en Adobe Experience Platform en el futuro mediante el [Conector de origen de Adobe Analytics para datos de clasificación](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/classifications.html)</li></ul>Tenga en cuenta los siguientes cambios que pueden afectar potencialmente al flujo de trabajo de su organización:<ul><li>Al usar el explorador o la importación mediante FTP, &#39;[!UICONTROL Sobrescribir en conflicto]&#39; siempre está habilitado.</li><li>Al utilizar el explorador o la importación mediante FTP, ya no se admite la opción de exportar inmediatamente después de la importación.</li><li>La API de Analytics 2.0 `GetDimensions` ahora devuelve identificadores de cadena para clasificaciones en lugar de identificadores numéricos. Se pueden seguir utilizando identificadores numéricos, pero Adobe recomienda utilizar los nuevos identificadores de cadena siempre que sea posible. Los identificadores numéricos se pueden recuperar utilizando la variable `?expansion=hidden` parámetro de cadena de consulta.</li></ul>Póngase en contacto con el Servicio de atención al cliente de Adobe si desea un programa de migración más específico para su organización o si tiene preguntas o inquietudes acerca de esta migración. [Más información](/help/components/classifications/sets/overview.md) |

{style=&quot;table-layout:auto&quot;}

## Avisos de fin de vida útil (EOL)

| Final de la vida útil de producto o función | Fecha de incorporación o actualización | Descripción |
| --- | --- | --- |
| **Fin de la vida útil de algunas funciones de programación de Reports &amp; Analytics y Report Builder** | 9 de febrero de 2023 | Las siguientes funciones de programación finalizaron su vida útil el 31 de enero de 2023:<ul><li>La opción &quot;finalizar después de x ocurrencias&quot; para tareas por hora en el Report Builder</li><li>La capacidad de programar nuevos informes y descargar extractos de datos en Reports and Analytics</li></ul><p>**Nota**: Originalmente, terminamos estas funciones en abril de 2022, pero revirtimos el cambio. También enviamos una notificación de que estas funciones se estaban restaurando temporalmente y que se volverían a finalizar el 31 de enero de 2023. |
| **Funcionalidad del final de vida útil de las [!UICONTROL Listas de publicación]** | 29 de septiembre de 2022 | Como parte del final de la vida útil de Reports &amp; Analytics, las Listas de publicación están programadas para llegar al final de su vida útil en **diciembre de 2023**. No podrá crear Listas de publicaciones nuevas ni acceder a las existentes para enviar o programar proyectos de Analysis Workspace. |
| **Fin de la vida útil para Data Workbench** | 14 de septiembre de 2022 | Adobe tiene planeado el fin de la vida útil de Data Workbench con fecha de aplicación el **31 de diciembre de 2023**. Consulte [Anuncio del fin de la vida útil de Data Workbench](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=es) para obtener más información. Póngase en contacto con el Administrador de cuentas de Adobe de su organización si tiene alguna pregunta. |
| **EOL para [!DNL Reports & Analytics]** | 4 de enero de 2022 | A partir del **31 de diciembre de 2023**, Adobe tiene la intención de descatalogar [!DNL Reports & Analytics] y sus informes y funciones correspondientes. Los informes, las visualizaciones y la tecnología subyacente que alimentan [!DNL Reports & Analytics] ya no cumplen los estándares tecnológicos de Adobe. La mayoría de las funciones de [!DNL Reports & Analytics] están disponibles en [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=es). Desde el lanzamiento de Analysis Workspace en 2015, las funcionalidades y capacidades de [!DNL Reports & Analytics] se han trasladado a Analysis Workspace y se ha alcanzado un umbral de paridad de flujo de trabajo. [Este aviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) explica el proceso de finalización de la vida útil. |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement

Para obtener las últimas actualizaciones de las versiones de AppMeasurement (2.23.0), consulte las [notas de la versión de AppMeasurement para JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=es).


## Recursos relacionados

* [Notas de la versión anteriores de 2022](/help/release-notes/2022.md)
* [Notas de la versión de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=es)
* [Notas de la versión de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
* Las últimas actualizaciones de la versión para los [productos de Adobe Experience Cloud](https://business.adobe.com/es/products/adobe-experience-cloud-products.html)

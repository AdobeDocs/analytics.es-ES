---
title: Últimas notas de la versión de Analytics
description: Vea las notas de la versión actuales de Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 6d9b568a0ce9d0e8b25d04e934052d2f8012da8c
workflow-type: tm+mt
source-wordcount: '1538'
ht-degree: 62%

---

# Notas de la versión de Adobe Analytics actual (Abril de 2023)

**Última actualización**: 12 de abril de 2023

Las versiones de Adobe Analytics funcionan con un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funcionalidades. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Funciones nuevas o actualizadas en Adobe Analytics {#features}

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Filtrado de filas y columnas para el streaming del conector de origen de Analytics** | El conector de origen de Analytics en Adobe Experience Platform ahora permite filtrar los datos de Analytics que se usan para rellenar perfiles en el [Perfil del cliente en tiempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=es). El filtrado de nivel de fila reduce el número de eventos asociados a perfiles. El filtrado a nivel de columna ayuda a reducir la riqueza de los propios eventos, lo que permite optimizar el uso de derechos de perfil. Este filtrado solo se aplica a los datos enviados al perfil del cliente en tiempo real y al [Servicio de identidad](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=es). **El filtrado no afecta a los datos que se envían al lago de datos para su uso en aplicaciones como Customer Journey Analytics**. [Más información](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=es#filtering-for-profile) | N/A | 29 de marzo de 2023 |
| **Compatibilidad parcial con el Activity Map con el SDK web** | A partir de la versión 2.15.0 del SDK web, se empezaron a rellenar los datos del Activity Map cuando el seguimiento de vínculos está habilitado. Esto permite a los usuarios del SDK web obtener informes de Activity Map si tienen habilitado el seguimiento de vínculos con el SDK web y el Activity Map configurado en Analytics.<p>Al habilitar el seguimiento de vínculos con el SDK web, se envían eventos de vínculo cuando un cliente navega de una página a otra. Esto es diferente a cómo funciona AppMeasurement y puede resultar potencialmente en visitas facturables adicionales enviadas al Adobe. Más información [here](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html?lang=es) y [here](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md) | N/A | 31 de marzo de 2023 |
| **Confusión de IP para Experience Edge** | Experience Edge admitirá la confusión de IP para los datos enviados directamente a Adobe Experience Platform. Esto beneficia a los clientes que envían datos directamente a Platform para su uso en CJA u otras soluciones de Platform. La confusión de IP se configurará en el nivel de flujo de datos. Admite la eliminación del último octeto o de toda la dirección IP.<p>**Nota**: La confusión NO se aplica a los datos enviados a Adobe Analytics. Analytics sigue obteniendo la IP completa. El procesamiento de IP se sigue realizando en Analytics por separado. En el futuro, planeamos permitir que los datos de Analytics se confundan en Edge. | N/A | Versión de AEP del 26 de abril de 2023 |
| **Diccionario de datos en Analysis Workspace** | El diccionario de datos ayuda a los usuarios y a los administradores a realizar el seguimiento de los componentes (dimensiones, métricas) en el entorno de Analytics, a administrarlos y a comprenderlos mejor. [Más información](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) | 15 de marzo de 2023 | 29 de marzo de 2023 |
| **Uso compartido de vínculos para proyectos (no se requiere inicio de sesión)** - Solo acceso beta privado | <p>Ahora puede compartir vínculos de solo lectura a proyectos de Analysis Workspace con personas que no tienen acceso a Adobe Analytics. Puede compartir vínculos de proyectos con personas fuera de su organización o con personas de su organización que no estén aprovisionadas para Adobe Analytics. [Más información](/help/analyze/analysis-workspace/curate-share/share-projects.md)</p> <p>Para unirse a la versión beta privada, póngase en contacto con su equipo de cuenta de Adobe.</p> | 26 de abril de 2023 | Junio de 2023 |

{style="table-layout:auto"}

## Correcciones en Adobe Analytics

* Se ha corregido un problema con los archivos de búsqueda de Operating System.tsv en la fuente de datos.
* Se ha corregido un problema con los valores de las métricas que diferían entre Reports &amp; Analytics y Workspace (AN-315965).
* Se ha corregido un problema que impedía importar clasificaciones parciales. (AN-315854)
* Se ha corregido un problema con la API de Analytics 1.4. (AN-316475)
* Se ha corregido un problema que impedía que algunos clientes obtuvieran clasificaciones para la dimensión Página a través del Report Builder y de Report &amp; Analytics. (AN-314445)
* Se ha corregido un problema que impedía transferir alertas. (AN-306457)

### Otras correcciones

AN-288373; AN-305144; AN-309023; AN-310466; AN-311686; AN-311705; AN-312018; AN-312105; AN-312116; AN-312191; AN-312502; AN-312737; AN-312854; AN-312991; AN-313253; AN-313275; AN-313278; AN-313282; AN-313365; AN-313390; AN-313547; AN-313549; AN-313818; AN-313986; AN-314080; AN-314248; AN-314251; AN-314262; AN-314300; AN-314309; AN-314448; AN-314643; AN-314564; AN-314645; AN-314705; AN-314761; AN-314831; AN-314919; AN-314948; AN-315032; AN-315115; AN-315154; AN-315158; AN-315321; AN-315375; AN-315379; AN-315392; AN-315407; AN-315427; AN-315582; AN-315591; AN-315699; AN-315700; AN-315704; AN-315705; AN-315777; AN-315923; AN-316237; AN-316243; AN-316324; AN-316415; AN-316474; AN-316493; AN-316596; AN-316864;

## Avisos importantes para los administradores de Adobe Analytics {#admin}

| Aviso | Fecha de incorporación o actualizada | Descripción |
| ----------- | ---------- | ---------- |
| **Los procesos de búsqueda de dispositivos ahora utilizan un tercero para todas las búsquedas de dispositivos** | 3 de marzo de 2023 | El 2 de marzo de 2023, como parte del despliegue de asistencia para sugerencias de clientes, actualizamos nuestros procesos de búsqueda de dispositivos para utilizar un tercero para todas las búsquedas de dispositivos. Anteriormente, solo habíamos utilizado el tercero para búsquedas de dispositivos móviles. Como parte de ese despliegue, algunos sistemas operativos de escritorio se etiquetaron incorrectamente con el texto &quot;móvil&quot; (p. ej. &quot;Mobile OS X 10.15.7&quot; en lugar de &quot;OS X 10.15.7&quot;).<p>Durante la publicación de Adobe en abril corregiremos estos nombres. Los informes de Analytics y CJA se actualizarán de forma retroactiva, ya que sus informes buscarán el nombre del sistema operativo en función de un ID registrado como parte de los datos de evento. Una vez actualizado el valor de búsqueda correspondiente a un ID, se corregirán todos los informes, incluidos los datos históricos. Para [!UICONTROL Fuentes de datos] clientes, el cambio es retroactivo si utiliza un proceso de búsqueda similar en el momento de generar el informe. Sin embargo, si almacena el valor del sistema operativo en los datos de evento, los informes se actualizarán en adelante únicamente. Consulte [Sistema operativo](/help/components/dimensions/operating-systems.md) para obtener más información. |
| **Actualización de las búsquedas de dispositivos debido a las sugerencias del cliente de Google** | 27 de febrero de 2023 | El uso de sugerencias del cliente, planificado para el 16 de febrero de 2023, se pospuso para garantizar mejor la calidad de las búsquedas de dispositivos mediante sugerencias. El 27 de febrero de 2023, procedimos con la primera fase de la versión para admitir Sugerencias del cliente. La segunda y última fase de la versión se completó el jueves, 2 de marzo de 2023. [Más información](/help/technotes/client-hints.md) |
| **Migración automática a la arquitectura del conjunto de clasificación** | 8 de febrero de 2023 | En los próximos meses, Adobe planea migrar todas las clasificaciones de todas las organizaciones a la arquitectura de clasificación más reciente. Se estima que los últimos clientes en migrar lo harán en mayo de 2023. No se requiere ninguna acción por parte del cliente y no se espera tiempo de inactividad. Esta nueva arquitectura tiene muchas ventajas, entre ellas estas:<ul><li>Reducción significativa del tiempo de procesamiento (72 horas → 24 horas)</li><li>La capacidad de usar la IU de los [conjuntos de clasificación](/help/components/classifications/sets/overview.md)</li><li>La opción de usar datos de clasificación en Adobe Experience Platform en el futuro mediante el [Conector de origen de Adobe Analytics para datos de clasificación](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/classifications.html?lang=es)</li></ul>Tenga en cuenta los siguientes cambios que pueden afectar potencialmente al flujo de trabajo de su organización:<ul><li>Al usar el explorador o la importación mediante FTP, “[!UICONTROL Sobrescribir en caso de conflicto]” siempre está habilitado.</li><li>Al utilizar el explorador o la importación mediante FTP, ya no se admite la opción de exportar inmediatamente después de la importación.</li><li>El punto final `GetDimensions` de la API de Analytics 2.0 ahora devuelve identificadores de cadena para clasificaciones, en lugar de identificadores numéricos. Se pueden seguir utilizando identificadores numéricos, pero Adobe recomienda utilizar los nuevos identificadores de cadena siempre que sea posible. Los identificadores numéricos se pueden recuperar utilizando el parámetro de cadena de consulta `?expansion=hidden`.</li></ul>Póngase en contacto con el Servicio de atención al cliente de Adobe si desea obtener una programación de migración más específica para su organización o si tiene preguntas o inquietudes acerca de esta migración. [Más información](/help/components/classifications/sets/overview.md) |

{style="table-layout:auto"}

## Avisos de final de la vida útil {#eol}

| Final de la vida útil de producto o función | Fecha de incorporación o actualización | Descripción |
| --- | --- | --- |
| **Fin de la vida útil del servicio japonés de seguimiento de Feature Phone** | 21 de marzo de 2023 | Solo para nuestros clientes japoneses: En el **finales de mayo de 2023**, el servicio japonés de seguimiento de Feature Phone (mod_ktrack) se interrumpirá. Pedimos disculpas por las molestias, pero le pedimos que desinstale o deshabilite los módulos instalados en su servidor Apache. Consulte las páginas 27 y 28 en [este documento](/help/release-notes/mod_ktrackforSiteCatalyst_ver1.40.pdf) como referencia. |
| **EOL para [!DNL Reports & Analytics]** | 7 de marzo de 2023 | A partir del **31 de diciembre de 2023**, Adobe tiene la intención de descatalogar [!DNL Reports & Analytics] y sus informes y funciones correspondientes. Los informes, las visualizaciones y la tecnología subyacente que alimentan [!DNL Reports & Analytics] ya no cumplen los estándares tecnológicos de Adobe. La mayoría de las funciones de [!DNL Reports & Analytics] están disponibles en [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=es). Desde el lanzamiento de Analysis Workspace en 2015, las funcionalidades y capacidades de [!DNL Reports & Analytics] se han trasladado a Analysis Workspace y se ha alcanzado un umbral de paridad de flujo de trabajo. [Este aviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) explica el proceso de finalización de la vida útil.<p>El 31 de diciembre de 2023, finalizaremos muchas de las funciones de Reports &amp; Analytics asociadas, incluidas, entre otras, las siguientes: Informes programados, Extractos de datos e Informes DL. A partir del 31 de diciembre de 2023, ya no se enviarán los informes programados. En **Abril de 2023**, cualquier informe que estuviera programado para caducar después del 31 de diciembre de 2023 se actualizará automáticamente y se revertirá para que caduque el 31 de diciembre de 2023. Además, ya no puede programar informes futuros después del 31 de diciembre de 2023. |
| **EOL de la métrica [!UICONTROL Personas]** | 9 de marzo de 2023 | Con la retirada de [[!DNL Device Co-op]](https://experienceleague.adobe.com/docs/discontinued/using/device-co-op.html?lang=es), la métrica Personas relacionada con la cooperación entre dispositivos ya no es relevante. El 8 de mayo de 2023, eliminaremos el [!UICONTROL People] métrica. En ese momento, redireccionaremos sus datos a la métrica [!UICONTROL Visitante único] para evitar que se estropeen los proyectos, los segmentos y las métricas calculadas.<p>**Nota**: La métrica [[!UICONTROL Personas] vinculada a análisis multidispositivo](/help/components/metrics/people.md) no se ve afectado por este anuncio. |
| **Funcionalidad del final de vida útil de las [!UICONTROL Listas de publicación]** | 29 de septiembre de 2022 | Como parte del final de la vida útil de Reports &amp; Analytics, las [!UICONTROL Listas de publicación] están programadas para llegar al final de su vida útil en **diciembre de 2023**. No podrá crear [!UICONTROL Listas de publicación] nuevas ni acceder a las existentes para enviar o programar proyectos de [!UICONTROL Analysis Workspace]. |
| **Fin de la vida útil para Data Workbench** | 14 de septiembre de 2022 | Adobe tiene planeado el fin de la vida útil de Data Workbench con fecha de aplicación el **31 de diciembre de 2023**. Consulte [Anuncio del fin de la vida útil de Data Workbench](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=es) para obtener más información. Póngase en contacto con el Administrador de cuentas de Adobe de su organización si tiene alguna pregunta. |

{style="table-layout:auto"}

## AppMeasurement

Para obtener las últimas actualizaciones de las versiones de AppMeasurement (2.23.0), consulte las [notas de la versión de AppMeasurement para JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=es).


## Recursos relacionados

* [Notas de la versión anteriores de 2022](/help/release-notes/2022.md)
* [Notas de la versión de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=es)
* [Notas de la versión de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
* Las últimas actualizaciones de la versión para los [productos de Adobe Experience Cloud](https://business.adobe.com/es/products/adobe-experience-cloud-products.html)

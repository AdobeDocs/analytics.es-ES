---
title: Últimas notas de la versión de Analytics
description: Vea las notas de la versión actuales de Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 3d2e6966fbc765cd19f7a258457d89af3097083f
workflow-type: tm+mt
source-wordcount: '1208'
ht-degree: 50%

---

# Notas de la versión de Adobe Analytics actual (Marzo de 2023)

**Última actualización**: 9 de marzo de 2023

Las versiones de Adobe Analytics funcionan con un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funcionalidades. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Funciones nuevas o actualizadas en Adobe Analytics {#features}

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Diccionario de datos en Analysis Workspace** | El diccionario de datos ayuda a los usuarios y administradores a realizar un seguimiento, administrar y comprender mejor los componentes (dimensiones, métricas) de su entorno de Analytics. [Más información](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) | 15 de marzo de 2023 | 22 de marzo de 2023 |
| **Historias de datos en paneles móviles** | Las historias de datos le permiten agregar varias vistas de detalles personalizables a mosaicos en proyectos de cuadros de resultados móviles. Utilice historias de datos para profundizar en los controladores clave, las métricas relacionadas y los diferentes pasos a lo largo del recorrido del cliente. Puede deslizar fácilmente el dedo a través de estas vistas para comprender toda la historia detrás de sus métricas clave. [Más información](/help/analyze/mobile-app/create-scorecard.md#create-data-story) | N/A | 8 de marzo de 2023 |
| **Fechas de caducidad del proyecto programado** | Puede establecer las fechas de caducidad máximas para los proyectos programados hasta un año, independientemente de la frecuencia de programación. | N/A | 8 de marzo de 2023 |
| **Uso compartido de vínculos para proyectos (no se requiere inicio de sesión)** - Solo acceso beta privado | <p>Ahora puede compartir vínculos de solo lectura a proyectos de Analysis Workspace con personas que no tienen acceso a Adobe Analytics. Puede compartir vínculos de proyectos con personas fuera de su organización o con personas de su organización que no estén aprovisionadas para Adobe Analytics. [Más información](/help/analyze/analysis-workspace/curate-share/share-projects.md)</p> <p>Para unirse a la versión beta privada, póngase en contacto con el equipo de la cuenta de Adobe.</p> | 15 de marzo de 2023 (beta privada) | Abril de 2023 |
| **Actualizaciones del intervalo de fechas del panel** | En Workspace, hemos añadido las siguientes mejoras:<ul><li>A partir de la versión de febrero, los elementos de dimensión y las vistas previas de datos se basan en el intervalo de fechas del panel y no en los últimos 90 días. </li><li>Todos los elementos de dimensión enumerados se basan en los datos dentro del intervalo de fechas del panel. Si un elemento de dimensión tiene datos fuera del intervalo de fechas, puede mostrar datos adicionales más allá del intervalo de fechas en la parte inferior de la lista.</li><li>Los Dimension que no tienen datos se pueden mostrar en el carril izquierdo. Haga clic en las opciones mostrar más para ver los elementos de dimensión con datos fuera del intervalo de fechas del panel.</li><li>Las vistas previas de datos en los creadores de segmentos y métricas calculadas se basan en el intervalo de fechas del panel a menos que se acceda desde los administradores de componentes, que no tienen un panel asociado y siguen basados en los últimos 90 días.</li><li>Las vistas previas de datos muestran datos o componentes basados en el intervalo de fechas del panel.</li></ul> | N/A | 8 de febrero de 2023 |

## Correcciones en Adobe Analytics 

AN-308177; AN-308727; AN-308846; AN-309591; AN-310614; AN-311544; AN-311570; AN-311665; AN-311948 AN-312108 AN-AN-312142 AN-AN; AN-AN-AN; AN-AN; AN-AN; AN-AN;-AN; Y-AN-AN; Y-AN-312143; AN-AN; Y-AN-AN; Y-AN-AN; Y-AN-AN-AN; Y-AN-AN-AN; Y-AN-AN; Y-312114; AN-; AN-; AN-312389; AN-; AN-312391; AN-312431; AN-312453; AN-312454; AN-312458; AN-312503; AN-; AN-312533; AN-312682 312698 312714 312738 312807 312829 312849 312875 312980 312997 313059 313077 313110 313195 313196 313258 313554 313580 313702 313820 313844 313859 313879 314273

## Avisos importantes para los administradores de Adobe Analytics {#admin}

| Aviso | Fecha de incorporación  o actualizada | Descripción |
| ----------- | ---------- | ---------- |
| **Actualización de las búsquedas de dispositivos debido a las sugerencias del cliente de Google** | 27 de febrero de 2023 | El uso de sugerencias del cliente, planificado para el 16 de febrero de 2023, se pospuso para garantizar mejor la calidad de las búsquedas de dispositivos mediante sugerencias. El 27 de febrero de 2023, procedimos con la primera fase de la versión para admitir Client Hints. La segunda y última fase de la versión se completó el jueves, 2 de marzo de 2023. [Más información](/help/technotes/client-hints.md) |
| **Disponibilidad del conector de origen de Analytics** | 15 de febrero de 2023 | El 28 de febrero de 2023, el conector de origen de Analytics estuvo disponible en el nuevo centro de datos de Adobe Experience Platform ubicado en Canadá. |
| **Migración automática a la arquitectura del conjunto de clasificación** | 8 de febrero de 2023 | En los próximos meses, Adobe planea migrar todas las clasificaciones de todas las organizaciones a la arquitectura de clasificación más reciente. Se estima que los últimos clientes en migrar lo harán en mayo de 2023. No se requiere ninguna acción por parte del cliente y no se espera tiempo de inactividad. Esta nueva arquitectura tiene muchas ventajas, entre ellas estas:<ul><li>Reducción significativa del tiempo de procesamiento (72 horas → 24 horas)</li><li>La capacidad de usar la IU de los [conjuntos de clasificación](/help/components/classifications/sets/overview.md)</li><li>La opción de usar datos de clasificación en Adobe Experience Platform en el futuro mediante el [Conector de origen de Adobe Analytics para datos de clasificación](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/classifications.html?lang=es)</li></ul>Tenga en cuenta los siguientes cambios que pueden afectar potencialmente al flujo de trabajo de su organización:<ul><li>Al usar el explorador o la importación mediante FTP, “[!UICONTROL Sobrescribir en caso de conflicto]” siempre está habilitado.</li><li>Al utilizar el explorador o la importación mediante FTP, ya no se admite la opción de exportar inmediatamente después de la importación.</li><li>El punto final `GetDimensions` de la API de Analytics 2.0 ahora devuelve identificadores de cadena para clasificaciones, en lugar de identificadores numéricos. Se pueden seguir utilizando identificadores numéricos, pero Adobe recomienda utilizar los nuevos identificadores de cadena siempre que sea posible. Los identificadores numéricos se pueden recuperar utilizando el parámetro de cadena de consulta `?expansion=hidden`.</li></ul>Póngase en contacto con el Servicio de atención al cliente de Adobe si desea obtener una programación de migración más específica para su organización o si tiene preguntas o inquietudes acerca de esta migración. [Más información](/help/components/classifications/sets/overview.md) |

{style="table-layout:auto"}

## Avisos de final de la vida útil {#eol}

| Final de la vida útil de producto o función | Fecha de incorporación o actualización | Descripción |
| --- | --- | --- |
| **EOL para [!DNL Reports & Analytics]** | 7 de marzo de 2023 | A partir del **31 de diciembre de 2023**, Adobe tiene la intención de descatalogar [!DNL Reports & Analytics] y sus informes y funciones correspondientes. Los informes, las visualizaciones y la tecnología subyacente que alimentan [!DNL Reports & Analytics] ya no cumplen los estándares tecnológicos de Adobe. La mayoría de las funciones de [!DNL Reports & Analytics] están disponibles en [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=es). Desde el lanzamiento de Analysis Workspace en 2015, las funcionalidades y capacidades de [!DNL Reports & Analytics] se han trasladado a Analysis Workspace y se ha alcanzado un umbral de paridad de flujo de trabajo. [Este aviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) explica el proceso de finalización de la vida útil.<p>El 31 de diciembre de 2023, finalizaremos muchas de las funciones de Reports &amp; Analytics asociadas, incluidas, entre otras, las siguientes: Informes programados, Extractos de datos e Informes DL. A partir del 31 de diciembre de 2023, ya no se enviarán los informes programados. Entrada **Abril de 2023**, cualquier informe que estuviera programado para caducar más allá del 31 de diciembre de 2023 se actualizará automáticamente y se revertirá para que caduque el 31 de diciembre de 2023. Además, ya no puede programar informes futuros más allá del 31 de diciembre de 2023. |
| **EOL de [!UICONTROL People] métrica** | 9 de marzo de 2023 | Con la obsolescencia del [[!DNL Device Co-op]](https://experienceleague.adobe.com/docs/discontinued/using/device-co-op.html), la métrica Personas relacionadas con Device Co-op ya no es relevante. El 8 de mayo de 2023, se eliminará el [!UICONTROL People] métrica. En ese momento, redireccionaremos sus datos al [!UICONTROL Visitante único] para evitar que se rompan los proyectos, los segmentos y las métricas calculadas.<p>**Nota**: La [[!UICONTROL People] Métrica vinculada a análisis entre dispositivos](/help/components/metrics/people.md) no se ve afectado por este anuncio. |
| **Funcionalidad del final de vida útil de las [!UICONTROL Listas de publicación]** | 29 de septiembre de 2022 | Como parte del final de la vida útil de Reports &amp; Analytics, [!UICONTROL Listas de publicaciones] están programadas para alcanzar el final de su vida útil en **Diciembre de 2023**. No podrá crear elementos nuevos ni acceder a los existentes [!UICONTROL Listas de publicaciones] para enviar o programar [!UICONTROL Analysis Workspace] proyectos. |
| **Fin de la vida útil para Data Workbench** | 14 de septiembre de 2022 | Adobe tiene planeado el fin de la vida útil de Data Workbench con fecha de aplicación el **31 de diciembre de 2023**. Consulte [Anuncio del fin de la vida útil de Data Workbench](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=es) para obtener más información. Póngase en contacto con el Administrador de cuentas de Adobe de su organización si tiene alguna pregunta. |
| **EOL para [!DNL Reports & Analytics]** | 4 de enero de 2022 | A partir del **31 de diciembre de 2023**, Adobe tiene la intención de descatalogar [!DNL Reports & Analytics] y sus informes y funciones correspondientes. Los informes, las visualizaciones y la tecnología subyacente que alimentan [!DNL Reports & Analytics] ya no cumplen los estándares tecnológicos de Adobe. La mayoría de las funciones de [!DNL Reports & Analytics] están disponibles en [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=es). Desde el lanzamiento de Analysis Workspace en 2015, las funcionalidades y capacidades de [!DNL Reports & Analytics] se han trasladado a Analysis Workspace y se ha alcanzado un umbral de paridad de flujo de trabajo. [Este aviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) explica el proceso de finalización de la vida útil. |

{style="table-layout:auto"}

## AppMeasurement

Para obtener las últimas actualizaciones de las versiones de AppMeasurement (2.23.0), consulte las [notas de la versión de AppMeasurement para JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=es).


## Recursos relacionados

* [Notas de la versión anteriores de 2022](/help/release-notes/2022.md)
* [Notas de la versión de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=es)
* [Notas de la versión de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
* Las últimas actualizaciones de la versión para los [productos de Adobe Experience Cloud](https://business.adobe.com/es/products/adobe-experience-cloud-products.html)

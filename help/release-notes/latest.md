---
title: Últimas notas de la versión de Analytics
description: Vea las notas de la versión actuales de Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 1d98d711c17d3c7ca487b8f5bd4e918a9a399ea7
workflow-type: tm+mt
source-wordcount: '1456'
ht-degree: 53%

---

# Notas de la versión de Adobe Analytics actual (Junio de 2023)

**Última actualización**: 1 de junio de 2023

Las versiones de Adobe Analytics funcionan con un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funcionalidades. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Elementos destacados de la versión {#highlights}

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Uso compartido de vínculos para proyectos (no se requiere inicio de sesión)** | Ahora puede compartir vínculos de solo lectura a proyectos de Analysis Workspace con personas que no tienen acceso a Adobe Analytics. Esto incluye compartir con personas fuera de su organización o con personas de su organización que no estén aprovisionadas para Adobe Analytics. [Más información](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=es#share-public-link)<p>Esta funcionalidad está habilitada de forma predeterminada y el administrador del sistema puede inhabilitarla. [Más información](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/user-preferences.html?lang=es#company-preferences)</p> | 3 de mayo de 2023 | 7 de junio de 2023 |
| **Conjuntos de clasificaciones: consolidación** | Combine clasificaciones de diferentes grupos de informes en un conjunto de datos consolidado. El conjunto de datos consolidado puede utilizarse en Conjuntos de clasificaciones o como conjunto de datos de búsqueda en CJA. Más información (próximamente) |  | 7 de junio de 2023 |
| **Conjuntos de clasificaciones: generador de reglas** | Utilice el generador de reglas de clasificación en la arquitectura de conjunto de clasificación actual. Más información (próximamente) |  | 7 de junio de 2023 |
| **Conjuntos de clasificaciones: importación automatizada** | Ahora puede importar automáticamente los datos del conjunto de clasificaciones desde destinos de almacenamiento en la nube. Más información (próximamente) |  | 7 de junio de 2023 |
| **Nueva variable de AppMeasurement** | La variable `doubleEncodeLinkParameters` se adapta a los casos extremos en los que las implementaciones codifican caracteres multibyte en variables de seguimiento de vínculos. La mayoría de las implementaciones no necesitan definir esta variable. Más información (próximamente) |  | 7 de junio de 2023 |
| **Destinos seguros para la exportación de fuentes de datos** | Ahora, las fuentes de datos se pueden enviar a los siguientes destinos de almacenamiento en la nube:<ul><li>Amazon S3</li><li>Azure RBAC</li><li>Azure SAS</li><li>Google Cloud Platform</li></ul>Ya no se recomiendan los destinos que antes estaban disponibles (FTP, SFTP, S3 y Azure Blob). [Más información](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/create-feed.html?lang=es) |  | 12 de junio de 2023 |
| **Creación de informes de bots en Workspace** | Los informes de bots ya están disponibles en Analysis Workspace. Esta función incluye varias adiciones:<ul><li>Una nueva dimensión: [Nombre de bot](/help/components/dimensions/bot-name.md)</li><li>Dos nuevas métricas: [Vistas de página de bots](/help/components/metrics/bot-page-views.md) y [Ocurrencias de bots](/help/components/metrics/bot-occurrences.md).</li><li>Una nueva plantilla de métrica calculada: [Proporción de vistas de página de bots](/help/components/c-calcmetrics/cm-reference/default-calcmetrics.md)</li><li>Un nuevo informe de Workspace: Informes de bots</li></ul>La nueva dimensión y las métricas contienen datos que se rellenan a partir de marzo de 2023. |  | Junio de 7,2023 |

{style="table-layout:auto"}

## Otras funciones nuevas o actualizadas {#other}

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Eliminación de filas que contienen dimensiones dinámicas de una tabla de forma libre** | En una tabla de forma libre de Analysis Workspace, ahora puede eliminar rápidamente filas específicas que contengan dimensiones dinámicas mediante el icono x. Al hacerlo, se aplica automáticamente la regla de filtro &quot;Excluir siempre elementos&quot;.<p>Anteriormente, la única forma de eliminar filas que contenían dimensiones dinámicas era crear manualmente una regla en el cuadro de diálogo Filtro. [Más información](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)</p> | N/A | 17 de mayo de 2023 |
| **Nuevo botón para añadir una visualización dentro de un panel** | Ahora hay disponible un nuevo botón en la parte inferior de cada panel en Analysis Workspace, lo que le permite añadir rápidamente una visualización. <p>Anteriormente, los únicos métodos para añadir una visualización a un panel eran arrastrar una visualización desde el carril izquierdo, duplicar o copiar una visualización existente o crear un panel en blanco. [Más información](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)</p> | N/A | 17 de mayo de 2023 |
| **Vinculación profunda (aplicación móvil)** | Permite a los usuarios enviar vínculos a cuadros de resultados que los llevarán directamente al cuadro de resultados de la aplicación. Esto facilita aún más el uso compartido de proyectos e impulsa la participación de una audiencia menos técnica. [Más información](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/create-scorecard.html#share-scorecards-using-a-shareable-link) | N/A | 17 de mayo de 2023 |
| **Filtros desplegables dinámicos** | Presentamos un nuevo tipo de filtro desplegable que determina los valores disponibles en función de los datos dentro del intervalo de informes del panel y los valores de otros filtros desplegables. Puede utilizar filtros desplegables dinámicos arrastrando una dimensión a la zona desplegable del panel mientras mantiene pulsada [!UICONTROL Shift]. Los filtros desplegables estáticos permanecen inalterados al arrastrar un grupo de elementos de dimensión a la zona desplegable del panel mientras se mantiene presionado [!UICONTROL Shift]. [Más información](/help/analyze/analysis-workspace/c-panels/panels.md) |  | 14 de junio de 2023 |
| **Página de aprendizaje de Analytics actualizada** | La pestaña Aprendizaje de la página de aterrizaje de Adobe Analytics ahora contiene las siguientes mejoras:<ul><li>Diseño mejorado que muestra más contenido de aprendizaje en una sola página con navegación mejorada</li><li>Capacidad para personalizar el contenido de aprendizaje por nivel de experiencia (principiante, intermedio y avanzado)</li></ul>[Más información](/help/analyze/landing.md) |  | Junio de 30,2023 |
| **Ordenar componentes en Analysis Workspace** | Ahora hay disponible una nueva opción de ordenación al ver componentes en el carril izquierdo o en el diccionario de datos de Analysis Workspace. Puede ordenar los componentes por Recomendado (los más utilizados), Alfabético o Categórico (tipo).<p>Anteriormente, solo se podían buscar o filtrar componentes. [Más información](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)</p> | N/A | Por determinar |

{style="table-layout:auto"}

## Correcciones en Adobe Analytics

-311878; -313968; AN-314130; AN-315701; AN-315761; AN-316613; AN-317563; AN-318829; AN-319009; AN-319043; AN-319066; AN-; AN-; AN-319166; AN-319245; AN-319271; AN-319381; AN-319391; AN-319482; AN-319621; AN-319637; AN-319676; AN-320176; AN-320221; AN-320225; AN-320286; AN-320312; AN-320316; AN-320449; AN-320477; AN-320492; AN-320538; AN-320556; AN-320569; AN-320679; AN-320684; AN-320786; AN-320802; AN-320811; AN-320812; AN-320815; AN-321032; AN-321033; AN-321070; AN-321096; AN-321105; AN-321122; AN-321337;

## Avisos importantes para los administradores de Adobe Analytics {#admin}

| Aviso | Fecha de incorporación o actualizada | Descripción |
| ----------- | ---------- | ---------- |
| **Caducidad de 37 meses de los ID de compra y los ID de evento (serialización de eventos)** | Mayo de 25,2023 | Próxima versión del motor de procesamiento de visitas de Analytics, prevista para su lanzamiento en **finales de junio de 2023 o principios de julio de 2023**, empezará a aplicar una caducidad de 37 meses para los ID de compra y los ID de evento (serialización de eventos). Actualmente, los ID de compra y los ID de evento nunca caducan en Adobe Analytics. Una vez que se vea/utilice un ID de compra o ID de evento, cualquier visita futura, independientemente de cuándo, tendrá esa compra o evento marcado como duplicado. Con la nueva versión del motor de procesamiento:<ul><li>Los ID de compra y los ID de evento siempre caducan pasados 37 meses.</li><li>Si han pasado 37 meses desde que se vio el ID de compra o el ID de evento, ya no se considera una compra o evento duplicado.</li><li> Si está &quot;reutilizando&quot; los ID de compra o ID de evento de hace más de 37 meses, ya no se consideran duplicados.</li></ul> |
| **Migración a las credenciales de servidor a servidor de AdobeIO OAuth** | 11 de mayo de 2023 | Los clientes de la API de Adobe Analytics y Livestream que utilizan las credenciales de JWT de AdobeIO deben migrar a las credenciales de servidor a servidor de OAuth de AdobeIO de **1 de enero de 2025**. Para obtener más información y cronologías, consulte el aviso de fin de vida útil en la tabla siguiente. |
| **Nuevas IP utilizadas por las fuentes de datos de Adobe Analytics y la salida de Data Warehouse en el centro de datos de Londres** | 27 de abril de 2023 | Esto afecta a los clientes del centro de datos de Londres que tienen solicitudes de fuentes de datos o informes de Data Warehouse que se entregan a un servicio FTP/SFTP. Los siguientes intervalos de direcciones IP deben añadirse a la configuración del cortafuegos para permitir el acceso: <ul><li>130.248.244.32/29</li><li>130.248.244.40/29</li></ul> |

{style="table-layout:auto"}

## Avisos de final de la vida útil {#eol}

| Final de la vida útil de producto o función | Fecha de incorporación o actualización | Descripción |
| --- | --- | --- |
| **Migración a las credenciales de servidor a servidor de AdobeIO OAuth** | 11 de mayo de 2023 | Los clientes de la API de Adobe Analytics y Livestream que utilizan las credenciales de JWT de AdobeIO deben migrar a las credenciales de servidor a servidor de OAuth de AdobeIO de **1 de enero de 2025**. AdobeIO no permitirá que se creen nuevas credenciales de JWT a partir del 1 de mayo de 2024. Los clientes que utilizan JWT deben crear una nueva credencial de servidor a servidor OAuth o migrar su credencial JWT existente a una credencial de servidor a servidor OAuth. Los clientes también deben actualizar sus aplicaciones cliente para utilizar las nuevas credenciales de servidor a servidor de OAuth. <ul><li>[Migración de credenciales de cuenta de servicio (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Uso de las nuevas credenciales de servidor a servidor de OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Preguntas frecuentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **EOL para [!DNL Reports & Analytics]** | 7 de marzo de 2023 | A partir del **31 de diciembre de 2023**, Adobe tiene la intención de descatalogar [!DNL Reports & Analytics] y sus informes y funciones correspondientes. Los informes, las visualizaciones y la tecnología subyacente que alimentan [!DNL Reports & Analytics] ya no cumplen los estándares tecnológicos de Adobe. La mayoría de las funciones de [!DNL Reports & Analytics] están disponibles en [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=es). Desde el lanzamiento de Analysis Workspace en 2015, las funcionalidades y capacidades de [!DNL Reports & Analytics] se han trasladado a Analysis Workspace y se ha alcanzado un umbral de paridad de flujo de trabajo. [Este aviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) explica el proceso de finalización de la vida útil.<p>El 31 de diciembre de 2023, finalizaremos muchas de las funciones de Reports &amp; Analytics asociadas, incluidas, entre otras, las siguientes: Informes programados, Extractos de datos e Informes DL. A partir del 31 de diciembre de 2023, ya no se enviarán los informes programados. En **Abril de 2023**, cualquier informe que estuviera programado para caducar después del 31 de diciembre de 2023 se actualizará automáticamente y se revertirá para que caduque el 31 de diciembre de 2023. Además, ya no puede programar informes futuros después del 31 de diciembre de 2023. |
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

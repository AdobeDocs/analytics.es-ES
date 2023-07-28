---
title: Últimas notas de la versión de Analytics
description: Vea las notas de la versión actuales de Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: f996448224ffebd57023c8d8e4eeeccb4d6e2a47
workflow-type: ht
source-wordcount: '920'
ht-degree: 100%

---

# Notas de la versión de Adobe Analytics actual (Julio de 2023)

**Última actualización**: 10 de julio de 2023

Las versiones de Adobe Analytics funcionan con un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funcionalidades. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Nuevas funciones o mejoras {#features}

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Configuración de ubicaciones del almacenamiento de cuentas en la nube para introducir datos de clasificación** | Ahora puede administrar las ubicaciones del almacenamiento de cuentas en la nube que se utilizan para la automatización de conjuntos de clasificación. [Más información](/help/components/locations/configure-import-accounts.md)<p> | N/A | 10 de julio de 2023 |
| **Mejoras del filtro de reparación de datos** | Se han añadido tres mejoras de filtrado a Reparación de datos:<ul><li>Filtre por una variable para modificar una segunda variable. Por ejemplo, si `eVar2` contiene &quot;@&quot;, elimine `eVar3`.</li><li>Filtrar por valores numéricos o no numéricos</li><li>Aplique varios filtros con un AND. Por ejemplo, donde `eVar2="a"`AND `eVar3="b"`</li></ul>[Más información](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/) | 21 de junio de 2023 | 12 de julio de 2023 |
| **Destinos seguros para la exportación de fuentes de datos** | Ahora, las fuentes de datos se pueden enviar a los siguientes destinos de almacenamiento en la nube:<ul><li>Amazon S3</li><li>Azure RBAC</li><li>Azure SAS</li><li>Google Cloud Platform</li></ul>Ya no se recomiendan los destinos que antes estaban disponibles (FTP, SFTP, S3 y Azure Blob). [Más información](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/create-feed.html?lang=es) | 12 de junio de 2023 | 13 de julio de 2023 |
| **Nueva variable de AppMeasurement** | La variable `decodeLinkParameters` se adapta a los casos extremos en los que las implementaciones codifican caracteres multibyte en variables de seguimiento de vínculos. La mayoría de las implementaciones no necesitan definir esta variable. [Más información](../implement/vars/config-vars/decodelinkparameters.md) |  | 17 de julio de 2023 |

{style="table-layout:auto"}

## Correcciones en Adobe Analytics

AN-307816; AN-318111; AN-318584; AN-318828; AN-320440; AN-320568; AN-320616; AN-321013; AN-321513; AN-321520; AN-321757; AN-321820; AN-321917; AN-322034; AN-322135; AN-322140; AN-322142; AN-322251; AN-322353; AN-322378; AN-322383; AN-322427; AN-322458; AN-322543; AN-322630; AN-322637; AN-322638; AN-322647; AN-322728; AN-322732; AN-322777; AN-322817; AN-322957; AN-322958; AN-323035; AN-323074; AN-323150; AN-323196; AN-323197; AN-323205; AN-323206; AN-323217; AN-323224; AN-323225; AN-323244; AN-323257; AN-323277; AN-323280; AN-323293; AN-323309; AN-323318; AN-323468; AN-323476; AN-323514; AN-323572; AN-323592; AN-323782; AN-323835

## Avisos importantes para los administradores de Adobe Analytics {#admin}

| Aviso | Fecha de incorporación o actualizada | Descripción |
| ----------- | ---------- | ---------- |
| **Caducidad de 37 meses de los ID de compra y los ID de evento (serialización de eventos)** | 10 de julio de 2023 | Una próxima versión del motor de procesamiento de visitas de Analytics, prevista para su lanzamiento el **13 de julio de 2023**, empezará a aplicar una caducidad de 37 meses para los ID de compra y los ID de evento (serialización de eventos). Actualmente, los ID de compra y los ID de evento nunca caducan en Adobe Analytics. Una vez que se vea/utilice un ID de compra o ID de evento, cualquier visita futura, independientemente de cuándo, tendrá esa compra o evento marcado como duplicado. Con la nueva versión del motor de procesamiento:<ul><li>Los ID de compra y los ID de evento siempre caducan pasados 37 meses.</li><li>Si han pasado 37 meses desde que se vio el ID de compra o el ID de evento, ya no se considera una compra o evento duplicado.</li><li> Si está &quot;reutilizando&quot; los ID de compra o ID de evento de hace más de 37 meses, ya no se consideran duplicados.</li></ul> |
| **Migración a las credenciales de servidor a servidor de Adobe I/O OAuth** | 11 de mayo de 2023 | Los clientes de la API de Adobe Analytics y Livestream que utilizan las credenciales de JWT de Adobe I/O deben migrar a las credenciales de servidor a servidor de Adobe I/O OAuth de forma predeterminada el **1 de enero de 2025**. Para obtener más información y cronologías, consulte el aviso de fin de vida útil en la tabla siguiente. |

{style="table-layout:auto"}

## Avisos de final de la vida útil {#eol}

| Final de la vida útil de producto o función | Fecha de incorporación o actualización | Descripción |
| --- | --- | --- |
| **Migración a las credenciales de servidor a servidor de Adobe I/O OAuth** | 11 de mayo de 2023 | Los clientes de la API de Adobe Analytics y Livestream que utilizan las credenciales de JWT de Adobe I/O deben migrar a las credenciales de servidor a servidor de Adobe I/O OAuth de forma predeterminada el **1 de enero de 2025**. Adobe I/O no permitirá que se creen nuevas credenciales de JWT a partir del 1 de mayo de 2024. Los clientes que utilizan JWT deben crear una nueva credencial de servidor a servidor OAuth o migrar su credencial JWT existente a una credencial de servidor a servidor OAuth. Los clientes también deben actualizar sus aplicaciones cliente para utilizar las nuevas credenciales de servidor a servidor de OAuth. <ul><li>[Migración de credenciales de cuenta de servicio (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guía de implementación para aplicaciones nuevas y antiguas con OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Uso de las nuevas credenciales de servidor a servidor de OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Preguntas frecuentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **EOL para [!DNL Reports & Analytics]** | 7 de marzo de 2023 | A partir del **31 de diciembre de 2023**, Adobe tiene la intención de descatalogar [!DNL Reports & Analytics] y sus informes y funciones correspondientes. Los informes, las visualizaciones y la tecnología subyacente que alimentan [!DNL Reports & Analytics] ya no cumplen los estándares tecnológicos de Adobe. La mayoría de las funciones de [!DNL Reports & Analytics] están disponibles en [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=es). Desde el lanzamiento de Analysis Workspace en 2015, las funcionalidades y capacidades de [!DNL Reports & Analytics] se han trasladado a Analysis Workspace y se ha alcanzado un umbral de paridad de flujo de trabajo. [Este aviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) explica el proceso de finalización de la vida útil.<p>El 31 de diciembre de 2023, finalizaremos muchas de las funciones de Reports &amp; Analytics asociadas, incluidas, entre otras, las siguientes: Informes programados, Extractos de datos e Informes DL. A partir del 31 de diciembre de 2023, ya no se enviarán los informes programados. En **Abril de 2023**, cualquier informe que estuviera programado para caducar después del 31 de diciembre de 2023 se actualizará automáticamente y se revertirá para que caduque el 31 de diciembre de 2023. Además, ya no puede programar informes futuros después del 31 de diciembre de 2023. |
| **Funcionalidad del final de vida útil de las [!UICONTROL Listas de publicación]** | 29 de septiembre de 2022 | Como parte del final de la vida útil de Reports &amp; Analytics, las [!UICONTROL Listas de publicación] están programadas para llegar al final de su vida útil en **diciembre de 2023**. No podrá crear [!UICONTROL Listas de publicación] nuevas ni acceder a las existentes para enviar o programar proyectos de [!UICONTROL Analysis Workspace]. |
| **Fin de la vida útil para Data Workbench** | 14 de septiembre de 2022 | Adobe tiene planeado el fin de la vida útil de Data Workbench con fecha de aplicación el **31 de diciembre de 2023**. Consulte [Anuncio del fin de la vida útil de Data Workbench](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=es) para obtener más información. Póngase en contacto con el Administrador de cuentas de Adobe de su organización si tiene alguna pregunta. |

{style="table-layout:auto"}

## AppMeasurement

Para obtener las últimas actualizaciones de las versiones de AppMeasurement (2.24.0), consulte las [notas de la versión de AppMeasurement para JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=es).


## Recursos relacionados

* [Notas de la versión anteriores de 2022](/help/release-notes/2022.md)
* [Notas de la versión de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=es)
* [Notas de la versión de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
* Las últimas actualizaciones de la versión para los [productos de Adobe Experience Cloud](https://business.adobe.com/es/products/adobe-experience-cloud-products.html)

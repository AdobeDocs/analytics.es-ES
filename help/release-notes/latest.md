---
title: Notas de la versión de Adobe Analytics actual
description: Vea las notas de la versión actuales de Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 2232778be91502eca2ecdc2c9598b8a3375abb8b
workflow-type: tm+mt
source-wordcount: '895'
ht-degree: 100%

---

# Notas de la versión de Adobe Analytics actual (Agosto de 2023)

**Última actualización**: 24 de agosto de 2023

Estas notas de la versión corresponden al periodo comprendido entre el 9 de agosto y el 13 de septiembre de 2023. Las versiones de Adobe Analytics funcionan con un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funcionalidades. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Nuevas funciones o mejoras {#features}

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Conjuntos de clasificación en la API 2.0** | Proporciona métodos de la API de Adobe Analytics 2.0 para guardar, eliminar, recuperar, importar y exportar datos del conjunto de clasificación. | N/A | 30 de agosto de 2023 |
| **Administrador de actividades de creación de informes** | El administrador de actividades de creación de informes proporciona a los administradores una visibilidad detallada del consumo de creación de informes para cada grupo de informes, lo que permite a los administradores diagnosticar fácilmente y luego corregir los problemas de capacidad durante las horas de mayor actividad de creación de informes. [Más información](/help/admin/admin/reporting-activity.md) | N/A | 12 de septiembre de 2023 |

{style="table-layout:auto"}

## Correcciones en Adobe Analytics

* Se ha corregido un problema con los eventos personalizados que no conseguían cargarse. (AN-324163)
* Se ha corregido un problema que impedía editar etiquetas para las leyendas en una visualización. (AN-323246)

AN-315605; AN-316306; AN-317494; AN-317844; AN-320424; AN-320597; AN-320680; AN-320869; AN-321624; AN-321693; AN-322009; AN-322244; AN-322380; AN-322432; AN-322466; AN-322556; AN-322669; AN-322735; AN-323151; AN-323220; AN-323380; AN-323492; AN-323595; AN-323755; AN-323854; AN-323916; AN-324044; AN-324200; AN-324213; AN-324238; AN-324347; AN-323598; AN-323625; AN-323631; AN-323638; AN-323641; AN-323755; AN-323767; AN-323777; AN-323825; AN-323846; AN-323972; AN-324113; AN-324170; AN-324197; AN-324273; AN-324275; AN-324345; AN-324384; AN-324433; AN-324511; AN-324513; AN-324521; AN-324524; AN-324531; AN-324532; AN-324534; AN-324537; AN-324569; AN-324618; AN-324635; AN-324688; AN-324704; AN-324712; AN-324721; AN-324745; AN-324792; AN-324793; AN-324794; AN-324795; AN-324824; AN-324905; AN-324918; AN-324932; AN-324934; AN-324947; AN-325003; AN-325073; AN-325143; AN-325148; AN-325153; AN-325177; AN-325187; AN-325252; AN-325305; AN-325363; AN-325401; AN-325439; AN-325431; AN-325491; AN-325495; AN-325508; AN-325594; AN-325601; AN-325660; AN-325779; AN-325857; AN-325883; AN-325885; AN-325886


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

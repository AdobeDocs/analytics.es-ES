---
title: Notas de la versión de Adobe Analytics actual
description: Vea las notas de la versión actuales de Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: d1b9ef79a456fc52b7fa644d088f7089c9b654e4
workflow-type: tm+mt
source-wordcount: '899'
ht-degree: 79%

---

# Notas de la versión de Adobe Analytics actual (Agosto de 2023)

**Última actualización**: 9 de agosto de 2023

Estas notas de la versión abarcan el periodo de lanzamiento del 9 de agosto al 13 de septiembre de 2023. Las versiones de Adobe Analytics funcionan con un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funcionalidades. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Nuevas funciones o mejoras entre el 9 de agosto y el 12 de septiembre de 2023 {#features}

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Conjuntos de clasificación en la API 2.0** | Proporciona métodos de la API de Adobe Analytics 2.0 para guardar, eliminar, recuperar, importar y exportar datos del conjunto de clasificaciones. | N/A | 31 de agosto de 2023 |
| **Administrador de actividades de creación de informes** | El Administrador de actividades de creación de informes proporciona a los administradores una visibilidad detallada del consumo de creación de informes para cada grupo de informes, lo que permite a los administradores diagnosticar fácilmente y luego corregir los problemas de capacidad durante las horas de mayor actividad de la creación de informes. [Más información](/help/admin/admin/reporting-activity.md) | N/A | 6 de septiembre de 2023 |

{style="table-layout:auto"}

## Correcciones en Adobe Analytics

* Se ha corregido un problema con los eventos personalizados que no se cargaban. (AN-324163)
* Se ha corregido un problema que impedía editar etiquetas para las leyendas en una visualización. (AN-323246)

AN-315605; AN-316306; AN-317494; AN-317844; AN-320424; AN-320597; AN-320680; AN-320869; AN-321624 AN-321693 AN-AN-322244 AN-AN; AN-AN-AN; AN-AN; AN-AN; AN-AN;-AN; Y-AN-AN; Y-AN-322380; AN-AN; Y-AN-AN; Y-AN-AN; Y-AN-AN-AN; Y-AN-AN-AN; Y-AN-AN; Y-322009; AN-; AN-; AN-322432; AN-322466; AN-322556; AN-322669; AN-AN; AN-AN-AN; AN-AN-AN; AN-AN-AN; AN-AN-AN; AN-AN-AN; AN-AN-AN; AN-AN; AN-AN; AN-AN; AN-AN; AN-AN; AN-AN; AN-AN; AN-AN; AN-AN; AN-AN; AN-AN; AN-AN; AN-AN; AN-322735;-AN;-AN;-323151;-AN;-AN-323220; AN-; AN-; AN-; AN-323380; AN-323492; AN-323595; AN-323755; AN-323854; AN-AN; AN-AN; AN-AN; AN-AN; AN-AN; AN-AN; AN-AN; AN-AN; AN-AN; AN-AN; AN-AN; AN-AN; AN-AN; AN-AN; AN-AN; AN-AN; AN-AN; AN-AN; AN-AN; AN-323916; AN-AN; AN-324044;-AN;-AN-324200;-AN-324213;-AN-AN-324238 324347 323598 323625 323631 323638 323641 323755 323767 323777 323825 323846 323972 324113 324170 324197 324273 324275 324345 324384 324433 324511 324513 324521 324524 324531 324532 324534 324537 324569 324618 324635 324688 324704 324712 324721 324745 324792 324793 324794 324795 324824 324905 324918 324932 324934 324947 325003 325073 325143 325148 325153 325177 325187 325252 325305 325363 325401 325439 325431 325491 325495 325508 325594 325601 325660 325779 325857 325883 325885 325886; Y-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-A-


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

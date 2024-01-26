---
description: Descripciones de los grupos de informes globales
title: Grupos de informes globales
feature: Report Suite Settings
exl-id: 97bdc9bd-2212-436b-b3b4-ec518624f9e6
role: Admin
source-git-commit: 938795c7378cb1f0537ff84eddeab3feddf8d073
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 90%

---

# Grupos de informes globales

Un grupo de informes globales recopila datos de todos los dominios y las aplicaciones que posee su organización. Requiere implementación para enviar todas las solicitudes de imagen a un único grupo de informes.

Adobe recomienda implementar un grupo de informes globales en la mayoría de los casos. Consulte [Consideraciones sobre el grupo de informes globales](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/global-rs.html?lang=es) para conocer las ventajas de implementar un grupo de informes globales.

Puede proporcionar subconjuntos de los datos del grupo de informes globales de su compañía a distintos usuarios finales mediante los enfoques de *etiquetado de grupos múltiples* y *grupo de informes virtuales*:

* **Etiquetado de grupos múltiples**: el etiquetado de grupos múltiples le permite enviar solicitudes de imagen no solo a un grupo de informes globales, sino también a grupos de informes secundarios individuales. La duplicación de los datos del informe global se anula en todos los grupos de informes.

  Por ejemplo, podría recopilar todos los datos de un grupo de informes globales y también configurar grupos de informes secundarios según la marca, la región u otro diferenciador. Los diferentes equipos de su compañía podrían entonces centrarse en los datos de los grupos de informes que les interesen.

  Para utilizar el etiquetado de grupos múltiples, implemente grupos de informes secundarios y un grupo de informes globales que incluya todos los datos de los grupos secundarios. El código de seguimiento de sus páginas web y aplicaciones incluirá el ID del grupo de informes (RSID) para el grupo de informes globales y también los RSID para los grupos de informes secundarios aplicables.<!-- Wording/be more specific? And include any links? -->

  Se realiza una llamada al servidor independiente a cada grupo de informes en la solicitud de imagen. Las llamadas a los grupos de informes secundarios son llamadas secundarias.

* **Grupo de informes virtuales**: un [grupo de informes virtuales](/help/components/vrs/vrs-about.md) es una consulta en segmentos especificados recopilados en un grupo de informes globales y disponibles para grupos de usuarios especificados. Los grupos de informes virtuales le permiten depurar elementos de informes para distintos usuarios finales sin utilizar el etiquetado de grupos múltiples, lo cual evita llamadas secundarias al servidor.

  Para utilizar grupos de informes virtuales, implemente un grupo de informes globales y luego analice los datos para crear grupos de informes virtuales con segmentos específicos aplicados y con permisos de grupo específicos. Puede crear grupos de informes virtuales en el Administrador de grupos de informes virtuales ([!UICONTROL Componentes] > [!UICONTROL Grupos de informes virtuales]). Consulte [Flujo de trabajo de grupos de informes virtuales](/help/components/vrs/c-workflow-vrs/vrs-workflow.md) para obtener más información.

El uso de grupos de informes virtuales en lugar del etiquetado de grupos múltiples suele ser una práctica recomendada, pero los grupos de informes virtuales tienen algunas limitaciones. Consulte [Grupos de informes virtuales y consideraciones sobre el etiquetado de grupos múltiples](/help/components/vrs/vrs-considerations.md) para determinar qué enfoque de grupo de informes es la mejor opción para sus necesidades comerciales. Para obtener una comparación detallada de los grupos de informes virtuales y la funcionalidad de etiquetado de grupos múltiples, consulte &quot;[Grupos de informes virtuales frente al etiquetado de grupos múltiples](/help/components/vrs/vrs-about.md#section_317E4D21CCD74BC38166D2F57D214F78).&quot;

<!---## Rollup reports

>[!NOTE]
>
>[!DNL Reports & Analytics] is the only tool that supported rollup reports. Reports & Analytics was end-of-lifed on January 17, 2024.

Limitations of Rollup Reports {#limitations-rollups}

* Rollups provide total data, but they do not report individual values in reports. For example, eVar1 values are not included, but their aggregate total can be.
* Data is not deduplicated when the rollup combines data across report suites.
* Rollups run nightly at midnight.
* When you add a report suite to an existing rollup, historical data is not included in the rollup.
* All child report suites must have data in them for a rollup to function. If new report suites are included in a rollup, make sure to send at least one page view to each of those report suites.
* Rollup report suites can include a maximum of 40 child report suites.
* Rollup report suites can include a maximum of 100 events.
* Data contained in rollup report suites does not support breakdowns or segments.
* The Pages report is replaced with the Most Popular Sites report, which reports on metrics at the child-suite level.

## Comparison of Global Report Suite and Rollup Report  Features

**Secondary server calls**: Rollups do not incur any additional server calls beyond what a single report suite collects. If your organization uses multi-suite tagging, secondary server calls are made for each additional report suite included in an image request.

>[!TIP]
>
>If you use only a global report suite with [virtual report suites](/help/components/vrs/vrs-considerations.md), no secondary server calls are needed.

**Implementation changes**: Rollups do not require any implementation changes, while global report suites require you to include the global report suite ID in your implementation.

**Duplication**: Global report suites deduplicate unique visitors, while rollups do not. For example, if a user visits three of your domains in the same day, rollups would count three daily unique visitors. Global report suites would record one unique visitor.

**Time frame**: Rollups are only processed at midnight each night, while global report suites report data with standard latency.

**Breadth**: Rollups have no way to communicate between report suites. Global report suites can attribute credit to conversion variables between report suites and provide pathing across report suites.

**Historical data**: Rollups can aggregate historical data, while global report suites only report data from the point they were implemented.

**Reports**: Global report suites provide data on all dimensions; rollups provide aggregate data on only high-level reports.

**Supported products**: Rollups could only be used in Reports & Analytics. They are not supported in Analysis Workspace, or Data Warehouse. Global report suites can be used across all products.

**Number of aggregated report suites**: Rollups only support a maximum of 40 child report suites. Global report suites can be implemented on any number of domains or apps that you own.--->

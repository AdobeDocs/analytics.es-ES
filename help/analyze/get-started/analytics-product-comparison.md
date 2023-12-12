---
description: Requisitos del sistema y comparación de Analysis Workspace, Reports & Analytics, Report Builder, Data Warehouse y Data Workbench
title: Comparación de productos y requisitos de Analytics
exl-id: 5adc6c10-cbbb-48d5-a7ab-367cbaff5e8a
feature: Analytics Basics
source-git-commit: 984406d00e5a5ae966fff60ec9fcfcb000958696
workflow-type: ht
source-wordcount: '416'
ht-degree: 100%

---

# Comparación de productos y requisitos de Analytics

Esta página contiene una comparación de varios productos de Adobe Analytics: Analysis Workspace, Reports &amp; Analytics, Report Builder, Data Warehouse, Data Workbench, Fuentes de datos y API de Analytics 2.0.

Para obtener información sobre qué producto de Adobe Analytics utilizar, consulte [¿Qué herramienta de Adobe Analytics debo usar?](/help/analyze/get-started/which-analytics-tool.md).

| Nombre del producto y vínculo de ayuda | [Analysis Workspace](/help/analyze/analysis-workspace/home.md) | [Reports &amp; Analytics](/help/analyze/reports-analytics/getting-started.md) | [Report Builder](/help/analyze/report-builder/home.md) | [Data Warehouse](/help/export/data-warehouse/data-warehouse.md) | [Data Workbench](https://experienceleague.adobe.com/docs/data-workbench/using/home.html?lang=es) | [Archivo de fuentes de datos](/help/export/analytics-data-feed/data-feed-overview.md) | [API de Analytics 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
|---|---|---|---|---|---|---|---|
| **Método de acceso** | [Explorador](/help/analyze/get-started/sys-reqs.md) | [Explorador](/help/analyze/get-started/sys-reqs.md) | [MS Excel para Windows](/help/analyze/report-builder/setup/system-requirements.md) | Realice la configuración a través del explorador. [Más información](/help/analyze/get-started/sys-reqs.md) | [Windows de 64 bits](https://experienceleague.adobe.com/docs/data-workbench/using/install/c-data-workbench-client-install.html?lang=es) | Realice la configuración a través del explorador. [Más información](/help/export/analytics-data-feed/data-feed-overview.md) | Herramientas de API de RESTful. Inicie sesión con las credenciales de Adobe Developer. [Más información](https://developer.adobe.com/analytics-apis/docs/2.0/) |
| **Granularidad de los datos** | Agregado | Agregado | Agregado | Agregado | Visita individual | Visita individual | Agregado |
| **Experience Cloud ID (ECID) disponible** | No | No | No | Sí | Sí | Sí | No |
| **Marca de tiempo disponible** | No | No | No | No | Sí | Sí | No |
| **Nivel de procesamiento** | Procesamiento completo | Procesamiento completo, con [informe en tiempo real](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime.md) independiente | Procesamiento completo, con [informe en tiempo real](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime.md) independiente | Procesamiento completo | Procesamiento completo | Procesamiento completo | Procesamiento completo |
| **Datos del filtro de bots de administrador incluidos** <br> [Más información](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-removal.md) | No | Sí: informe de bots independiente | Sí: informe de bots independiente | No | No | No | No |
| **Aparece poco tráfico (valores exclusivos excedidos)** <br> [Más información](/help/technotes/low-traffic.md) | Sí | Sí | Sí | No | No | No | Sí |
| **Límite de fila visible (antes de la paginación)** | 400 | 200 | 50000 | Sin límite | Sin límite | Sin límite | 50000 |
| **Múltiples grupos de informes** | [Sí](/help/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.md) | Sí, con limitaciones | Sí | No | Sí | No | Sí |
| **Número de desgloses** | Sin límite | Hasta 2 | Hasta 2 | Sin límite | Sin límite | Sin límite | Sin límite, ejecutar en varias consultas |
| **Segmentación** <br> [Más información](/help/components/segmentation/segmentation-workflow/seg-workflow.md) | Sí | Sí | Sí | Sí, con [limitaciones](/help/components/segmentation/seg-reference/seg-compatibility.md) | Sí | No | Sí |
| **Métricas calculadas** <br> [Más información](/help/components/c-calcmetrics/cm-overview.md) | Sí, con [Atribución](/help/analyze/analysis-workspace/attribution/overview.md) | Sí | Sí | No | Sí | No | Sí, con [Atribución](/help/analyze/analysis-workspace/attribution/overview.md) |
| **Canales de marketing** <br> [Más información](/help/components/c-marketing-channels/c-getting-started-mchannel.md) | Sí | Sí | Sí | Sí | Sí | Sí, [va_finder, va_closer](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md) | Sí |
| **Análisis de cohorte** | [Sí](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | No | No | No | Sí | No | No |
| **Atribución** | Sí, con [Atribución](/help/analyze/analysis-workspace/attribution/overview.md) | Limitado | Limitado | No | Sí | No | Sí, con [Atribución](/help/analyze/analysis-workspace/attribution/overview.md) |
| **Revisión** <br> [Más información](/help/analyze/analysis-workspace/curate-share/curate.md) | Sí - Proyecto y grupo de informes virtuales | No | No | No | No | No | Sí - Solo grupo de informes virtuales |
| **Uso compartido de proyectos** <br> [Más información](/help/analyze/analysis-workspace/curate-share/share-projects.md) | Sí, con funciones de proyecto | Sí | Sí | No | Sí | No | No |
| **Envío programado** | Sí | Sí | Sí | Sí | No | Sí | No |
| **Destinos de envío** | Correo electrónico | Correo electrónico | Correo electrónico, FTP, SFTP, [publicación en Microsoft Power BI](/help/analyze/report-builder/c-publish-power-bi/power-bi.md) | Amazon S3, Google Cloud Platform, Azure SAS, Azure RBAC y correo electrónico | - | Amazon S3, Azure RBAC, Azure SAS y Google Cloud Platform | - |
| **Procesamiento del tiempo en la creación de informes con grupos de informes virtuales** <br> [Más información](/help/components/vrs/vrs-report-time-processing.md) | Sí | No | No | No | No | No | Sí |

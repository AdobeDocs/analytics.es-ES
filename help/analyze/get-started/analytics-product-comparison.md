---
description: Requisitos del sistema y comparación de Analysis Workspace, Report Builder, Data Warehouse, y Data Workbench
title: Comparación de productos y requisitos de Analytics
exl-id: 5adc6c10-cbbb-48d5-a7ab-367cbaff5e8a
feature: Analytics Basics
source-git-commit: 9a2d4c582b6a3946b658924851e5b5ada2f5a7ee
workflow-type: ht
source-wordcount: '0'
ht-degree: 100%

---

# Comparación de productos y requisitos de Analytics

Esta página contiene una comparación de varios productos de Adobe Analytics: Analysis Workspace, Report Builder, Data Warehouse, Fuentes de datos y Analytics API 2.0.

Para obtener información sobre qué producto de Adobe Analytics utilizar, consulte [¿Qué herramienta de Adobe Analytics debo usar?](/help/analyze/get-started/which-analytics-tool.md).

| Nombre del producto y vínculo de ayuda | [Analysis Workspace](/help/analyze/analysis-workspace/home.md) | [Report Builder](/help/analyze/report-builder/rb-overview.md) | [Data Warehouse](/help/export/data-warehouse/data-warehouse.md) | [Archivo de fuentes de datos](/help/export/analytics-data-feed/data-feed-overview.md) | [API de Analytics 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
|---|---|---|---|---|---|
| **Método de acceso** | [Explorador](/help/analyze/get-started/sys-reqs.md) | [MS Excel para Windows](/help/analyze/legacy-report-builder/setup/system-requirements.md) | Realice la configuración a través del explorador. [Más información](/help/analyze/get-started/sys-reqs.md) | Realice la configuración a través del explorador. [Más información](/help/export/analytics-data-feed/data-feed-overview.md) | Herramientas de API de RESTful. Inicie sesión con las credenciales de Adobe Developer. [Más información](https://developer.adobe.com/analytics-apis/docs/2.0/) |
| **Granularidad de los datos** | Agregado | Agregado | Agregado | Visita individual | Agregado |
| **Experience Cloud ID (ECID) disponible** | No | No | Sí | Sí | No |
| **Marca de tiempo disponible** | No | No | No | Sí | No |
| **Nivel de procesamiento** | Procesamiento completo | Procesamiento completo, con [informe en tiempo real](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime.md) independiente | Procesamiento completo | Procesamiento completo | Procesamiento completo |
| **Datos del filtro de bots de administrador incluidos** <br> [Más información](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-removal.md) | No | Sí: informe de bots independiente | No | No | No |
| **Aparece poco tráfico (valores exclusivos excedidos)** <br> [Más información](/help/technotes/low-traffic.md) | Sí | Sí | No | No | Sí |
| **Límite de fila visible (antes de la paginación)** | 400 | 50000 | Sin límite | Sin límite | 50000 |
| **Múltiples grupos de informes** | [Sí](/help/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.md) | Sí | No | Sí | No | Sí |
| **Número de desgloses** | Sin límite | Hasta 2 | Sin límite | Sin límite | Sin límite, ejecutar en varias consultas |
| **Segmentación** <br> [Más información](/help/components/segmentation/segmentation-workflow/seg-workflow.md) | Sí | Sí | Sí, con [limitaciones](/help/components/segmentation/seg-reference/seg-compatibility.md) | No | Sí |
| **Métricas calculadas** <br> [Más información](/help/components/c-calcmetrics/cm-overview.md) | Sí, con [Atribución](/help/analyze/analysis-workspace/attribution/overview.md) | Sí, con Atribución | Sí | No | Sí, con [Atribución](/help/analyze/analysis-workspace/attribution/overview.md) |
| **Canales de marketing** <br> [Más información](/help/components/c-marketing-channels/c-getting-started-mchannel.md) | Sí | Sí | Sí | Sí, [va_finder, va_closer](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md) | Sí |
| **Análisis de cohorte** | [Sí](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | Sí | No | No | No |
| **Atribución** | Sí, con [Atribución](/help/analyze/analysis-workspace/attribution/overview.md) | Limitado | No | No | Sí, con [Atribución](/help/analyze/analysis-workspace/attribution/overview.md) | No |
| **Revisión** <br> [Más información](/help/analyze/analysis-workspace/curate-share/curate.md) | Sí - Proyecto y grupo de informes virtuales | No | No | No | Sí. Solo grupo de informes virtuales |
| **Uso compartido de proyectos** <br> [Más información](/help/analyze/analysis-workspace/curate-share/share-projects.md) | Sí, con funciones de proyecto | Sí | No | No | No |
| **Envío programado** | Sí | Sí | Sí | Sí | No |
| **Destinos de envío** | Correo electrónico | Correo electrónico, FTP, SFTP, [publicación en Microsoft Power BI](/help/analyze/legacy-report-builder/c-publish-power-bi/power-bi.md) | Amazon S3, Google Cloud Platform, Azure SAS, Azure RBAC y correo electrónico | Amazon S3, Azure RBAC, Azure SAS y Google Cloud Platform | - |
| **Procesamiento del tiempo en la creación de informes con grupos de informes virtuales** <br> [Más información](/help/components/vrs/vrs-report-time-processing.md) | Sí | No | No | No | Sí |

---
description: Requisitos del sistema y comparación de Analysis Workspace, Reports & Analytics, Ad Hoc Analysis, Report Builder, Data Warehouse y Data Workbench
title: Comparación de productos y requisitos de Analytics
translation-type: tm+mt
source-git-commit: 8a48a5bd9e7ef38ffc90ecb9c640166bb3ac4405
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 54%

---


# Analytics Comparación de productos y requisitos de

Esta página contiene una comparación de varios productos de Adobe Analytics: Analysis Workspace, Informes y análisis, Report Builder, Data Warehouse, Data Workbench, Fuentes de datos y API de Analytics 2.0.

Si no sabe qué producto de Adobe Analytics utilizar, consúltelo [aquí](/help/admin/c-analytics-product-comparison/which-analytics-tool.md).

| Nombre del producto y vínculo de ayuda | [Analysis Workspace](/help/analyze/analysis-workspace/home.md) | [Reports &amp; Analytics](/help/analyze/reports-analytics/getting-started.md) | [Report Builder](/help/analyze/report-builder/home.md) | [Data Warehouse](/help/export/data-warehouse/data-warehouse.md) | [Data Workbench](https://docs.adobe.com/content/help/es-ES/data-workbench/using/home.html) | [Archivo de fuentes de datos](/help/export/analytics-data-feed/data-feed-overview.md) | [API 2.0 de Analytics](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
|---|---|---|---|---|---|---|---|
| **Método de acceso** | [Explorador](/help/admin/sys-reqs.md) | [Explorador](/help/admin/sys-reqs.md) | [MS Excel para Windows](/help/analyze/report-builder/setup/system-requirements.md) | Realice la configuración a través del explorador. [Más información](/help/admin/sys-reqs.md) | [Windows de 64 bits](https://docs.adobe.com/content/help/es-ES/data-workbench/using/install/c-data-workbench-client-install.html) | Realice la configuración a través del explorador. [Más información](/help/export/analytics-data-feed/data-feed-overview.md) | Herramientas de API de RESTful. Inicie sesión con las credenciales de E/S de Adobe. [Más información](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
| **Granularidad de datos** | Agregado | Agregado | Agregado | Agregado | Visita | Visita | Agregado |
| **ID de Experience Cloud (ECID) disponible** | No | No | No | Sí | Sí | Sí | No |
| **Marca de hora disponible** | No | No | No | No | Sí | Sí | No |
| **Nivel de procesamiento** | Completamente procesado | Completamente procesado, con informe separado en tiempo [real](/help/components/c-real-time-reporting/realtime.md) | Completamente procesado, con informe separado en tiempo [real](/help/components/c-real-time-reporting/realtime.md) | Completamente procesado | Completamente procesado | Completamente procesado | Completamente procesado |
| **Se incluyen los datos del filtro de bots de administración** <br> [Más información](/help/admin/admin/bot-removal/bot-removal.md) | No | Sí: informe de bots independiente | Sí: informe de bots independiente | No | No | No | No |
| **Aparece poco tráfico (se excedió la cantidad de valores exclusivos)** <br> [Más información](/help/technotes/low-traffic.md) | Sí | Sí | Sí | No | No | No | Sí |
| **Límite de fila visible (antes de la paginación)** | 400 | 200 | 50000 | Sin límite | Sin límite | Sin límite | 50000 |
| **Varios grupos de informes** | [Sí](/help/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.md) | Sí, con limitaciones | Sí | No | Sí | No | Sí |
| **Número de desgloses** | Sin límite | Hasta 2 | Hasta 2 | Sin límite | Sin límite | Sin límite | Sin límite, ejecutar en varias consultas |
| **Segmentación** <br> [Más información](/help/components/segmentation/segmentation-workflow/seg-workflow.md) | Sí | Sí | Sí | Sí, con [limitaciones](/help/components/segmentation/seg-reference/seg-compatibility.md) | Sí | No | Sí |
| **Métricas calculadas** <br> [Más información](/help/components/c-calcmetrics/cm-overview.md) | Sí, con [Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md) | Sí | Sí | No | Sí | No | Sí, con [Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md) |
| **Canales de marketing** <br> [Más información](/help/components/c-marketing-channels/c-getting-started-mchannel.md) | Sí | Sí | Sí | Sí | Sí | Sí: [va_finder, va_close](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md) | Sí |
| **Análisis de cohorte** | [Sí](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | No | No | No | Sí | No | No |
| **Atribución** | Sí, con [Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md) | Limitado | Limitado | No | Sí | No | Sí, con [Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md) |
| **Funciones de analista virtual** <br> [Más información](/help/analyze/analysis-workspace/virtual-analyst/overview.md) | Sí | No | No | No | No | No | Sí |
| **Depuración** <br> [Más información](/help/analyze/analysis-workspace/curate-share/curate.md) | Sí - Proyecto y VRS | No | No | No | No | No | Sí: solo VRS |
| **Uso compartido de proyectos** <br> [Más información](/help/analyze/analysis-workspace/curate-share/share-projects.md) | Sí, con funciones de proyecto | Sí | Sí | No | Sí | No | No |
| **Envío programado** | Sí | Sí | Sí | Sí | No | Sí | No |
| **Destinos de envío** | Correo electrónico  | Correo electrónico  | Correo electrónico, FTP, SFTP, [publicar en Microsoft PowerBI](/help/analyze/report-builder/c-publish-power-bi/power-bi.md) | Correo electrónico, FTP. Póngase en contacto con el Servicio de atención al cliente para obtener asistencia técnica de destino adicional, incluidos SFTP, Azure Blob y Amazon S3 | - | FTP, SFTP, Azure Blob, Amazon S3 | - |
| **Procesamiento de tiempo del informe VRS** <br> [Más información](/help/components/vrs/vrs-report-time-processing.md) | Sí | No | No | No | No | No | Sí |

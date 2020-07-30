---
description: Requisitos del sistema y comparación de Analysis Workspace, Reports & Analytics, Ad Hoc Analysis, Report Builder, Data Warehouse y Data Workbench
title: Comparación de productos y requisitos de Analytics
translation-type: tm+mt
source-git-commit: 54d6b4c2993c5b0391b9243c76661db1da4087b8
workflow-type: tm+mt
source-wordcount: '714'
ht-degree: 54%

---


# Analytics Comparación de productos y requisitos de 

Esta página contiene una comparación de varios productos de Adobe Analytics: Analysis Workspace, Informes y Analytics, Report Builder, Data warehouse, Data Workbench, Fuentes de datos y Analytics API 2.0.

Si no sabe qué producto de Adobe Analytics utilizar, consúltelo [aquí](/help/admin/c-analytics-product-comparison/which-analytics-tool.md).

| Nombre del producto y vínculo de ayuda | [Analysis Workspace](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/home.html) | [Reports &amp; Analytics](https://docs.adobe.com/content/help/es-ES/analytics/analyze/reports-analytics/getting-started.translate.html) | [Report Builder](https://docs.adobe.com/content/help/es-ES/analytics/analyze/report-builder/home.translate.html) | [Data Warehouse](https://docs.adobe.com/content/help/es-ES/analytics/export/data-warehouse/data-warehouse.html) | [Data Workbench](https://docs.adobe.com/content/help/es-ES/data-workbench/using/home.html) | [Archivo de fuentes de datos](https://docs.adobe.com/content/help/es-ES/analytics/export/analytics-data-feed/data-feed-overview.html) | [Analytics API 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
|---|---|---|---|---|---|---|---|
| **Método de acceso** | [Explorador](https://docs.adobe.com/content/help/es-ES/analytics/admin/sys-reqs.html) | [Explorador](https://docs.adobe.com/content/help/es-ES/analytics/admin/sys-reqs.html) | [MS Excel para Windows](https://docs.adobe.com/content/help/es-ES/analytics/analyze/report-builder/report-builder-setup/system-requirements.html) | Realice la configuración a través del explorador. [Más información](https://docs.adobe.com/content/help/es-ES/analytics/admin/sys-reqs.html) | [Windows de 64 bits](https://docs.adobe.com/content/help/es-ES/data-workbench/using/install/c-data-workbench-client-install.html) | Realice la configuración a través del explorador. [Más información](https://docs.adobe.com/content/help/es-ES/analytics/export/analytics-data-feed/data-feed-overview.html) | Herramientas de API de RESTful. Inicie sesión con las credenciales de E/S de Adobe. [Más información](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
| **Granularidad de datos** | Agregado | Agregado | Agregado | Agregado | Visita | Visita | Agregado |
| **Experience Cloud ID (ECID) disponible** | No | No | No | Sí | Sí | Sí | No |
| **Marca de hora disponible** | No | No | No | No | Sí | Sí | No |
| **Nivel de procesamiento** | Completamente procesado | Completamente procesado, con informe separado en tiempo [real](https://docs.adobe.com/content/help/en/analytics/components/real-time-reporting/realtime.html) | Completamente procesado, con informe separado en tiempo [real](https://docs.adobe.com/content/help/en/analytics/components/real-time-reporting/realtime.html) | Completamente procesado | Completamente procesado | Completamente procesado | Completamente procesado |
| **Datos del filtro de bots de administración incluidos** <br>[Más información](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/bot-removal/bot-removal.html) | No | Sí: informe de bots independiente | Sí: informe de bots independiente | No | No | No | No |
| **Se muestra** poco tráfico (se excedió la cantidad de valores exclusivos) <br>[Más información](https://docs.adobe.com/content/help/es-ES/analytics/technotes/low-traffic.html) | Sí | Sí | Sí | No | No | No | Sí |
| **Límite de fila visible (antes de la paginación)** | 400 | 200 | 50000 | Sin límite | Sin límite | Sin límite | 50000 |
| **Varios grupos de informes** | [Sí](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.html) | Sí, con limitaciones | Sí | No | Sí | No | Sí |
| **Número de desgloses** | Sin límite | Hasta 2 | Hasta 2 | Sin límite | Sin límite | Sin límite | Sin límite, ejecutar en varias consultas |
| **Segmentación** <br>[Más información](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-workflow.html) | Sí | Sí | Sí | Sí, con [limitaciones](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segment-reference/seg-compatibility.html) | Sí | No | Sí |
| **Métricas** calculadas <br>[Más información](https://docs.adobe.com/content/help/es-ES/analytics/components/calculated-metrics/cm-overview.html) | Sí, con [Attribution IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/attribution/overview.html) | Sí | Sí | No | Sí | No | Sí, con [Attribution IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/attribution/overview.html) |
| **Canales** de marketing <br>[Más información](https://docs.adobe.com/content/help/es-ES/analytics/components/marketing-channels/c-getting-started-mchannel.html) | Sí | Sí | Sí | Sí | Sí | Sí: [va_finder, va_close](https://docs.adobe.com/content/help/en/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html) | Sí |
| **análisis de cohorte** | [Sí](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.html) | No | No | No | Sí | No | No |
| **Atribución** | Sí, con [Attribution IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/attribution/overview.html) | Limitado | Limitado | No | Sí | No | Sí, con [Attribution IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/attribution/overview.html) |
| **Funciones** de analista virtual <br>[Más información](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/virtual-analyst/overview.html) | Sí | No | No | No | No | No | Sí |
| **Curation** <br>[Más información](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/curate-share/curate.html) | Sí - Proyecto y VRS | No | No | No | No | No | Sí: solo VRS |
| **Uso compartido** de proyectos <br>[Más información](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/curate-share/share-projects.html) | Sí, con funciones de proyecto | Sí | Sí | No | Sí | No | No |
| **Envío programado** | Sí | Sí | Sí | Sí | No | Sí | No |
| **Destinos de Envío** | Correo electrónico | Correo electrónico | Correo electrónico, FTP, SFTP, [publicar en Microsoft PowerBI](https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/publish-powerbi/power-bi.html) | Correo electrónico, FTP. Póngase en contacto con el Servicio de atención al cliente para obtener asistencia técnica de destino adicional, incluidos SFTP, Azure Blob y Amazon S3 | - | FTP, SFTP, Azure Blob, Amazon S3 | - |
| **Procesamiento** del tiempo del informe VRS <br>[Más información](https://docs.adobe.com/content/help/es-ES/analytics/components/virtual-report-suites/vrs-report-time-processing.html) | Sí | No | No | No | No | No | Sí |

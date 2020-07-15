---
description: Requisitos del sistema y comparación de Analysis Workspace, Reports & Analytics, Ad Hoc Analysis, Report Builder, Data Warehouse y Data Workbench
title: Comparación de productos y requisitos de Analytics
translation-type: tm+mt
source-git-commit: cb3948f03e65edf18b7f3c54c891b77629b41dc0
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 83%

---


# Analytics Comparación de productos y requisitos de 

Requisitos del sistema y comparación de Analysis Workspace, Informes y Analytics, Creador de informes, Data warehouse, Data Workbench, Analytics API 2.0, Fuentes de datos y Customer Journey Analytics.

Si no sabe qué producto de Adobe Analytics utilizar, consúltelo [aquí](/help/admin/c-analytics-product-comparison/which-analytics-tool.md).

| Nombre del producto y vínculo de ayuda | [Analysis Workspace](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/home.html) | [Reports &amp; Analytics](https://docs.adobe.com/content/help/es-ES/analytics/analyze/reports-analytics/getting-started.translate.html) | [Report Builder](https://docs.adobe.com/content/help/es-ES/analytics/analyze/report-builder/home.translate.html) | [Data Warehouse](https://docs.adobe.com/content/help/es-ES/analytics/export/data-warehouse/data-warehouse.html) | [Data Workbench](https://docs.adobe.com/content/help/es-ES/data-workbench/using/home.html) | Analytics API 2.0 | Archivo de fuentes de datos | Customer Journey Analytics |
|---|---|---|---|---|---|---|
| **Método de acceso** | Solución de navegador para crear proyectos de análisis sólidos y personalizados y democratizar las perspectivas. | Solución de navegador para el análisis digital. | La solución de navegador que genera informes en formato .csv. Puede generar archivos de formato Tableau. | Herramienta de análisis multicanal avanzado, como modelado de atribución personalizado, análisis predictivo y análisis integral de clientes. |  |  |  |
| **Desgloses de informes** | Sin límite | Hasta 2 correlaciones | Hasta 2 correlaciones | Realiza desgloses completamente ampliados, ilimitados y por segmento. | Sin límite |  |  |  |
| **Comparaciones por segmentos** | Sin límite | Hasta 2 segmentos | Sin límite (apilamiento de solicitudes de datos) | 1 segmento. Admite varios segmentos (ilimitados). | Sin límite |  |  |  |
| **Límite de salida de línea** | 400 | 200 | 50 000 | Sin límite | Personalizable |  |  |  |
| **** Límites de valores únicos (en informes de propiedades/eVar) | 500K-2MM | 500K-2MM | 500K-2MM | Sin límite | Personalizable |  |  |  |
| **Canal/Rutas** | Sí: [Visitas en el orden previsto](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow.html)/[Flujo](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/visualizations/flow/flow.html) | [Sí](https://docs.adobe.com/content/help/es-ES/analytics/analyze/reports-analytics/reports.html) | Sí | No | Sí |  |  |  |
| **Análisis avanzado de trayectos de los clientes** | Yes: [Customer Journey Analytics](https://docs.adobe.com/content/help/es-ES/analytics-platform/using/cja-landing.html) | No | No | No | Sí |  |  |  |
| **Análisis de cohorte** | [Sí](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.html) | No | No | No | Sí |  |  |  |
| **Atribución avanzada** | Sí: [IQ de atribución](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/attribution-iq.html) | Con límite: primero/último/lineal | Con límite: primero/último/lineal | Con límite: primero/último/lineal | Sí |  |  |  |
| **Opciones de visualización mejorada** | [Sí](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html) | No | Sí | No | Sí |  |  |  |
| **Diseño personalizable** | [Sí](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/home.html) | Sí: [Tableros](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/dashboard.html) | [Sí](https://docs.adobe.com/content/help/es-ES/analytics/analyze/report-builder/layout/configure-the-custom-layout.html) | Se ordenan resultados por desglose o métricas. | Sí |  |  |  |
| **** Revisión de proyecto (se simplifican informes para los no analistas) | [Sí](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/curate-share/curate.html) | No | Sí | No | Sí |  |  |  |
| **Uso compartido de proyecto** | [Sí: todos/todos los usuarios](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/curate-share/curate.html) | [Sí: todos/todos los usuarios](https://docs.adobe.com/content/help/es-ES/analytics/analyze/reports-analytics/scheduling.html) | Sí: todos/todos los usuarios | No | Sí |  |  |  |
| **Envío de informes** programados | [Sí](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/curate-share/schedule-projects.html) | [Sí](https://docs.adobe.com/content/help/es-ES/analytics/analyze/reports-analytics/scheduling.html) | [Sí](https://docs.adobe.com/content/help/es-ES/analytics/analyze/report-builder/t-schedule-a-data-request.html) | Sí | Sí |  |  |  |
| **Requisitos del sistema** | <br>[ExploradorMás...](https://docs.adobe.com/content/help/es-ES/analytics/admin/sys-reqs.html) | <br>[ExploradorMás...](https://docs.adobe.com/content/help/es-ES/analytics/admin/sys-reqs.html) | Windows, MS<br>[ExcelMás...](https://docs.adobe.com/content/help/es-ES/analytics/analyze/report-builder/report-builder-setup/system-requirements.html) | Navegador y programa para abrir archivos .csv como MS Excel. Puede generar archivos de formato Tableau. | Windows 64 bit, good graphics adapter for OpenGL 3.2 [More...](https://docs.adobe.com/content/help/es-ES/data-workbench/using/install/c-data-workbench-client-install.html) |  |  |  |
| **Compatibilidad con grupos de informes virtuales (procesamiento de tiempo de informes)** | Sí | Sí | Sí | No | Sí? |  |  |  |
| **Múltiples grupos de informes** | Sí | No | No | No | Sí? |  |  |  |
| **Métricas calculadas** | Sí | Sí | Sí | Sí | Sí |  |  |  |
| **Compatibilidad con Canales de marketing** | Sí | Sí | Sí | ? | ? |  |  |  |
| **Nivel de granularidad** |  |  |  |  |  |  |  |  |
| **Detección de anomalías** | Sí | No |  |  |  |  |  |  |
| **Análisis de contribución** | Sí | No | No | No | Sí |  |  |  |
| **Tipos de segmentos** |  |  |  |  |  |  |  |  |
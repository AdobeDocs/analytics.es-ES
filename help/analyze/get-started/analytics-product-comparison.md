---
description: Requisitos del sistema y comparación de Analysis Workspace, Report Builder, Data Warehouse, y Data Workbench
title: Comparación de productos y requisitos de Analytics
exl-id: 5adc6c10-cbbb-48d5-a7ab-367cbaff5e8a
feature: Analytics Basics
TQID: https://experienceleague.adobe.com/VQgK6DUSlz-UA3zk-Q18-QOAI5M6xfK7KqBYwW56j6w
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: a421fb65-2c82-457a-921c-28c46b697a39id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: ac8a38fa-dec3-4581-8f64-178fde9f64e8id: af53ada8-1b7d-4929-ac91-ac971dd20ec7id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705cid: dcae653e-62c6-4cc8-84e6-ee110b848296id: e9cb007b-c8b7-4975-bc81-11a788c535faid: ef60b66e-5984-4336-ba72-6d978b1b6f87id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 530
ht-degree: 67%

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
| **Nivel de procesamiento** | Procesamiento completo | Procesamiento completo, con [informe en tiempo real](/help/admin/tools/manage-rs/edit-settings/realtime/realtime.md) independiente | Procesamiento completo | Procesamiento completo | Procesamiento completo |
| **Datos del filtro de bots de administrador incluidos** <br> [Más información](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-removal.md) | No | Sí: informe de bots independiente | No | No | No |
| **Aparece poco tráfico (valores exclusivos excedidos)** <br> [Más información](/help/technotes/low-traffic.md) | Sí | Sí | No | No | Sí |
| **Límite de fila visible (antes de la paginación)** | 400 | 50000 | Ilimitado | Ilimitado | 50000 |
| **Múltiples grupos de informes** | [Sí](/help/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.md) | Sí | No | Sí | No |
| **Número de desgloses** | Sin límite | Hasta 2 | Ilimitado | Ilimitado | Sin límite, ejecutar en varias consultas |
| **Segmentación** <br> [Más información](/help/components/segmentation/segmentation-workflow/seg-workflow.md) | Sí | Sí | Sí, con [limitaciones](/help/components/segmentation/seg-reference/seg-compatibility.md) | No | Sí |
| **Métricas calculadas** <br> [Más información](/help/components/calculated-metrics/cm-overview.md) | Sí, con [Atribución](/help/analyze/analysis-workspace/attribution/overview.md) | Sí, con Atribución | Sí | No | Sí, con [Atribución](/help/analyze/analysis-workspace/attribution/overview.md) |
| **Canales de marketing** <br> [Más información](/help/components/c-marketing-channels/c-getting-started-mchannel.md) | Sí | Sí | Sí | Sí, [va_finder, va_closer](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md) | Sí |
| **Análisis de cohorte** | [Sí](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | Sí | No | No | No |
| **Atribución** | Sí, con [Atribución](/help/analyze/analysis-workspace/attribution/overview.md) | Limitado | No | No | Sí, con [Atribución](/help/analyze/analysis-workspace/attribution/overview.md) |
| **Revisión** <br> [Más información](/help/analyze/analysis-workspace/curate-share/curate.md) | Sí - Proyecto y grupo de informes virtuales | No | No | No | Sí. Solo grupo de informes virtuales |
| **Uso compartido de proyectos** <br> [Más información](/help/analyze/analysis-workspace/curate-share/share-projects.md) | Sí, con funciones de proyecto | Sí | No | No | No |
| **Envío programado** | Sí | Sí | Sí | Sí | No |
| **Destinos de envío** | Correo electrónico | Correo electrónico, FTP, SFTP, [publicación en Microsoft Power BI](/help/analyze/legacy-report-builder/c-publish-power-bi/power-bi.md) | Amazon S3, Google Cloud Platform, Azure SAS, Azure RBAC y correo electrónico | Amazon S3, Azure RBAC, Azure SAS y Google Cloud Platform | - |
| **Procesamiento del tiempo en la creación de informes con grupos de informes virtuales** <br> [Más información](/help/components/vrs/vrs-report-time-processing.md) | Sí | No | No | No | Sí |
| **Informes geográficos y tecnológicos** | Sí <p>Utiliza valores medios en lugar de campos posteriores. La lógica de primera visita se basa en `post_cust_hit_time_gmt` en lugar de en `visit_page_num=1`. Los resultados pueden diferir de otras herramientas si la IP cambia a mitad de la visita, las visitas llegan sin orden o las visitas cruzan los límites del mes.</p> | Sí <p>Utiliza valores medios en lugar de campos posteriores. La lógica de primera visita se basa en `post_cust_hit_time_gmt` en lugar de en `visit_page_num=1`. Los resultados pueden diferir de otras herramientas si la IP cambia a mitad de la visita, las visitas llegan sin orden o las visitas cruzan los límites del mes.</p> | Sí <p>Utiliza valores post y `visit_page_num=1` para determinar la primera visita. Aplica el valor de la primera visita a todas las visitas individuales de la visita para estas dimensiones.</p> | Sí <p>Utiliza valores post y `visit_page_num=1` para determinar la primera visita. Aplica el valor de la primera visita a todas las visitas individuales de la visita para estas dimensiones.</p> | Sí <p>Utiliza valores medios en lugar de campos posteriores. La lógica de primera visita se basa en `post_cust_hit_time_gmt` en lugar de en `visit_page_num=1`. Los resultados pueden diferir de otras herramientas si la IP cambia a mitad de la visita, las visitas llegan sin orden o las visitas cruzan los límites del mes.</p> |

---
description: Recursos y vínculos para la API de informes.
title: API de informes de Analytics
uuid: 68ec3490-6e47-4606-860d-dd5e89c574a1
feature: API
role: Developer
exl-id: 003a8b83-6ef0-4313-903a-b76078558d55
source-git-commit: a9d892ab8caaeb797fbbd9b5aa136c5dab76f8bd
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 73%

---

# API de informes de Analytics

La documentación de las API de Adobe Analytics se encuentra en [Adobe I/O](https://adobe.io/analytics-apis/docs).

## Comparación de las API de Analytics

| **Tipo de API** | **Procesamiento total** | **Tiempo real** | **Livestream** | **Data Warehouse** |
| --- | --- | --- | --- | --- |
| **Descripción** | Datos totalmente procesados y finalizados disponibles en todas las interfaces de Analytics. | Métricas parcialmente procesadas y limitadas disponibles unos segundos después de recopilarse. | Datos de visitas parcialmente procesados disponibles unos segundos después de recopilarse. | Datos totalmente procesados y finalizados que se utilizan para extraer exportaciones de datos de gran volumen. |
| [**Latencia**](/help/technotes/latency.md) | 30 a 90 minutos | De segundos a 10 minutos | De segundos a 10 minutos | Más de 90 minutos |
| **Finalización del procesamiento** | Completa | Parcial | Parcial | Completa |
| **Interfaces de generación de informes** | Analysis Workspace, Reports &amp; Analytics, Report Builder, API | Informe en tiempo real en Reports &amp; Analytics, Report Builder, API 1.4 | Solo API | Data Warehouse, API |
| **Granularidad de los datos** | Resumida | Resumida | Nivel de visita | Resumida |
| **Procesamiento de perfiles del visitante** | Sí | No | No | Sí |
| **Compatibilidad con segmentos** | Sí | No | No | Parcial |

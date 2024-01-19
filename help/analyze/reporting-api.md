---
description: Recursos y vínculos para la API de informes.
title: API de informes de Analytics
uuid: 68ec3490-6e47-4606-860d-dd5e89c574a1
feature: API
role: Developer
exl-id: 003a8b83-6ef0-4313-903a-b76078558d55
source-git-commit: d173a6c6c9751a86f4218ec842da17da14f8485b
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 90%

---

# API de informes de Analytics

La documentación de las API de Adobe Analytics se encuentra en [Adobe Developer](https://developer.adobe.com/analytics-apis/docs/2.0/).

## Comparación de las API de Analytics

| **Tipo de API** | **Procesamiento total** | **Tiempo real** | **Livestream** | **Data Warehouse** |
| --- | --- | --- | --- | --- |
| **Descripción** | Datos totalmente procesados y finalizados disponibles en todas las interfaces de Analytics. | Métricas parcialmente procesadas y limitadas disponibles unos segundos después de recopilarse. | Datos de visitas parcialmente procesados disponibles unos segundos después de recopilarse. | Datos totalmente procesados y finalizados que se utilizan para extraer exportaciones de datos de gran volumen. |
| [**Latencia**](/help/technotes/latency.md) | 30 a 90 minutos | De segundos a 10 minutos | De segundos a 10 minutos | Más de 90 minutos |
| **Finalización del procesamiento** | Completa | Parcial | Parcial | Completa |
| **Interfaces de generación de informes** | Analysis Workspace, Report Builder, API | Informe en tiempo real en Report Builder, API 1.4 | Solo API | API de Data Warehouse |
| **Granularidad de los datos** | Resumida | Resumida | Nivel de visita | Resumida |
| **Procesamiento del perfil del visitante** | Sí | No | No | Sí |
| **Compatibilidad con segmentos** | Sí | No | No | Parcial |

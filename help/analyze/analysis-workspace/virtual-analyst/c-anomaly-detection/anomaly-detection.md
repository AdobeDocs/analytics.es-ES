---
description: Puede ver y analizar las anomalías de datos en contexto, dentro de Analysis Workspace.
title: Resumen de la Detección de anomalías
feature: Anomaly Detection
role: User, Admin
exl-id: b1625206-c774-40ef-9d92-25ee8ff1478d
source-git-commit: 10ae8213b8745439ab5968853f655a1176b8c38a
workflow-type: ht
source-wordcount: '258'
ht-degree: 100%

---

# Resumen de la Detección de anomalías

Puede ver y analizar las anomalías de datos en contexto, dentro de Analysis Workspace.

>[!VIDEO](https://video.tv.adobe.com/v/25444/?quality=12)

>[!IMPORTANT]
>
>La característica Detección de anomalías se ha eliminado del conjunto de funciones de Reports &amp; Analytics, y ahora solo está disponible en Analysis Workspace. Tenga en cuenta que los clientes de Adobe Analytics Select y Adobe Analytics Foundation solo tienen acceso a la Detección de anomalías de “granularidad diaria” en Workspace. Para obtener más información, consulte la información relativa a los [derechos de Detección de anomalías y Análisis de contribución](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.md#section_9278D58F21A840AA9B1ED1BD07A1EF0A).

La Detección de anomalías constituye un método estadístico para determinar el cambio experimentado en una métrica determinada respecto a los datos anteriores.

La detección de anomalías permite separar las “señales verdaderas” del “ruido” y así identificar los posibles factores que contribuyeron a hacer saltar estas señales o anomalías. En otras palabras, le permite identificar las fluctuaciones estadísticas que son importantes y las que no lo son. A continuación, podrá identificar la causa raíz de una anomalía real. Además, se pueden consultar predicciones de métricas (KPI) fiables.

Algunos ejemplos de anomalías que puede investigar son:

* Caídas drásticas en un valor de pedido promedio
* Picos en pedidos con ingresos bajos
* Picos o caídas en registros de prueba
* Caídas en vistas de páginas de aterrizaje
* Picos en eventos de almacenamiento de vídeo
* Picos en tasas de bits de vídeo bajas

Tanto la detección de anomalías como el [análisis de contribución](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html?lang=es) son flujos de trabajo principales en Analysis Workspace. Puede ejecutar el análisis de contribución para cualquier anomalía diaria e incrustar el resultado en su proyecto de Analysis Workspace.

El algoritmo de Detección de anomalías de Analysis Workspace incluye:

* Compatibilidad con las granularidades horaria, semanal y mensual, además de con la granularidad diaria.
* Diferenciación por temporadas (como el “Black Friday”) y períodos vacacionales.

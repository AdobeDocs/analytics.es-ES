---
description: Puede ver y analizar las anomalías de datos en contexto, dentro de Analysis Workspace.
seo-description: Puede ver y analizar las anomalías de datos en contexto, dentro de Analysis Workspace.
seo-title: Resumen de la Detección de anomalías
title: Resumen de la Detección de anomalías
uuid: 991fde08-198c-4410-9606-d5a4f3dd8339
translation-type: tm+mt
source-git-commit: ca9f1ed00295b556250894ae4e7fa377ef8a593d

---


# Resumen de la Detección de anomalías

Puede ver y analizar las anomalías de datos en contexto dentro de Analysis Workspace.

[Detección de anomalías en YouTube](https://www.youtube.com/watch?v=krXyQCjXoeU&index=63&list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) (4:53)

[Análisis de contribución en YouTube](https://www.youtube.com/watch?v=MbpeJIADtGk&index=64&list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) (3:20)

> [!IMPORTANT] La detección de anomalías solo está disponible en Analysis Workspace. Los clientes de Adobe Analytics Select y Foundation solo tienen acceso a la detección de anomalías de "granularidad diaria" en Workspace. Para obtener más información, consulte la información relativa a los [derechos de Detección de anomalías y Análisis de contribución](../contribution-analysis/ca-tokens.md).

La detección de anomalías constituye un método estadístico para determinar el cambio experimentado en una métrica determinada respecto a los datos anteriores.

La detección de anomalías permite separar las “señales verdaderas” del “ruido” y así identificar los posibles factores que contribuyeron a hacer saltar estas señales o anomalías. En otras palabras, le permite identificar las fluctuaciones estadísticas que son importantes y las que no lo son. A continuación, podrá identificar la causa raíz de una anomalía real. Además, se pueden consultar predicciones de métricas (KPI) fiables.

Algunos ejemplos de anomalías que puede investigar son:

* Caídas drásticas en un valor de pedido promedio
* Picos en pedidos con ingresos bajos
* Picos o caídas en registros de prueba
* Caídas en vistas de páginas de aterrizaje
* Picos en eventos de almacenamiento de vídeo
* Picos en tasas de bits de vídeo bajas

Tanto la detección de anomalías como el [análisis de contribución](https://marketing.adobe.com/resources/help/en_US/analytics/contribution/ca_main.html) son flujos de trabajo principales en Analysis Workspace. Puede ejecutar el análisis de contribución para cualquier anomalía diaria e incrustar el resultado en su proyecto de Analysis Workspace.

El algoritmo de Detección de anomalías de Analysis Workspace incluye:

* Compatibilidad con las granularidades horaria, semanal y mensual, además de con la granularidad diaria.
* Diferenciación por temporadas (como el “Black Friday”) y períodos vacacionales.

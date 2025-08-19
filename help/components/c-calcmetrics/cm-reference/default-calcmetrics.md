---
description: Adobe proporciona varias métricas calculadas que puede utilizar. En esta página se enumeran dichas métricas y los usos previstos.
title: Métricas calculadas predeterminadas
feature: Calculated Metrics
exl-id: 84468e63-f967-41cd-8084-525b1b90957a
source-git-commit: 7609ecb3c34fb0bc8293fc1ecd409cfabb327295
workflow-type: tm+mt
source-wordcount: '758'
ht-degree: 98%

---

# Métricas calculadas predeterminadas

Adobe Analytics proporciona varias métricas calculadas para cubrir los casos de uso más comunes. Estas métricas calculadas están disponibles de forma predeterminada en Analysis Workspace.

A continuación se muestra una lista de cada métrica calculada proporcionada por Adobe, con su función deseada y la fórmula subyacente utilizada para calcularla:

>[!NOTE]
>
>Además de las métricas calculadas predeterminadas que se describen en esta página, también puede añadir métricas calculadas adicionales a un grupo de informes.
>
>Puede realizar lo siguiente:
>
> * Agregue métricas calculadas predeterminadas para los servicios de medios de streaming, tal como se describe en [Métricas calculadas](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/variables/calculated-metrics.html?lang=es)
> * Crear métricas calculadas personalizadas a partir de métricas existentes, tal como se describe en [Métricas calculadas y métricas calculadas avanzadas](/help/components/c-calcmetrics/cm-overview.md).
>

>[!TIP]
>
>Use el [Diccionario de datos](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) para examinar con más detalle la definición de una métrica calculada predeterminada y los componentes individuales que componen dicha definición.
>



| Nombre de métrica calculada | Función | Fórmula |
| --- | --- | --- |
| Clics en enlaces de adquisición | Número de veces que las personas hacen clic en un vínculo diseñado para conducir el tráfico al sitio. | `[Campaign Click-throughs]` |
| Acciones | Número total de acciones que se llevan a cabo en la aplicación | `[Has an Action] (segment)`<br>`[Custom Link Instances] (metric)` |
| Usuarios de la aplicación | Número total de usuarios de una aplicación móvil | `[Mobile App Users] (segment)`<br>`[Unique Visitors] (metric)` |
| Longitud promedio de sesión (móvil) | Promedio de tiempo que los visitantes pasan en el sitio durante una sola sesión. | En blanco |
| Promedio de tiempo en el sitio | Cantidad promedio de tiempo que un visitante pasa en el sitio antes de salir o navegar. | `[Average Time Spent on Site (Seconds)]` |
| Tasa de salida hacia otro sitio | La proporción de visitas que contenían exactamente una visita en comparación con el número de visitas en esa página. Esta métrica puede ayudar a comprender qué elementos de dimensión tienen la tasa de salida hacia otro sitio más alta o para ver una tasa de salida hacia otro sitio total agregada a lo largo del tiempo. | `[Bounces] / [Entries]` |
| Proporción de vistas de página de bots | La proporción de vistas de página de bots comparada con la cantidad total de vistas de página. | `[Bot Page Views] / [Page Views]` |
| Velocidad del contenido | La velocidad a la que se crea y publica nuevo contenido en el sitio y la velocidad con la que genera la participación del usuario. | `[Page Views] / [Visits]` |
| Tasa de conversión | Porcentaje de visitantes que realizaron una acción deseada, como una compra. | `[Orders] / [Visits]` |
| Tasa de entrada | Porcentaje de visitantes que entraron al sitio en una página determinada, comparado con el número total de sesiones en el sitio. | `[Entries] / [Visits]` |
| Visitantes únicos estimados (ITP 2.1) | Para los visitantes de ITP (usuarios en navegadores Safari), divida los visitantes únicos entre 2 o menos. Esta métrica calculada supone que se configuran cookies mediante JavaScript del lado del cliente (no mediante una implementación CNAME). Las implementaciones que establecen cookies mediante JavaScript del lado del cliente se vieron afectadas a partir de ITP 2.1. Consulte [Prevención inteligente del seguimiento](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) para obtener más información. | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) segment] / [Unique Visitors metric + Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) segment]` |
| Alcance del ID de Experience Cloud | Porcentaje de visitantes que tienen un ID de Experience Cloud. | `[Visitors with Experience Cloud ID] / [Unique Visitors]` |
| Tasa de salida | Porcentaje de visitantes que abandonan el sitio después de ver una página en particular. | `[Exits] / [Visits]` |
| Visitantes únicos/Visitantes únicos de ITP 2.1 | El porcentaje de visitantes únicos que utilizan un explorador afectado por las limitaciones de cookies de ITP 2.1. | `[Unique Visitors metric with ITP Visitors segment] / [Unique Visitors]` |
| Asistencias de pedidos | Número de veces que un canal o fuente contribuyó al recorrido de un cliente hacia la realización de una compra, pero no resultó en la compra final. | `[Orders (Visit Participation)] - [Orders]` |
| Pedidos / Visitas | El porcentaje de visitas al sitio que genera una transacción completada. | `[Orders] / [Visits]` |
| Pedidos / Visitante | El número promedio de pedidos o transacciones generados por cada visitante individual del sitio | `[Orders] / [Unique Visitors]` |
| Vistas de página/Visitantes únicos estimados (ITP 2.1) | Número promedio de páginas vistas para Visitantes únicos estimados (ITP 2.1). | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) segment] / [Unique Visitors (metric) with Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) segment]` |
| Vistas de página / Visitante único | El promedio de páginas vistas por cada visitante único del sitio. | `[Page Views] / [Unique Visitors]` |
| Vistas de página / Visitas | El promedio de páginas que ve un usuario durante una sola visita al sitio. | `[Page Views] / [Visits]` |
| Velocidad de página | Número de vistas de página adicionales que genera un fragmento de contenido. Esta métrica puede ayudarle a determinar qué contenido genera participación adicional. | `[Page Views] / [Visits]` |
| Recargas / Vistas de página | El porcentaje de vistas de página que resultaron en una recarga o actualización de la página. | `[Reloads] / [Page Views]` |
| Ingresos / Pedido | Cantidad promedio de ingresos generados por cada transacción o pedido completado en el sitio. | `[Revenue] / [Orders]` |
| Ingresos / Visitas | Cantidad promedio de ingresos generados por una sola visita al sitio. | `[Revenue] / [Visits]` |
| Ingresos / Visitante | Cantidad promedio de ingresos generados por cada visitante individual del sitio. | `[Revenue] / [Unique Visitors]` |
| Vistas de estado | Número de visualizaciones de los distintos estados o pantallas de la aplicación | `[Mobile App Users] (segment)`<br>`[Page Views] (metric)` |
| Tiempo empleado/usuario (estado) | Cantidad de tiempo que el visitante promedio pasa en un estado determinado mientras está en el sitio | `[Mobile App Users] (segment)`<br>`[Time Spent per Visitor (Seconds)] (metric)` |
| Visitantes únicos / Visitantes únicos que regresan después de 7 días | Porcentaje de visitantes únicos que regresan después de un período de 7 días o más. | `[Unique Visitors metric with Users returning after 7 days segment] / [Unique Visitors]` |
| Usuarios (móvil) | Número total de usuarios de una aplicación móvil | `[Mobile App Users] (segment)`<br>`[Unique Visitors] (metric)` |
| Visitas / Visitante | El promedio de visitas que realiza un visitante único al sitio. | `[Visits] / [Unique Visitors]` |
| Tasa de salida hacia otro sitio ponderada | Función | `IF([Visits] > PERCENTILE([Visits]), [Bounce Rate], 0)` |

{style="table-layout:auto"}

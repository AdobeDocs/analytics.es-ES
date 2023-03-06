---
description: Adobe proporciona varias métricas calculadas que puede utilizar. Esta página enumera dichas métricas y los usos a los que están destinadas.
title: 'Referencia: funciones básicas'
feature: Calculated Metrics
exl-id: 1a49435c-96d1-4617-bd1a-a5d3b74e3ebd
source-git-commit: 2874ea66765e650a92bc39537d6a9eb8cebcd6a4
workflow-type: tm+mt
source-wordcount: '891'
ht-degree: 10%

---

# Métricas calculadas predeterminadas

Adobe Analytics proporciona varias métricas calculadas para cubrir los casos de uso más comunes. Estas métricas calculadas están disponibles de forma predeterminada en Analysis Workspace.

A continuación se muestra una lista de cada Métrica calculada proporcionada por Adobe, con su función prevista y la fórmula subyacente utilizada para calcularla:

>[!NOTE]
>
>Además de las Métricas calculadas predeterminadas descritas en esta página, también puede agregar Métricas calculadas adicionales a un Grupo de informes.
>
>Puede:
> * Añada las métricas calculadas predeterminadas para los medios de streaming, tal como se describe en [Métricas calculadas](/https://experienceleague.adobe.com/docs/media-analytics/using/implementation/variables/calculated-metrics.html)
> * Cree métricas calculadas personalizadas a partir de métricas existentes, tal como se describe en [Métricas calculadas y calculadas avanzadas (derivadas)](/help/components/c-calcmetrics/cm-overview.md).



| Nombre de métrica calculada | Función | Fórmula |
|---------|----------|---------|
| Tasa de devoluciones | La proporción de visitas que contenían exactamente una visita en comparación con el número de visitas en esa página. Esto puede ayudarle a comprender qué elementos de dimensión tienen la tasa de salida hacia otro sitio más alta o a ver una tasa de salida hacia otro sitio total agregada a lo largo del tiempo. | Tasa de devoluciones |
| Ingresos/Visitante | Cantidad promedio de ingresos generados por cada visitante individual del sitio. | <p>Ingresos</p><p>/</p><p>Visitantes únicos</p> |
| Pedidos/Visitante | Número promedio de pedidos o transacciones generados por cada visitante individual del sitio | <p>Pedidos predeterminados</p><p>/</p><p>Visitante</p> |
| Ingresos / Visitas | Cantidad promedio de ingresos generados por una sola visita al sitio. | <p>Ingresos</p><p>/</p><p>Visitas únicas</p> |
| Ingresos / Pedido | Cantidad media de ingresos generados por cada transacción o pedido completado en la dirección. | <p>Ingresos</p><p>/</p><p>Pedido</p> |
| Pedidos/Visitas | Porcentaje de visitas al sitio que resultan en una transacción completada. | <p>Pedido</p><p>/</p><p>Visitas</p> |
| Vistas de página/Visitas | Promedio de páginas que un usuario ve durante una sola visita al sitio. | <p>Vistas de páginas</p><p>/</p><p>Visitas</p> |
| Visitas/Visitante | Número promedio de visitas que un visitante único realiza al sitio. | <p>Visitas</p><p>/</p><p>Visitantes únicos</p> |
| Recargas / Vistas de página | Porcentaje de vistas de página que resultaron en una recarga o actualización de la página. | <p>Recargas</p><p>/</p><p>Vistas de páginas</p> |
| Tasa de salida hacia otro sitio ponderada | Función | if(visitas>percentil(visitas),bouncerate,0) |
| Asistencia para pedidos | El número de veces que un canal o fuente contribuyó al recorrido de un cliente para realizar una compra, pero no resultó en la compra final. | <p>Pedidos (participación\|visita)</p><p>-</p><p>Pedidos</p> |
| Tasa de salida | El porcentaje de visitantes que abandonan el sitio después de ver una página en particular. | <p>Salidas</p><p>/</p><p>Visitas</p> |
| Tasa de entrada | El porcentaje de visitantes que entraron al sitio en una página determinada, comparado con la cantidad total de sesiones en el sitio. | <p>Entradas</p><p>/</p><p>Visitas</p> |
| Promedio de tiempo en el sitio | Cantidad promedio de tiempo que un visitante pasa en el sitio antes de salir o navegar. | Tiempo promedio invertido en el sitio (segundos) |
| Tiempo empleado/usuario (estado) | Período de tiempo que el visitante promedio pasa en un estado determinado mientras está en el sitio | Métrica Tiempo empleado por visitante (segundos) + Segmento de aplicación móvil |
| Usuarios (móvil) | Número total de usuarios de una aplicación móvil | Métrica Visitantes únicos + segmento Usuarios de aplicaciones móviles |
| Usuarios de aplicación | Número total de usuarios de una aplicación móvil | Métrica Visitantes únicos + segmento de aplicación móvil |
| Vistas de estado | Número de vistas a los diferentes estados o pantallas de la aplicación | Métrica Vistas de página + Segmento de aplicación móvil |
| Acciones | Número total de acciones realizadas en la aplicación | Instancia de vínculo personalizado + Tiene un segmento de acción |
| Clics en vínculos de adquisición | La cantidad de veces que las personas hacen clic en un vínculo diseñado para dirigir el tráfico al sitio. | Métrica de clics de Campaign |
| Velocidad de página | Número de vistas de página adicionales que genera un fragmento de contenido. Esto puede ayudarle a determinar qué contenido genera participación adicional. | <p>Vistas de páginas</p><p>/</p><p>Visitas</p> |
| Tasa de conversión | El porcentaje de visitantes que realizaron una acción deseada, como una compra. | <p>Pedidos</p><p>/</p><p>Visitas</p> |
| Longitud promedio de la sesión (móvil) | Promedio de tiempo que los visitantes pasan en el sitio durante una sola sesión. | En blanco |
| Cobertura de ID de Experience Cloud | El porcentaje de visitantes que tienen un ID de Experience Cloud. | <p>Visitantes con Experience Cloud ID</p><p>/</p><p>Visitantes únicos</p> |
| Velocidad del contenido | La velocidad a la que se crea y publica contenido nuevo en el sitio y la velocidad con la que genera la participación del usuario. | <p>Vistas de páginas</p><p>/</p><p>Visitas</p> |
| Visitantes únicos/Visitantes únicos de ITP 2.1 | El porcentaje de visitantes únicos que utilizan un explorador afectado por las limitaciones de cookies de ITP 2.1. Es decir, los clientes que no utilizan una implementación CNAME. (Esto se aplica a los clientes que configuran cookies mediante JavaScript del lado del cliente). | <p>Métrica Visitantes únicos + segmento Visitantes de ITP</p><p>/</p><p>Visitantes únicos</p> |
| Visitantes únicos/Visitantes únicos que regresan después de 7 días | El porcentaje de visitantes únicos que regresan después de un período de 7 días o más. | <p>Métrica Visitantes únicos + Segmento de usuarios que regresan después de 7 días</p><p>/</p><p>Visitantes únicos</p> |
| Vistas de página/Visitante único | Promedio de páginas vistas para cada visitante único del sitio. | <p>Vistas de páginas</p><p>/</p><p>Visitantes únicos</p> |
| Visitas / Visitantes | Número promedio de visitas que un visitante único realiza al sitio | <p>Visitas</p><p>/</p><p>Visitantes únicos</p> |
| Visitantes únicos estimados (ITP 2.1) | <p>Para los visitantes de ITP (usuarios en navegadores Safari), divida los visitantes únicos entre 2 o menos.</p><p>Esto supone que está configurando cookies mediante JavaScript del lado del cliente (no utilizando una implementación CNAME). Las implementaciones que establecen cookies mediante JavaScript del lado del cliente se vieron afectadas a partir de ITP 2.1. Consulte: [https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/)</p> | <p>Métrica Visitantes únicos + Segmento Visitantes de ITP (ITP 2.1, implementaciones que no son CNAME)</p><p>/</p><p>Métrica Visitantes únicos + Segmento Visitantes que no son ITP (implementaciones ITP 2.1 y que no son CNAME)</p> |
| Vistas de página/Visitantes únicos estimados (ITP 2.1) | Número promedio de páginas vistas para Visitantes únicos estimados (ITP 2.1). | <p>Métrica Visitantes únicos + Segmento Visitantes de ITP (ITP 2.1, implementaciones que no son CNAME)</p><p>/</p><p>Métrica Visitantes únicos + Segmento Visitantes que no son ITP (implementaciones ITP 2.1 y que no son CNAME)</p> |

{style="table-layout:auto"}

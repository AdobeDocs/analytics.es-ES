---
description: Hay dos modos de utilizar métricas en Analysis Workspace.
title: Métricas en Analysis Workspace
feature: Metrics
role: User, Admin
exl-id: 0a5dc709-c4e8-412a-a6cf-37b85d811f65
source-git-commit: e0a10540bdfbd9fa3694ff3c7a8585eeb87eaad8
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 23%

---

# Métricas

Las métricas le permiten cuantificar los puntos de datos en Analysis Workspace. Normalmente se utilizan como columnas en una visualización y están vinculadas a dimensiones.

Adobe ofrece varios tipos de métricas para su uso en Analysis Workspace:

* **Métricas estándar**: La mayoría de las métricas que se utilizan en los proyectos son métricas estándar. Algunos ejemplos son [Vistas de página](/help/components/metrics/page-views.md), [Ingresos](/help/components/metrics/revenue.md)o [Eventos personalizados](/help/components/metrics/custom-events.md). Consulte [Resumen de las métricas](/help/components/metrics/overview.md) en la guía del usuario Componentes para obtener más información.

   ![Métrica estándar](assets/standard-metric.png)

* **Métricas calculadas**: Métricas definidas por el usuario que se basan en métricas estándar, números estáticos o funciones algorítmicas. Las métricas calculadas definidas por el usuario muestran un icono de calculadora en la lista de componentes disponibles. Consulte [Información general sobre las métricas calculadas](/help/components/c-calcmetrics/cm-overview.md) en la guía del usuario Componentes para obtener más información.

   ![Métrica calculada](assets/calculated-metric.png)

* **Plantillas de métricas calculadas**: Métricas definidas por Adobes que se comportan de manera similar a las métricas calculadas. Puede utilizarlos tal cual en proyectos de Workspace o guardar una copia para personalizar su lógica. Las plantillas de métricas calculadas muestran un icono de Adobe en la lista de componentes disponibles.

   ![Plantilla de métrica calculada](assets/calculated-metric-template.png)

Las métricas son flexibles en su uso dentro de Analysis Workspace. Arrastre una métrica a una tabla improvisada vacía para ver si esa métrica tiene tendencias a lo largo del periodo de fechas del proyecto. También puede arrastrar una métrica cuando haya una dimensión presente para ver esa métrica en comparación con cada elemento de dimensión. Si arrastra una métrica sobre un encabezado de métrica existente, podrá reemplazarla y, si arrastra una métrica junto al encabezado, podrá ver ambas métricas una al lado de la otra.

>[!VIDEO](https://video.tv.adobe.com/v/40817/?quality=12)

## Métricas calculadas

Las métricas calculadas permiten ver fácilmente cómo se relacionan las métricas entre sí mediante operadores simples o funciones estadísticas. Existen varias formas de crear métricas calculadas:

* Haga clic en el icono del signo más situado junto al encabezado Métricas en la lista de componentes de la izquierda.
* Vaya a **[!UICONTROL Componentes]** > **[!UICONTROL Métricas calculadas]** > **[!UICONTROL Agregar]**.
* Haga clic con el botón derecho en el encabezado de una columna > **[!UICONTROL Crear métrica a partir de la selección]** cuando se seleccionan una o más celdas de columna de encabezado. Esta opción crea automáticamente una métrica calculada sin necesidad de usar el Creador de reglas de métricas calculadas.

[Métricas calculadas: métricas sin implementación](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-implementationless-metrics.html?lang=es) (3:42)

## Comparar métricas con diferentes modelos de atribución

Si quiere comparar rápida y fácilmente un modelo de atribución con otro, haga clic con el botón secundario en una métrica y seleccione **[!UICONTROL Comparar modelo de atribución]**:

![Comparar atribución](assets/compare-attribution.png)

Este método abreviado permite comparar rápida y fácilmente un modelo de atribución con otro sin tener que arrastrar una métrica y configurarla dos veces.

## Uso de la función [!UICONTROL media acumulativa] para aplicar el suavizado de métricas

A continuación, se muestra un vídeo sobre este tema:

>[!VIDEO](https://video.tv.adobe.com/v/27068/?quality=12)

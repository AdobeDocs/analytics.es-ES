---
description: Pasos para agregar métricas y dimensiones a una solicitud.
title: Agregar métricas y dimensiones
topic: Report builder
uuid: 588ce96b-3a2d-42b7-8a8e-7e6f448a0115
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Agregar métricas y dimensiones

Pasos para agregar métricas y dimensiones a una solicitud.

1. [Cree la solicitud](/help/analyze/report-builder/data-requests/data-requests.md) de datos en el [!UICONTROL Request Wizard: Step 1], luego haga clic en **[!UICONTROL Next]**.
1. On the [!UICONTROL Request Wizard: Step 2], double-click metrics, or drag them to the desired position.

   ![Información sobre los pasos](assets/adding_metrics.png)

   When you add metrics, they are not removed from the [!UICONTROL Metrics] tab, because you can display metrics multiple times within a request. Por ejemplo, se puede mostrar el subtotal de la métrica junto con cada valor. Sin embargo, la lista de las métricas disponibles cambia cada vez que se añade o se elimina una dimensión.

   You can add only metrics to the [!UICONTROL Metrics] layout section. Las métricas se agregan al [!UICONTROL Column Label] diseño como un [!UICONTROL Metric Header]. If you move a [!UICONTROL Metric Header] from [!UICONTROL Column Layout] to [!UICONTROL Row Layout], it is displayed there and is used as a metric as a breakdown.

   Tenga en cuenta que se muestra una barra de búsqueda en la pestaña Métricas, justo encima de la lista Métrica.

   ![](assets/search_bar_metric.png)

   Recuerde:

   * A medida que introduce un término de búsqueda, la lista se actualizará automáticamente para mostrar solo las métricas cuyas etiquetas coincidan con el término de búsqueda.
   * Las coincidencias no distinguen entre mayúsculas y minúsculas y son equivalentes a una búsqueda &quot;contiene&quot;.
   * Las búsquedas de palabras completas u otros indicadores de búsqueda especial (comienza con, termina con, AND, OR, etc.) no son compatibles.

      El Término de búsqueda se borrará al salir del Asistente para solicitudes (p.ej., al hacer clic en Finalizar o Cancelar), al volver al Paso 1 del Asistente para solicitudes o al cambiar la categoría de Métrica.

      El término de búsqueda no se borrará en los siguientes casos:

   * Al arrastrar y soltar (o hacer doble clic) en uno de los elementos de métrica en la lista, de modo que se agregue al Panel de Métricas Diseño de tabla dinámica/Diseño personalizado.
   * Al eliminar un elemento de métrica del Panel de Métricas Diseño de tabla dinámica/Diseño personalizado.
   * Al hacer clic en la ficha Dimensiones y, a continuación, volver a la ficha Métricas.
   * Al invocar otros subformularios (modales o sin modo) que al salir, vuelven al Paso de 2 del Asistente para solicitudes. Varios ejemplos de estos formularios son

      * Formularios de filtro de dimensión
      * Formularios de formato de rango de fecha
      * Formularios de opciones de formato
      * Formularios de anteponer/posponer texto
      * Formularios de ubicación del rango de salida

1. (Opcional) Para clasificar una solicitud por métrica, simplemente haga clic en la etiqueta de métrica.
1. Añada las dimensiones del mismo modo en que se agregan las métricas.

On the [!UICONTROL Dimensions] tab, the system displays dimensions that break down or are a classification of any base report you select on Step 1, and on the configuration of the report suite. Cuando se coloca una dimensión en las cuadrículas de diseño, esta se elimina de la vista de árbol y se vuelve a calcular la lista de las dimensiones restantes disponibles.

The [!UICONTROL Date] dimension is added automatically. Available date dimensions change depending on the selected granularity from the [!UICONTROL Request Wizard: Step 1]. (Los valores válidos son:

    * Hora
    * Día
    * Semana
    * Mes
    * Año
    * Intervalo de fecha (cuando no se especifica granularidad)

1. Modifique las métricas y las dimensiones configurando las [opciones y los filtros de formato](/help/analyze/report-builder/layout/t-format-display-headers.md).
1. Haga clic en **[!UICONTROL Finish]**.
In the following example, dimensions relate to the [!UICONTROL Page] metric. Aquí, la [!UICONTROL Referring Domain] dimensión crea un informe de desglose entre [!UICONTROL Page] y [!UICONTROL Referring Domain]. The [!UICONTROL Dimension] tab is updated with only dimensions that you can add to a breakdown report.

![](assets/page_pageview_02.png)

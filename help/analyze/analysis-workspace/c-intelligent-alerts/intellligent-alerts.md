---
description: El nuevo sistema Alertas inteligentes permite un control más granular sobre las alertas e integra la detección de anomalías en el sistema de alerta.
title: Resumen de las alertas inteligentes
uuid: b9bf75ad-bb6f-49fe-8c55-355ea3c50a71
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Resumen de las alertas inteligentes

Alertas inteligentes permite un control más granular de las alertas e integra la detección de anomalías con el sistema de alerta.

[Alertas inteligentes en YouTube](https://www.youtube.com/watch?v=UVH9xr_2REA) (5:34)

## Información general

El nuevo Generador de alertas y el Administrador de alertas en Analysis Workspace sustituyen la funcionalidad de alertas existente en Reports &amp; Analytics. Las alertas inteligentes le permiten:

* Generar alertas en función de anomalías (umbrales del 90 %, 95 %, 99 %, 99,75 % y 99,9 %; cambio de %; por encima/por debajo)
* Obtener una vista previa de la frecuencia con la que se activará una alerta
* Enviar alertas por correo electrónico o SMS con vínculos a proyectos de Analysis Workspace autogenerados
* Crear alertas “apiladas” que capturan varias métricas en una sola alerta

Hay cuatro formas en las que puede acceder al Generador de alertas:

* Ir directamente al Generador de alertas:  **[!UICONTROL Componentes]** &gt; **[!UICONTROL Alertas]**
* Uso del método abreviado de teclado en Workspace: `Ctrl + Shift + A` (Windows) o `Cmd + Shift + A` (Mac)
* Selecting one or more freeform table line item/s, right-clicking and selecting **[!UICONTROL Create Alert from Selection]**. Se abre el Generador de alertas y se rellenan previamente las métricas y los filtros adecuados aplicados desde la tabla. Puede editar la alerta si es necesario.

   ![Crear alertas a partir de la selección](assets/create-alert-from-selection.png)

* From within a Reports &amp; Analytics report, by going to  **[!UICONTROL More]** &gt; **[!UICONTROL Add Alert]** . Esto abre el creador de alertas y rellena previamente las métricas y filtros adecuados aplicados desde el informe. Puede editar la alerta si es necesario.

   ![Agregar alerta](assets/add-alert.png)

Los umbrales porcentuales son desviaciones estándar. Por ejemplo, 95 % = 2 desviaciones estándar y 99 % = 3 desviaciones estándar. En función de la granularidad de tiempo que seleccione, se emplean [distintos modelos](../virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md) para calcular cuánto se aleja (cuántas desviaciones estándar tiene) cada punto de datos respecto a la norma. Si establece un umbral inferior (como 90 %), obtendrá más anomalías que si establece un umbral superior (99,75 %).

> [!IMPORTANT] El uso de datos con marca de hora para crear alertas puede provocar que las alertas se activen incorrectamente. Adobe recomienda utilizar datos sin marca de hora para las alertas inteligentes.

## Retrospectiva de anomalías para alertas

Si una alerta utiliza la detección de anomalías, el período de prueba varía según la granularidad seleccionada para la alerta.

* Granularidad mensual: 15 meses + el mismo intervalo del año pasado
* Granularidad semanal: 15 semanas + el mismo intervalo del año pasado
* Granularidad diaria: 35 días + el mismo intervalo del año pasado
* Granularidad por hora: 336 horas

Consulte Técnicas [estadísticas utilizadas en la detección](../virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md) de anomalías para obtener más información.

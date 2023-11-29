---
description: El nuevo sistema Alertas inteligentes permite un control más granular sobre las alertas e integra la detección de anomalías en el sistema de alerta.
title: Resumen de las alertas inteligentes
feature: Alerts
role: User, Admin
exl-id: 49d47896-bf93-4960-b647-2765c935eb25
source-git-commit: 2eff7656741bdba3d5d7d1f33e9261b59f8e6083
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 100%

---

# Resumen de las alertas inteligentes

El sistema Alertas inteligentes permite un control más granular sobre las alertas e integra la detección de anomalías en el sistema de alerta.

Este es un tutorial en vídeo sobre [Alertas inteligentes](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/intelligent-alerts.html?lang=es) (5:34)

## Información general

El nuevo Generador de alertas y el Administrador de alertas en Analysis Workspace sustituyen la funcionalidad de alertas existente en Reports &amp; Analytics. Las alertas inteligentes le permiten:

* Generar alertas en función de anomalías (umbrales del 90 %, 95 %, 99 %, 99,75 % y 99,9 %; cambio de %; por encima/por debajo)
* Obtener una vista previa de la frecuencia con la que se activará una alerta
* Enviar alertas por correo electrónico o SMS con vínculos a proyectos de Analysis Workspace autogenerados
* Crear alertas “apiladas” que capturan varias métricas en una sola alerta

Hay cuatro formas en las que puede acceder al Generador de alertas:

| Método | Detalles |
| --- | --- |
| Ir directamente al Generador de alertas | **[!UICONTROL Componentes]** > **[!UICONTROL Alertas]** |
| Uso del atajo de teclado en Espacio de trabajo | `Ctrl + Shift + A` (Windows) o `Cmd + Shift + A` (Mac) |
| Seleccione uno o más elementos de línea de la tabla de forma libre | Haga clic con el botón derecho y seleccione **[!UICONTROL Crear alerta a partir de la selección]**. Se abre el [!UICONTROL Generador de alertas] y se rellenan previamente las métricas y los filtros adecuados aplicados desde la tabla. A continuación, puede editar la alerta si fuera necesario. ![Crear alerta a partir de la selección](assets/create-alert-from-selection.png) |
| Desde un informe de Reports &amp; Analytics | Vaya a  **[!UICONTROL Más]** > **[!UICONTROL Añadir alerta]**. Esto abre el Generador de alertas y rellena previamente las métricas y filtros adecuados aplicados desde el informe. A continuación, puede editar la alerta si fuera necesario. ![Agregar alerta](assets/add-alert.png) |

Los porcentajes de umbral son desviaciones estándar. Por ejemplo, 95 % = 2 desviaciones estándar y 99 % = 3 desviaciones estándar. En función de la granularidad de tiempo que seleccione, se emplean [distintos modelos](/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md) para calcular cuánto se aleja (cuántas desviaciones estándar tiene) cada punto de datos respecto a la norma. Si establece un umbral más bajo (por ejemplo, 90%), obtendrá más anomalías que con otro más alto (99,75%).

>[!IMPORTANT]
>
>El uso de datos con fecha y hora para crear alertas puede hacer que se activen incorrectamente. Adobe recomienda utilizar datos sin marca de hora para las alertas inteligentes.

## Retrospectiva de anomalías para alertas

Si una alerta utiliza la detección de anomalías, el periodo de prueba varía según la granularidad seleccionada para la alerta.

* Granularidad mensual: 15 meses + el mismo intervalo del año anterior
* Granularidad semanal: 15 semanas + el mismo intervalo del año anterior
* Granularidad diaria: 35 días + el mismo intervalo del año anterior
* Granularidad horaria: 336 horas

Consulte [Técnicas estadísticas utilizadas en la detección de anomalías](/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md) para obtener más información.

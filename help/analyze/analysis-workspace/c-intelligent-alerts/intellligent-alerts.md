---
description: El nuevo sistema Alertas inteligentes permite un control más granular sobre las alertas e integra la detección de anomalías en el sistema de alerta.
title: Resumen de las alertas inteligentes
feature: Alerts
role: User, Admin
exl-id: 49d47896-bf93-4960-b647-2765c935eb25
source-git-commit: d48f74d4fa642e34de601466737f16fc228a8199
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 52%

---

# Resumen de las alertas inteligentes

Las alertas inteligentes (o simplemente &quot;alertas&quot;) de Adobe Analytics le permiten recibir notificaciones inmediatamente cuando se producen eventos anómalos en sus datos.

Puede definir alertas para que se activen en función de umbrales de anomalías, porcentajes modificados o puntos de datos específicos. Las alertas proporcionan controles granulares que se integran con [Detección de anomalías](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md), que se activa cuando más los necesita.

Las alertas inteligentes le permiten:

* Generar alertas en función de anomalías (umbrales del 90 %, 95 %, 99 %, 99,75 % y 99,9 %; cambio de %; por encima/por debajo)
* Obtener una vista previa de la frecuencia con la que se activará una alerta
* Enviar alertas por correo electrónico o SMS con vínculos a proyectos de Analysis Workspace autogenerados
* Crear alertas “apiladas” que capturan varias métricas en una sola alerta

El siguiente tutorial de vídeo proporciona información general básica sobre las alertas: [Alertas inteligentes](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/intelligent-alerts.html?lang=es) (5:34)

## Retrospectiva de anomalías para alertas

Si una alerta utiliza la detección de anomalías, el periodo de prueba varía según la granularidad seleccionada para la alerta.

* Granularidad mensual: 15 meses + el mismo intervalo del año anterior
* Granularidad semanal: 15 semanas + el mismo intervalo del año anterior
* Granularidad diaria: 35 días + el mismo intervalo del año anterior
* Granularidad horaria: 336 horas

Para obtener más información, consulte [Técnicas estadísticas utilizadas en la detección de anomalías](/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md).

## Creación de alertas

Para obtener información sobre cómo crear alertas en Adobe Analytics, consulte [Creación de alertas](/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md).

>[!IMPORTANT]
>
>El uso de datos con fecha y hora para crear alertas puede hacer que se activen incorrectamente. Adobe recomienda utilizar datos sin marca de hora para las alertas inteligentes.

## Administración de alertas

Puede administrar las alertas existentes en el Administrador de alertas. Puede realizar varias tareas de administración en las alertas, como etiquetado, cambio de nombre, eliminación, etc.

Para obtener más información sobre cómo administrar las alertas existentes en Adobe Analytics, consulte [Administración de alertas](/help/analyze/analysis-workspace/c-intelligent-alerts/alert-manager.md).

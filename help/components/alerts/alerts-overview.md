---
description: Conozca cómo usar alertas para permitir un control granular sobre las notificaciones y la integración con la detección de anomalías.
title: Información general sobre alertas
feature: Alerts
exl-id: 1b23211e-7632-4b33-a27d-c58b3bbbbab1
source-git-commit: f02b660b551f5291443b8f7c5c51179a06b22eb9
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 54%

---

# Información general sobre alertas

Las alertas de Adobe Analytics permiten recibir notificaciones basadas en porcentajes modificados o puntos de datos específicos.

Según el paquete de Adobe Analytics, también puede utilizar alertas para activarlas en función de los umbrales de anomalías. Estas alertas (también conocidas como *Alertas inteligentes*) proporcionan controles granulares que se integran con la [Detección de anomalías](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md) y se activan cuando más las necesita.

Las alertas le permiten:

* Vista previa de la frecuencia con la que déclencheur una alerta.
* Enviar alertas por correo electrónico o SMS con vínculos a proyectos de Analysis Workspace autogenerados.
* Crear *alertas apiladas* que capturan varias métricas en una sola alerta.
* Generar alertas basadas en:
   * Anomalías en métricas que existen, que están por encima o por debajo de los valores de umbral esperados.

     [Detección de anomalías](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md) crea un valor esperado más un límite superior e inferior usando datos históricos. Si el valor real de la métrica va por encima o por debajo del límite inferior definido como valor de umbral, ese evento se considera una anomalía en el nivel de confianza de umbral y no almacena en déclencheur la alerta. Un umbral más alto (por ejemplo, 99 % o 99,9 %) implica una banda más ancha, lo que resulta en menos alertas causadas por anomalías más extremas. Un umbral más bajo (por ejemplo, 90 %) implica una banda más estrecha, lo que da como resultado más alertas causadas por anomalías menos extremas.
   * Cambios en las métricas según un porcentaje específico.
   * Métricas que están por encima, por debajo o iguales a un valor específico. (disponible solo para clientes de Adobe Analytics con un paquete Select, Prime o Ultimate)

Este [tutorial en vídeo](https://experienceleague.adobe.com/es/docs/analytics-learn/tutorials/data-science/intelligent-alerts) proporciona información general básica sobre las alertas.


## Retrospectiva de anomalías para alertas

>[!NOTE]
>
>El uso de alertas con detección de anomalías (también conocido como _alertas inteligentes_) solo está disponible para organizaciones con un paquete de Adobe Analytics Prime o Ultimate.

Si una alerta utiliza la detección de anomalías, el periodo de prueba varía según la granularidad seleccionada para la alerta.

* Granularidad mensual: 15 meses + el mismo intervalo del año anterior
* Granularidad semanal: 15 semanas + el mismo intervalo del año anterior
* Granularidad diaria: 35 días + el mismo intervalo del año anterior
* Granularidad horaria: 336 horas

Consulte [Técnicas estadísticas utilizadas en la detección de anomalías](/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md) para obtener más información.

## Creación de alertas

Para obtener información sobre cómo crear alertas en Adobe Analytics, consulte [Crear alertas](/help/components/alerts/alert-builder.md).

>[!IMPORTANT]
>
>El uso de datos con fecha y hora para crear alertas puede hacer que se activen incorrectamente. Adobe recomienda utilizar datos sin marca de hora para las alertas.

## Administración de alertas

Puede administrar las alertas existentes en el Administrador de alertas. Puede realizar varias tareas de administración de las alertas, como etiquetado, cambio de nombre, eliminación, etc.

Para obtener más información sobre cómo administrar las alertas existentes en Adobe Analytics, consulte [Administrar alertas](/help/components/alerts/alert-manager.md).

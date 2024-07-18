---
description: El nuevo sistema Alertas inteligentes permite un control más granular sobre las alertas e integra la detección de anomalías en el sistema de alerta.
title: Alertas inteligentes
feature: Alerts
exl-id: 1b23211e-7632-4b33-a27d-c58b3bbbbab1
source-git-commit: be5a73347d417c8dc6667d4059e7d46ef5f0f5cd
workflow-type: tm+mt
source-wordcount: '520'
ht-degree: 68%

---

# Alertas inteligentes

El nuevo sistema Alertas inteligentes permite un control más granular sobre las alertas e integra la detección de anomalías en el sistema de alerta.

A continuación, se muestra un vídeo introductorio:

>[!VIDEO](https://video.tv.adobe.com/v/25446/?quality=12)

## Información general {#section_6AC8CA81DEA94E99B0F192B60D0FDF03}

>[!IMPORTANT]
>
>Las alertas inteligentes están disponibles solo para los clientes de Adobe [!DNL Analytics] Prime y Adobe [!DNL Analytics] Ultimate.

Las alertas inteligentes le permiten

* Generar alertas en función de anomalías (umbrales del 90 %, 95 %, 99 %, 99,75 % y 99,9 %; cambio de %; por encima/por debajo).
* Obtener una vista previa de la frecuencia con la que se activará una alerta.
* Enviar alertas por correo electrónico o SMS con vínculos a proyectos de Analysis Workspace autogenerados.
* Crear alertas “apiladas” que capturan varias métricas en una sola alerta.

Los componentes del sistema de alerta incluyen: Generador de alertas, Administrador de alertas, Vista previa de alertas y un mejor acceso en contexto para la creación de alertas. La interfaz de usuario del sistema de alertas anterior ya no estará disponible, pero las alertas migran. Algunas de las funcionalidades de alerta heredadas [ya no están disponibles](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/alerts.html?lang=es).

Existen tres formas de acceder al Generador de alertas:

* Mediante el acceso directo siguiente en Analysis Workspace:

  `ctrl (or cmd) + shift + a`
* Seleccione directamente el Generador de alertas: **[!UICONTROL Workspace]** > **[!UICONTROL Componentes]** > **[!UICONTROL Alerta nueva]** .
* Seleccione uno o más elementos de línea de la tabla de forma libre, haga clic con el botón derecho y seleccione **[!UICONTROL Crear alerta a partir de la selección]**. De esta forma se abrirá el Generador de alertas, que se rellenará con las métricas y filtros adecuados aplicados a partir de la tabla. A continuación, puede editar la alerta si fuera necesario.

  ![](assets/create-alert-from-selection.png)


## Preguntas más frecuentes: Cómo se calculan y activan las alertas {#trigger}

Los porcentajes de umbral son desviaciones estándar. Por ejemplo, 95 % = 2 desviaciones estándar y 99 % = 3 desviaciones estándar. Según la granularidad de tiempo que elija, se usan [diferentes modelos](/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md) para calcular a qué distancia (cuántas desviaciones estándar tiene) cada punto de datos está respecto a la norma. Si establece un umbral más bajo (por ejemplo, 90 %), obtendrá más anomalías que con otro más alto (99 %). Los umbrales 99,75 % y 99,99 % se introdujeron específicamente para la granularidad horaria, de modo que no se activen tantas anomalías.

+++ ¿Hasta dónde se remonta la detección de anomalías de la alerta para determinar anomalías de datos?

El periodo de aprendizaje varía en función de la granularidad seleccionada. Consulte Técnicas estadísticas utilizadas en la <a href="/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md">detección de anomalías</a> para obtener más información. Aquí tiene un resumen:

* Mensual = 15 meses + el mismo intervalo del año anterior
* Semanal = 15 semanas + el mismo intervalo del año anterior
* Diaria = 35 días + el mismo intervalo del año anterior
* Horaria = 336 horas

+++

+++ Para recibir alertas solo de un descenso o solo de un pico en el comportamiento, ¿puedo utilizar la función de anomalías o necesito utilizar un valor absoluto?

El uso del valor absoluto seguiría almacenando en déclencheur las alertas tanto de caídas como de picos. No es posible aislar las alertas para diferenciar descensos y picos.

+++

+++ ¿Puedo configurar las alertas para que entren en déclencheur solo durante determinadas horas del día (por ejemplo, en horario laboral o fuera del horario laboral)?

En estos momentos, no.

+++

+++ ¿Puedo obtener una tabla de los &quot;valores esperados&quot; que comprenden la línea de puntos, o algún tipo de resultado de cuáles son esos valores?

No en Workspace, pero puede en Report Builder. Vea [este vídeo](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/exporting/report-builder/anomaly-detection-in-report-builder.html?lang=es) sobre la detección de anomalías en Report Builder.

Tenga en cuenta que el Report Builder emplea métodos de detección de anomalías menos sofisticados. Utiliza un periodo de formación de 30 días fijo, con un intervalo fijo del 95 %.

+++

---
description: El panel Analytics para Destinatario (A4T) permite analizar las actividades y experiencias de Adobe Target en Analysis Workspace.
title: Panel Analytics para Destinatario (A4T)
translation-type: tm+mt
source-git-commit: fe6202288cfc07575db437f7d0c055f1b40ddcf6
workflow-type: tm+mt
source-wordcount: '834'
ht-degree: 14%

---


# Panel Analytics para Destinatario (A4T)

El panel Analytics for Target (A4T) le permite analizar las actividades y experiencias de Adobe Target en Analysis Workspace. También le permite ver el alza y la confianza de hasta 3 métricas de éxito. Para acceder al panel A4T, navegue a un grupo de informes con componentes de A4T activados. A continuación, haga clic en el icono del panel situado en el extremo izquierdo y arrastre el panel Analytics para Destinatario a su proyecto Analysis Workspace.

## Entradas de panel {#Input}

Puede configurar el panel A4T con esta configuración de entrada:

| Configuración | Descripción |
|---|---|
| Actividad de Target | Seleccione una lista de Actividades de Destinatario o arrastre y suelte una actividad desde el carril izquierdo.<br>**Nota:**La lista se llena con los últimos 6 meses de actividades que han tenido al menos 1 visita. Si no ve una actividad en la lista, puede ser mayor de 6 meses. Todavía se puede añadir desde el carril izquierdo, que tiene un periodo retroactivo de hasta 18 meses. |
| Experiencia de control | Seleccione la experiencia de control. Puede cambiarlo si es necesario en la lista desplegable. |
| Métrica de normalización | Elija entre Visitantes únicos, visitas o impresiones de Actividad. Se recomiendan visitantes únicos para la mayoría de los casos de uso de análisis. Esta métrica (también denominada metodología de contabilización) se convierte en el denominador del cálculo del alza. También afecta a la manera en que se agregan los datos antes de que se calcule la confianza. |
| Métricas de éxito | Seleccione hasta 3 eventos de éxito estándar (no calculados) en la lista desplegable o arrastre y suelte las métricas desde el carril izquierdo. Cada métrica tendrá una tabla y una visualización dedicadas en el panel procesado. |
| Intervalo de fechas del calendario | Esto se rellenará automáticamente en función del intervalo de fechas de Actividad desde el Adobe Target. Puede cambiarlo si es necesario. |

![Generador de paneles](assets/a4t-panel-builder2.png)

## Salida de panel {#Output}

El panel Analytics para Destinatario devuelve un completo conjunto de datos y visualizaciones para ayudarle a comprender mejor el rendimiento de la actividad y las experiencias de Adobe Target. En la parte superior del panel, se proporciona una línea de resumen para recordarle la configuración del panel seleccionada. En cualquier momento, puede editar el panel haciendo clic en el lápiz de edición en la parte superior derecha.

Para cada métrica de éxito seleccionada, se mostrará una tabla improvisada y una tendencia de tasa de conversión:

![Procesado](assets/a4t-rendered.png)


Cada tabla improvisada muestra las siguientes columnas de métricas:

| Métrica | Descripción |
|---|---|
| Normalización de métricas | Visitantes únicos, visitas o impresiones de Actividad. |
| Métricas de éxito | La métrica seleccionada en el generador |
| Tasa de conversión | Métrica de éxito/métrica de normalización |
| Alza | Compara la tasa de conversión de cada experiencia con la experiencia de control.<br>**Nota:**El alza es una &quot;métrica bloqueada&quot; de las experiencias de Destinatario; no se puede desglosar ni utilizar con otras dimensiones. |
| Alza (inferior) | Representa la peor elevación que una experiencia de variante podría tener sobre el control. |
| Alza (media) | Representa la elevación media que una experiencia de variante podría tener sobre el control con un intervalo de confianza del 95 %. Esto es &quot;Alza&quot; en Informes y Analytics. |
| Alza (superior) | Representa la mejor elevación que una experiencia de variante podría tener sobre el control. |
| Confianza | La prueba T de los estudiantes calcula el nivel de confianza, lo que indica la probabilidad de que los resultados se dupliquen si la prueba se ejecuta de nuevo. Se ha aplicado a la métrica un rango de formato condicional fijo del 75%/85%/95%. Este formato se puede personalizar si es necesario en Configuración de columna. <br>**Nota:**La confianza es una &quot;métrica bloqueada&quot; para las experiencias de Destinatario; no se puede desglosar ni utilizar con otras dimensiones. |

Como con cualquier panel de Analysis Workspace, puede continuar con la análisis agregando tablas y [visualizaciones](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html) adicionales que le ayudarán a analizar sus actividades de Adobe Target.

## Preguntas frecuentes {#FAQ}

| Pregunta | Respuesta |
|---|---|
| ¿Qué tipos de actividad se admiten en A4T? | [Obtenga más](https://docs.adobe.com/content/help/en/target/using/integrate/a4t/a4t-faq/a4t-faq-activity-setup.html) información sobre los tipos de actividad admitidos. |
| ¿Se admiten las métricas calculadas en los cálculos de alza y confianza? | No. [Obtenga más](https://docs.adobe.com/content/help/en/target/using/integrate/a4t/a4t-faq/a4t-faq-lift-and-confidence.html) información sobre por qué las métricas calculadas no son compatibles con el alza y la confianza. Sin embargo, las métricas calculadas pueden utilizarse en sistemas de informes de A4T fuera de estas métricas. |
| ¿Por qué los visitantes únicos varían entre Destinatario y Analytics? | [Obtenga más](https://docs.adobe.com/content/help/en/target/using/integrate/a4t/a4t-faq/a4t-faq-viewing-reports.html) información sobre las variaciones de visitantes únicos entre productos. |
| Cuando se aplica un segmento de visita para una actividad de Destinatario específica en mi análisis, ¿por qué se devuelven experiencias no relacionadas? | La dimensión de A4T es una variable de lista, lo que significa que puede contener muchas actividades (y experiencias) a la vez. [Más información](https://docs.adobe.com/content/help/en/target/using/integrate/a4t/a4t-faq/a4t-faq-viewing-reports.html) |
| ¿La métrica de confianza representa los pedidos extremos o aplica una corrección de Bonferroni para varias ofertas? | No. [Obtenga más](https://docs.adobe.com/content/help/en/target/using/integrate/a4t/a4t-faq/a4t-faq-lift-and-confidence.html) información sobre cómo Analytics calcula la confianza. |

Para obtener más información sobre Analytics para el sistema de informes de Destinatario, visite el sistema de informes de [A4T](https://docs.adobe.com/content/help/en/target/using/integrate/a4t/reporting.html)

---
description: El panel Análisis para Destinatario (A4T) le permite analizar sus actividades y experiencias de Adobe Destinatario en el área de trabajo de Análisis.
title: Panel de Analytics para Destinatario (A4T)
translation-type: tm+mt
source-git-commit: 354bc118c869bd926a1cef0a75f5133d1a410cd5
workflow-type: tm+mt
source-wordcount: '613'
ht-degree: 14%

---


# Panel de Analytics para Destinatario (A4T)

>[!IMPORTANT]
>
>**[!UICONTROL El panel de Analytics para Destinatario (A4T)]** está actualmente en pruebas limitadas. [Más información](https://docs.adobe.com/content/help/en/analytics/landing/an-releases.html)

El panel Análisis para Destinatario (A4T) permite analizar las actividades y experiencias de Adobe Destinatario en el área de trabajo de Análisis. También le permite ver el alza y la confianza de hasta 3 métricas de éxito. Para acceder al panel A4T, navegue a un grupo de informes con componentes de A4T activados. A continuación, haga clic en el icono del panel situado en el extremo izquierdo y arrastre el panel Análisis para Destinatario a su proyecto de Espacio de trabajo de Análisis.

## Generador de paneles

Puede configurar el panel A4T con esta configuración:

| Configuración | Descripción |
|---|---|
| Actividad de Target | Seleccione una lista de Actividades de Destinatario o arrastre y suelte una actividad desde el carril izquierdo.<br>**Nota:**La lista se llena con los últimos 6 meses de actividades que han tenido al menos 1 visita. Si no ve una actividad en la lista, puede ser mayor de 6 meses. Todavía se puede añadir desde el carril izquierdo, que tiene un periodo retroactivo de hasta 18 meses. |
| Experiencia de control | Seleccione la experiencia de control. Puede cambiarlo si es necesario en la lista desplegable. |
| Métrica de normalización | Elija entre Visitantes únicos, visitas o impresiones de Actividad. Se recomiendan visitantes únicos para la mayoría de los casos de uso de análisis. |
| Métricas de éxito | Seleccione hasta 3 eventos de éxito estándar en los menús desplegables o arrastre y suelte las métricas desde el carril izquierdo. Cada métrica tendrá una tabla y una visualización dedicadas en el panel procesado. |
| Intervalo de fechas del calendario | Esto se rellenará automáticamente en función del intervalo de fechas de Actividad de Adobe Destinatario. Puede cambiarlo si es necesario. |

![](assets/a4t-panel-builder.png)

## Salida de panel

El panel Análisis para Destinatario devuelve un completo conjunto de datos y visualizaciones para ayudarle a comprender mejor el rendimiento de la actividad y las experiencias de Adobe Destinatario. En la parte superior del panel, se proporciona una línea de resumen para recordarle la configuración del panel seleccionada. En cualquier momento, puede editar el panel haciendo clic en el lápiz de edición en la parte superior derecha.

Para cada métrica de éxito seleccionada, se mostrará una tabla improvisada y una tendencia de tasa de conversión:

![](assets/a4t-rendered.png)

Cada tabla improvisada muestra las siguientes columnas de métricas:

| Métrica | Descripción |
|---|---|
| Normalización de métricas | Visitantes únicos, visitas o impresiones de Actividad. |
| Métricas de éxito | La métrica seleccionada en el generador |
| Tasa de conversión | Métrica de éxito/métrica de normalización |
| Alza | Compara la tasa de conversión de cada experiencia con la experiencia de control.<br>**Nota:**El alza es una &quot;métrica bloqueada&quot; de las experiencias de Destinatario; no se puede desglosar ni utilizar con otras dimensiones. |
| Alza (inferior) | Representa la peor elevación que una experiencia de variante podría tener sobre el control. |
| Alza (media) | Representa la elevación media que una experiencia de variante podría tener sobre el control con un intervalo de confianza del 95 %. Esto es &quot;Alza&quot; en Informes y análisis. |
| Alza (superior) | Representa la mejor elevación que una experiencia de variante podría tener sobre el control. |
| Confianza | La prueba T de los estudiantes calcula el nivel de confianza, lo que indica la probabilidad de que los resultados se dupliquen si la prueba se ejecuta de nuevo. Se ha aplicado a la métrica un rango de formato condicional fijo del 75%/85%/95%. Este formato se puede personalizar si es necesario en Configuración de columna. <br>**Nota:**La confianza es una &quot;métrica bloqueada&quot; para las experiencias de Adobe Destinatario. No se puede desglosar ni utilizar con otras dimensiones. |

Al igual que con cualquier panel de Análisis Workspace, puede continuar con la análisis agregando tablas y [visualizaciones](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html) adicionales que le ayudarán a analizar sus actividades de Adobe Destinatario.

Para obtener más opciones sobre Analytics para el sistema de informes de Destinatario, visite [A4T sistema de informes](https://docs.adobe.com/content/help/en/target/using/integrate/a4t/reporting.html)

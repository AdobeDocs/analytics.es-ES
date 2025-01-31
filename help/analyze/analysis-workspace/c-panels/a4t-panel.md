---
description: El panel Analytics for Target (A4T) le permite analizar las actividades y experiencias de Adobe Target en Analysis Workspace.
title: Panel de Analytics for Target (A4T)
feature: Panels
role: User, Admin
exl-id: 36bca104-37b8-43c6-b8d0-b607a9a333cc
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: tm+mt
source-wordcount: '1130'
ht-degree: 43%

---

# Panel de Analytics for Target {#analyze-for-target-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_a4t_button"
>title="Analytics for Target"
>abstract="Analizar actividades y experiencias de Target en Analysis Workspace."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_a4t_panel"
>title="Panel de Analytics for Target"
>abstract="Analizar actividades y experiencias de Target en Analysis Workspace.<br/><br>**Parámetros **<br/>**Actividad de destino**: La actividad de destino analizada.<br/>**Experiencia de control**: Experiencia de control para la actividad de Target seleccionada.<br/>**Métrica de normalización**: Visitantes, visitas o impresiones. Esta métrica (también denominada metodología de contabilización) se convierte en el denominador del cálculo del alza. También afecta a la manera en que se agregan los datos antes de que se calcule la confianza.<br/>**Métricas de éxito**: Hasta 3 métricas de éxito estándar (no calculadas) con las que analizar la actividad de Target."

<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_Este artículo documenta el panel de Analytics for Target en_ ![Adobe Analytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**._<br/>_Consulte [Panel de experimentación](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/panels/a4t-panel) para obtener información sobre cómo comparar diferentes variaciones de experiencias de usuario, marketing o mensajería en_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**._

>[!ENDSHADEBOX]

El panel Analytics for Target le permite analizar las actividades y experiencias de Adobe Target en Analysis Workspace. El panel también le permite ver el alza y la confianza hasta en 3 métricas de éxito. Para acceder al panel de Analytics for Target, vaya a un grupo de informes con los componentes de Analytics for Target habilitados. A continuación, seleccione el icono del panel en el extremo izquierdo y arrastre el panel Analytics for Target a su proyecto de Analysis Workspace.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Panel de Analytics for Target](https://video.tv.adobe.com/v/37247?quality=12&learn=on){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]

## Utiliza

Para usar un panel de **[!UICONTROL Analytics for Target]**:

1. Crear un panel de **[!UICONTROL Analytics for Target]**. Para obtener información sobre cómo crear un panel, consulta [Crear un panel](panels.md#create-a-panel).

1. Especifica la [entrada](#panel-input) para el panel.

1. Observa la [salida](#panel-output) del panel.

### Entrada de panel {#panel-nput}

Puede configurar el panel de Analytics for Target con esta configuración de entrada:

![Entrada del panel A4T](assets/a4t-panel-input.png)

| Configuración | Descripción |
|---|---|
| **[!UICONTROL Actividad de Target]** | Seleccione de una lista de actividades de Target. La lista se rellena con los últimos 6 meses de actividades que han tenido al menos 1 visita. Si no ve una actividad en la lista, puede haberse producido hace más de 6 meses. Todavía se puede añadir desde el carril izquierdo, que tiene un periodo retrospectivo que incluye hasta 18 meses. |
| **[!UICONTROL Experiencia de control]** | Seleccione la experiencia de control. |
| **[!UICONTROL Métrica de normalización]** | Seleccionar visitantes, visitas o impresiones. Se recomiendan [!UICONTROL Visitantes] para la mayoría de los casos de uso de análisis. Esta métrica (también denominada metodología de contabilización) se convierte en el denominador del cálculo del alza. También afecta a la manera en que se agregan los datos antes de que se calcule la confianza. |
| **[!UICONTROL Métricas de éxito]** | Seleccione hasta 3 eventos de éxito estándar (no calculados) en el menú desplegable o arrastre y suelte las métricas desde Métricas en el carril Componentes. Cada métrica tiene una tabla y una visualización dedicadas en el panel procesado. |

Seleccione **[!UICONTROL Generar]** para generar el panel.

### Salida de panel {#panel-output}

El panel de Analytics for Target devuelve un conjunto completo de datos y visualizaciones para ayudarle a comprender mejor el rendimiento de la actividad y las experiencias de Adobe Target. En la parte superior del panel, se proporciona una línea de resumen para recordarle la configuración del panel seleccionada. Para cada métrica de éxito seleccionada, se muestra una [tabla de forma libre](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md) y una visualización de [Línea](/help/analyze/analysis-workspace/visualizations/line.md) que muestra la tendencia de la tasa de conversión:

![Procesado](assets/a4t-panel-output.png)

Cada tabla de forma libre muestra las siguientes columnas de métricas:

| Métrica | Descripción |
|---|---|
| **[!UICONTROL Métricas de normalización]** | La métrica de normalización seleccionada en el panel de entrada es Visitantes únicos, Visitas o Impresiones de actividad. |
| **[!UICONTROL Métrica de éxito]** | La métrica de éxito seleccionada en el panel de entrada. |
| **[!UICONTROL Tasa de conversión]** | La métrica de éxito/métrica de normalización. |
| **[!UICONTROL Alza]** | Compara la tasa de conversión de cada experiencia con la experiencia de control. Nota: El alza es una *métrica bloqueada* de las experiencias de Target; no se puede desglosar ni utilizar con otras dimensiones. |
| **[!UICONTROL Alza (inferior)]** | Este valor representa la peor elevación que una experiencia de variante podría tener sobre el control con un intervalo de confianza del 95 %.<br>Consulte [Cálculos estadísticos](https://experienceleague.adobe.com/en/docs/target/using/reports/statistical-methodology/statistical-calculations) y el archivo de Excel [Calculadora de confianza completa](https://experienceleague.adobe.com/docs/target/assets/complete_confidence_calculator.xlsx) para obtener más información. |
| **[!UICONTROL Alza (media)]** | Este valor representa la elevación media que una experiencia de variante podría tener sobre el control con un intervalo de confianza del 95 %. <br>Consulte [Cálculos estadísticos](https://experienceleague.adobe.com/en/docs/target/using/reports/statistical-methodology/statistical-calculations) y el archivo de Excel [Calculadora de confianza completa](https://experienceleague.adobe.com/docs/target/assets/complete_confidence_calculator.xlsx) para obtener más información. |
| **[!UICONTROL Alza (superior)]** | Este valor representa la mejor elevación que una experiencia de variante podría tener sobre el control con un intervalo de confianza del 95 %.<br>Consulte [Cálculos estadísticos](https://experienceleague.adobe.com/en/docs/target/using/reports/statistical-methodology/statistical-calculations) y el archivo de Excel [Calculadora de confianza completa](https://experienceleague.adobe.com/docs/target/assets/complete_confidence_calculator.xlsx) para obtener más información. |
| **[!UICONTROL Confianza]** | La prueba T-test para estudiantes calcula el nivel de confianza, que indica la probabilidad de que los resultados se dupliquen si se vuelve a ejecutar la prueba. Se ha aplicado a la métrica un rango de formato condicional fijo del 75%/85%/95%. Este formato se puede personalizar, si es necesario, desde Configuración de columna. Nota: La confianza es una “métrica bloqueada” para las experiencias de Target; no se puede desglosar ni utilizar con otras dimensiones.<br>Consulte [Cálculos estadísticos](https://experienceleague.adobe.com/en/docs/target/using/reports/statistical-methodology/statistical-calculations) y el archivo de Excel [Calculadora de confianza completa](https://experienceleague.adobe.com/docs/target/assets/complete_confidence_calculator.xlsx) para obtener más información. |

Como con cualquier panel de Analysis Workspace, puede continuar con su análisis agregando tablas y [visualizaciones](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations) adicionales que le ayudarán a analizar sus actividades de Adobe Target. También puede aplicar un segmento en el nivel de panel o en la tabla de forma libre. Tenga en cuenta que si lo agrega dentro de la tabla de forma libre, debe superponerlo en toda la tabla para conservar los cálculos de elevación y confianza. Los segmentos de nivel de columna no son compatibles en este momento.

Use ![Editar](/help/assets/icons/Edit.svg) para reconfigurar y reconstruir el panel.

## Preguntas frecuentes {#FAQ}

| Pregunta | Respuesta |
|---|---|
| ¿Qué tipos de actividades se admiten en Analytics for Target? | [Obtenga más información](https://experienceleague.adobe.com/en/docs/target/using/integrate/a4t/a4t-faq/a4t-faq-activity-setup) sobre los tipos de actividad admitidos. |
| ¿Se admiten las métricas calculadas en los cálculos de alza y confianza? | No. [Obtenga más información](https://experienceleague.adobe.com/en/docs/target/using/integrate/a4t/a4t-faq/a4t-faq-lift-and-confidence) sobre por qué las métricas calculadas no son compatibles con el alza y la confianza. Sin embargo, las métricas calculadas pueden utilizarse en los informes de Analytics for Target fuera de estas métricas. |
| ¿Por qué los visitantes únicos varían entre Target y Analytics? | [Más información](https://experienceleague.adobe.com/en/docs/target/using/integrate/a4t/a4t-faq/a4t-faq-viewing-reports) sobre las variaciones de visitantes únicos entre productos. |
| Cuando se aplica un segmento de visita para una actividad de Target específica en mi análisis, ¿por qué se devuelven experiencias no relacionadas? | La dimensión de Analytics para Target es una variable de lista, lo que significa que puede contener muchas actividades (y experiencias) a la vez. [Más información](https://experienceleague.adobe.com/en/docs/target/using/integrate/a4t/a4t-faq/a4t-faq-viewing-reports) |
| ¿La métrica de confianza representa los pedidos extremos o aplica una corrección de Bonferroni para varias ofertas? | No. [Obtenga más información](https://experienceleague.adobe.com/en/docs/target/using/integrate/a4t/a4t-faq/a4t-faq-lift-and-confidence) sobre cómo Analytics calcula la confianza. |
| ¿Pueden utilizarse métricas de alza y confianza con otras dimensiones o desgloses? | El alza y la confianza son “métricas bloqueadas” a la dimensión de experiencias de Target, porque requieren un control y una variante para calcularlas. De este modo, no pueden desglosarse ni utilizarse con otras dimensiones. |
| ¿Cuándo se vuelven a calcular el alza y la confianza? | El alza y la confianza se vuelven a calcular cada vez que se crea el panel, su intervalo de fechas cambia o se aplica un segmento al panel o la tabla. Cuando se aplica un filtro de segmento a la tabla de forma libre, el segmento debe aplicarse en todas las columnas o el alza y la confianza no se actualizan correctamente. No se admiten segmentos de nivel de columna. |

Para obtener más información acerca de los informes de Analytics for Target, visite [Informes de Analytics for Target](https://experienceleague.adobe.com/en/docs/target/using/integrate/a4t/reporting)

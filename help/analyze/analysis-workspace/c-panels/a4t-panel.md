---
description: El panel Analytics for Target (A4T) le permite analizar las actividades y experiencias de Adobe Target en Analysis Workspace.
title: Panel de Analytics for Target (A4T)
feature: Panels
role: User, Admin
exl-id: 36bca104-37b8-43c6-b8d0-b607a9a333cc
source-git-commit: 7bac64aed46d9d7a83dc61c3f55d33ad56564efe
workflow-type: tm+mt
source-wordcount: '1158'
ht-degree: 70%

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
>abstract="Analizar actividades y experiencias de Target en Analysis Workspace.<br/><br>**Parámetros **<br/>**Actividad de destino**: La actividad de destino que se analizará.<br/>**Experiencia de control**: Experiencia de control para la actividad de Target seleccionada.<br/>**Métrica de normalización**: Visitantes, visitas o impresiones. Esta métrica (también denominada metodología de contabilización) se convierte en el denominador del cálculo del alza. También afecta a la manera en que se agregan los datos antes de que se calcule la confianza.<br/>**Métricas de éxito**: Hasta 3 métricas de éxito estándar (no calculadas) con las que analizar la actividad de Target."

<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

*Este artículo documenta el panel de Analytics for Target en **Adobe Analytics**.<br/>Consulte [Panel de experimentación](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/panels/a4t-panel) para obtener información sobre cómo comparar diferentes variaciones de experiencias de usuario, marketing o mensajería en **Customer Journey Analytics**.*

>[!ENDSHADEBOX]

El panel Analytics for Target le permite analizar las actividades y experiencias de Adobe Target en Analysis Workspace. El panel también le permite ver el alza y la confianza hasta en 3 métricas de éxito. Para acceder al panel de Analytics for Target, vaya a un grupo de informes con los componentes de Analytics for Target habilitados. A continuación, seleccione el icono del panel en el extremo izquierdo y arrastre el panel Analytics for Target a su proyecto de Analysis Workspace.

+++A continuación, se muestra un breve vídeo introductorio del panel Analytics for Target:

>[!VIDEO](https://video.tv.adobe.com/v/37247/?quality=12)

+++

## Utiliza

Para usar un panel de **[!UICONTROL Analytics for Target]**:

1. Crear un panel de **[!UICONTROL Analytics for Target]**. Para obtener información sobre cómo crear un panel, consulta [Crear un panel](panels.md#create-a-panel).

1. Especifica la [entrada](#panel-input) para el panel.

1. Observa la [salida](#panel-output) del panel.

### Entrada de panel {#panel-nput}

Puede configurar el panel de Analytics for Target con esta configuración de entrada:

| Configuración | Descripción |
|---|---|
| **[!UICONTROL Actividad de Target]** | Seleccione una lista de Actividades de Target o arrastre y suelte una actividad desde el carril izquierdo. Nota: La lista se rellena con los últimos 6 meses de actividades que han tenido al menos 1 visita. Si no ve una actividad en la lista, puede haberse producido hace más de 6 meses. Todavía se puede añadir desde el carril izquierdo, que tiene un periodo retrospectivo que incluye hasta 18 meses. |
| **[!UICONTROL Experiencia de control]** | Seleccione la experiencia de control. Puede cambiarla, si es necesario, en la lista desplegable. |
| **[!UICONTROL Métrica de normalización]** | Elija entre Visitantes únicos, Visitas o Impresiones de actividad. Se recomiendan visitantes únicos para la mayoría de los casos de uso de análisis. Esta métrica (también denominada metodología de contabilización) se convierte en el denominador del cálculo del alza. También afecta a la manera en que se agregan los datos antes de que se calcule la confianza. |
| **[!UICONTROL Métricas de éxito]** | Seleccione hasta 3 eventos de éxito estándar (no calculados) en la lista desplegable o arrastre y suelte las métricas desde el carril izquierdo. Cada métrica tendrá una tabla y una visualización dedicadas en el panel procesado. |
| C**[!UICONTROL intervalo de fechas del calendario]** | Esto se rellenará automáticamente en función del intervalo de fechas de Actividad de Adobe Target. Puede cambiarlo si es necesario. |

![Generador de paneles](assets/a4t-panel-builder2.png)

### Salida de panel {#panel-output}

El panel de Analytics for Target devuelve un conjunto completo de datos y visualizaciones para ayudarle a comprender mejor el rendimiento de la actividad y las experiencias de Adobe Target. En la parte superior del panel, se proporciona una línea de resumen para recordarle la configuración del panel seleccionada. En cualquier momento, puede editar el panel haciendo clic en el lápiz de edición en la parte superior derecha.

Para cada métrica de éxito seleccionada, se mostrará una tabla de forma libre y una tendencia de tasa de conversión:

![Procesado](assets/a4t-rendered.png)

Cada tabla de forma libre muestra las siguientes columnas de métricas:

| Métrica | Descripción |
|---|---|
| **[!UICONTROL Métricas de normalización]** | Visitantes únicos, Visitas o Impresiones de actividad. |
| **[!UICONTROL Métrica de éxito]** | La métrica seleccionada en el generador |
| **[!UICONTROL Tasa de conversión]** | Métrica de éxito/métrica de normalización |
| **[!UICONTROL Alza]** | Compara la tasa de conversión de cada experiencia con la experiencia de control. Nota: El alza es una “métrica bloqueada” de las experiencias de Target, no se puede desglosar ni utilizar con otras dimensiones. |
| **[!UICONTROL Alza (inferior)]** | Representa la peor elevación que una experiencia de variante podría tener sobre el control con un intervalo de confianza del 95 %.<br>Consulte [Cálculos estadísticos](https://experienceleague.adobe.com/docs/target/using/reports/statistical-methodology/statistical-calculations.html) y el archivo de Excel [Calculadora de confianza completa](https://experienceleague.adobe.com/docs/target/assets/complete_confidence_calculator.xlsx) para obtener más información. |
| **[!UICONTROL Alza (media)]** | Representa la elevación media que una experiencia de variante podría tener sobre el control con un intervalo de confianza del 95 %. <br>Consulte [Cálculos estadísticos](https://experienceleague.adobe.com/docs/target/using/reports/statistical-methodology/statistical-calculations.html) y el archivo de Excel [Calculadora de confianza completa](https://experienceleague.adobe.com/docs/target/assets/complete_confidence_calculator.xlsx) para obtener más información. |
| **[!UICONTROL Alza (superior]**) | Representa la mejor elevación que una experiencia de variante podría tener sobre el control con un intervalo de confianza del 95 %.<br>Consulte [Cálculos estadísticos](https://experienceleague.adobe.com/docs/target/using/reports/statistical-methodology/statistical-calculations.html) y el archivo de Excel [Calculadora de confianza completa](https://experienceleague.adobe.com/docs/target/assets/complete_confidence_calculator.xlsx) para obtener más información. |
| **[!UICONTROL Confianza]** | La prueba T-test para estudiantes calcula el nivel de confianza, que indica la probabilidad de que los resultados se dupliquen si se vuelve a ejecutar la prueba. Se ha aplicado a la métrica un rango de formato condicional fijo del 75%/85%/95%. Este formato se puede personalizar, si es necesario, desde Configuración de columna. Nota: La confianza es una “métrica bloqueada” para las experiencias de Target; no se puede desglosar ni utilizar con otras dimensiones.<br>Consulte [Cálculos estadísticos](https://experienceleague.adobe.com/docs/target/using/reports/statistical-methodology/statistical-calculations.html) y el archivo de Excel [Calculadora de confianza completa](https://experienceleague.adobe.com/docs/target/assets/complete_confidence_calculator.xlsx) para obtener más información. |

Como con cualquier panel de Analysis Workspace, puede continuar con el análisis agregando tablas y [visualizaciones](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html?lang=es) adicionales que le ayudarán a analizar sus actividades de Adobe Target. También puede aplicar un segmento en el nivel de panel o en la tabla de forma libre. Tenga en cuenta que si lo agrega dentro de la tabla de forma libre, debe superponerlo en toda la tabla para conservar los cálculos de elevación y confianza. Los segmentos de nivel de columna no son compatibles en este momento.

## Preguntas frecuentes {#FAQ}

| Pregunta | Respuesta |
|---|---|
| ¿Qué tipos de actividades se admiten en Analytics for Target? | [Obtenga más información](https://experienceleague.adobe.com/docs/target/using/integrate/a4t/a4t-faq/a4t-faq-activity-setup.html?lang=es) sobre los tipos de actividad admitidos. |
| ¿Se admiten las métricas calculadas en los cálculos de alza y confianza? | No. [Obtenga más información](https://experienceleague.adobe.com/docs/target/using/integrate/a4t/a4t-faq/a4t-faq-lift-and-confidence.html?lang=es) sobre por qué las métricas calculadas no son compatibles con el alza y la confianza. Sin embargo, las métricas calculadas pueden utilizarse en los informes de Analytics for Target fuera de estas métricas. |
| ¿Por qué los visitantes únicos varían entre Target y Analytics? | [Obtenga más información](https://experienceleague.adobe.com/docs/target/using/integrate/a4t/a4t-faq/a4t-faq-viewing-reports.html?lang=es) sobre las variaciones de visitantes únicos entre productos. |
| Cuando se aplica un segmento de visita para una actividad de Target específica en mi análisis, ¿por qué se devuelven experiencias no relacionadas? | La dimensión de Analytics para Target es una variable de lista, lo que significa que puede contener muchas actividades (y experiencias) a la vez. [Más información](https://experienceleague.adobe.com/docs/target/using/integrate/a4t/a4t-faq/a4t-faq-viewing-reports.html?lang=es) |
| ¿La métrica de confianza representa los pedidos extremos o aplica una corrección de Bonferroni para varias ofertas? | No. [Obtenga más información](https://experienceleague.adobe.com/docs/target/using/integrate/a4t/a4t-faq/a4t-faq-lift-and-confidence.html?lang=es) sobre cómo Analytics calcula la confianza. |
| ¿Pueden utilizarse métricas de alza y confianza con otras dimensiones o desgloses? | El alza y la confianza son “métricas bloqueadas” a la dimensión de experiencias de Target, porque requieren un control y una variante para calcularlas. De este modo, no pueden desglosarse ni utilizarse con otras dimensiones. |
| ¿Cuándo se vuelven a calcular el alza y la confianza? | La elevación y la confianza se vuelven a calcular cada vez que se ejecuta (o se vuelve a ejecutar) el panel, su intervalo de fechas cambia o se aplica un segmento al panel o la tabla. Al aplicar un filtro de segmento a la tabla de forma libre, debe aplicarse en todas las columnas, o la elevación y la confianza no se actualizarán correctamente. Los segmentos de nivel de columna no son compatibles en este momento. |

Para obtener más información acerca de los informes de Analytics for Target, visite [Informes de Analytics for Target](https://experienceleague.adobe.com/docs/target/using/integrate/a4t/reporting.html?lang=es)

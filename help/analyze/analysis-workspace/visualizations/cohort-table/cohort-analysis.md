---
keywords: Analysis Workspace
title: ¿Qué es el análisis de cohorte?
topic: Reports and analytics
uuid: 39a83f3a-15d1-41d7-bcdd-50c22aed8f1c
translation-type: tm+mt
source-git-commit: 5d4c0ae58dfb7c54b00f801aebe898f790432903
workflow-type: tm+mt
source-wordcount: '478'
ht-degree: 91%

---


# ¿Qué es el análisis de cohorte?

Una *`cohort`* es un grupo de personas que comparten características en común durante un periodo especificado. El análisis de cohorte es útil, por ejemplo, cuando desea saber cómo se involucra una cohorte con una marca. Puede identificar fácilmente los cambios en tendencias y responder en consecuencia. (Las explicaciones de análisis de cohorte se encuentran disponibles en la web, como en [Cohort Analysis 101 ](https://en.wikipedia.org/wiki/Cohort_analysis)(Guía de análisis de cohorte))

Después de crear un informe de cohorte, puede depurar sus componentes (dimensiones, métricas y segmentos específicos), y luego compartir el informe de cohorte con quien desee. Consulte  [Depurar y compartir](/help/analyze/analysis-workspace/curate-share/curate.md).

Ejemplos de lo que puede hacer con el análisis de cohorte:

* Iniciar campañas diseñadas para generar una acción deseada.
* Modificar el presupuesto de mercadotecnia en el momento justo del ciclo de vida del cliente.
* Reconocer cuándo finalizar una prueba o una oferta, para maximizar el valor.
* Obtener ideas para pruebas A/B en áreas como precios, ruta de actualización, etc.
* Ver un informe de análisis de cohorte dentro de un informe de análisis guiado.

El análisis de cohorte está disponible para todos los clientes de Analytics con derechos de acceso a Analysis Workspace.

[Análisis de cohorte en YouTube](https://www.youtube.com/watch?v=kqOIYrvV-co&amp;index=45&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) (4:36)

>[!IMPORTANT]
>
>La Análisis de cohorte no admite métricas no segmentables, como métricas calculadas, métricas no enteras o [!UICONTROL Ocurrencias]. En la Análisis de cohorte solo se pueden usar las métricas que se pueden usar en segmentos, y solo se pueden incrementar en 1 cada vez.

## Capacidades del análisis de cohorte

En enero de 2019, Adobe lanzó una versión nueva y considerablemente mejorada del análisis de cohorte. Ofrece un control mucho más preciso de las cohortes que genera. Estas son las mejoras destacadas:

### Tabla de retención

Un informe de cohorte de retención devuelve la información de visitantes: cada celda de datos muestra el número sin procesar y el porcentaje de visitantes en la cohorte que realizó la acción durante ese período de tiempo. Se pueden incluir hasta 3 métricas y hasta 10 segmentos.

![](assets/retention-report.png)

### Tabla de pérdida

Una cohorte de pérdida es la inversa de una tabla de retención y muestra a los visitantes que abandonaron o que no llegaron a satisfacer los criterios de regreso de su cohorte a lo largo del tiempo. Se pueden incluir hasta 3 métricas y hasta 10 segmentos.

![](assets/churn-report.png)

### Cálculo móvil

Permite calcular la retención o la pérdida en función de la columna previa, no de la columna incluida.

![](assets/cohort-rolling-calculation.png)

### Tabla de latencia

Mide el tiempo transcurrido antes y después de ocurrir el evento de inclusión. Es una excelente herramienta para el análisis previo/posterior. La columna &quot;Incluido&quot; está en el centro de la tabla y a ambos lados se muestran los periodos de tiempo antes y después del evento de inclusión.

![](assets/cohort-latency.png)

### Cohorte de dimensión personalizada

Cree cohortes basadas en una dimensión seleccionada y no en el tiempo, que es el comportamiento predeterminado. Utilice dimensiones como canal de marketing, campaña, producto, página, región o cualquier otra dimensión de Adobe Analytics para mostrar cómo cambia la retención en función de los distintos valores que adoptan.

![](assets/cohort-customizable-cohort-row.png)

Para obtener instrucciones sobre cómo se configura y ejecuta un informe de cohorte, visite  [Configurar un informe de análisis de cohorte](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md).


---
description: Obtenga más información sobre
title: Tipo de métrica y atribución
feature: Calculated Metrics
exl-id: 3fb98227-e2ef-4829-ae84-812f845470ee
source-git-commit: 21c4d1b591daf7229bd36845e42e2dec473e792f
workflow-type: ht
source-wordcount: '635'
ht-degree: 100%

---

# Tipo de métrica y atribución {#metric-type-attribution}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attributionmodel"
>title="Modelo"
>abstract="Seleccione un modelo de atribución para la métrica."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lasttouch"
>title="Último contacto"
>abstract="El 100 % del crédito se destina al último valor de dimensión visto por un visitante."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_firsttouch"
>title="Primer contacto"
>abstract="El 100 % del crédito se destina al primer valor de dimensión visto por un visitante."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_linear"
>title="Lineal"
>abstract="El crédito se distribuye de manera uniforme en todos los valores de dimensión."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_participation"
>title="Participación"
>abstract="100 % de crédito a cada valor de dimensión visto por un visitante.<br/>Los totales de columna están sobreestimados."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_sametouch"
>title="Mismo contacto"
>abstract="El crédito se otorga solo a los valores de dimensión que se producen en el mismo evento que la conversión."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_instance"
>title="Mismo contacto"
>abstract="El crédito se otorga solo a los valores de dimensión que se producen en el mismo evento que la conversión."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_ushaped"
>title="Forma de U"
>abstract="40 % de crédito al primer valor de dimensión, 40 % al último, 20 % compartido por el medio."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_jcurve"
>title="Curva J"
>abstract="60 % de crédito al último valor de dimensión, 20 % al primero y 20 % compartido por el medio."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_jshaped"
>title="Curva J"
>abstract="60 % de crédito al último valor de dimensión, 20 % al primero y 20 % compartido por el medio."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_inversej"
>title="J inversa"
>abstract="60 % de crédito al primer valor de dimensión, 20 % al último, 20 % compartido por el medio."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_reversejshaped"
>title="J inversa"
>abstract="60 % de crédito al primer valor de dimensión, 20 % al último, 20 % compartido por el medio."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_timedecay"
>title="Deterioro de tiempo"
>abstract="Los valores de dimensión más cercanos en el tiempo a una conversión obtienen la mayor cantidad de crédito."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_custom"
>title="Personalizado"
>abstract="Defina su propia ponderación de atribución basada en la posición."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_positionbased"
>title="Personalizado"
>abstract="Defina su propia ponderación de atribución basada en la posición."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_algorithmic"
>title="Algorítmico"
>abstract="El crédito se determina de forma dinámica mediante un algoritmo estadístico."


>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_container"
>title="Contenedor"
>abstract="Seleccione un contenedor para establecer el ámbito deseado para la atribución."


>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lookbackwindow"
>title="Ventana de retroactividad"
>abstract="Este ajuste determina la ventana de atribución de datos que se aplicará a cada conversión."

Al [crear una métrica calculada](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md), puede especificar el tipo de métrica y el modelo de atribución.

## Tipo de métrica

Para especificar el tipo de métrica al crear una métrica calculada:

1. Seleccione el icono de engranaje situado junto a la métrica cuyo tipo desee seleccionar.

   ![](assets/cm_type_alloc.png)

1. Elija entre las siguientes opciones:

   | Tipo de métrica | Definición |
   |---|---|
   | Estándar | Estas métricas son las mismas métricas utilizadas en los informes de [!DNL Analytics] estándares. Si una fórmula consiste en una única métrica estándar, muestra datos idénticos a los de su métrica no calculada homóloga. Las métricas estándar son útiles para crear métricas calculadas específicas para cada elemento de línea individual. Por ejemplo, [Pedidos] / [Visitas] toma pedidos de ese elemento de línea en concreto y lo divide por el número de visitas de ese elemento de línea específico. |
   | Total general | Utilice el total general para el período de generación de informes de cada elemento de línea. Si una fórmula consiste en una única métrica total general, muestra el mismo número total en cada elemento de línea. Las métricas totales generales son útiles para crear métricas calculadas que se comparan con los datos totales del sitio. Por ejemplo, [Pedidos] / [Visitas totales] muestra la proporción de pedidos en comparación con TODAS las visitas de su sitio, no solo las visitas de una línea en concreto. |

## Funcionamiento de la asignación lineal

[Atribución](/help/analyze/analysis-workspace/attribution/overview.md) es la forma en que se evalúan los modelos de asignación en las métricas calculadas.

Para obtener una lista completa de los modelos de atribución no predeterminados y de las ventanas retroactivas, consulte [Modelos de atribución y ventanas retroactivas](/help/analyze/analysis-workspace/attribution/models.md).

El ejemplo siguiente ilustra cómo funcionan las métricas calculadas con la asignación lineal en los informes:

| | Visita 1 | Visita 2 | Visita 3 | Visita 4 | Visita 5 | Visita 6 | Visita 7 |
|--- |--- |--- |--- |--- |--- |--- |--- |
| Datos recibidos | PROMOCIÓN A | - | PROMOCIÓN A | PROMOCIÓN B | - | PROMOCIÓN C | $10 |
| eVar de último toque | PROMOCIÓN A | PROMOCIÓN A | PROMOCIÓN A | PROMOCIÓN B | PROMOCIÓN B | PROMOCIÓN C | $10 |
| eVar de primer toque | PROMOCIÓN A | PROMOCIÓN A | PROMOCIÓN A | PROMOCIÓN A | PROMOCIÓN A | PROMOCIÓN A | $10 |
| Prop de ejemplo | PROMOCIÓN A | - | PROMOCIÓN A | PROMOCIÓN B | - | PROMOCIÓN C | $10 |

En este ejemplo, los valores A, B y C se han enviado a una variable en las visitas 1, 3, 4 y 6 antes de realizarse una compra de 10 USD en la visita 7. En la segunda fila, estos valores persisten a lo largo de las visitas con base en una visita de último toque. La tercera fila ilustra una persistencia de visita de primer toque. Finalmente, la última fila ilustra de qué forma se registrarán los datos para una prop que no tiene persistencia.


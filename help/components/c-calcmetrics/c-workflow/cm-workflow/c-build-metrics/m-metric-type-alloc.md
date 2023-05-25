---
description: Obtenga más información sobre
title: Tipo de métrica y atribución
feature: Calculated Metrics
exl-id: 3fb98227-e2ef-4829-ae84-812f845470ee
source-git-commit: 4bf8397ee979614539baf21b36363eb03357567a
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 73%

---

# Tipo de métrica y atribución

Cuándo [creación de una métrica calculada](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md), puede especificar el tipo de métrica y el modelo de atribución.

## Tipo de métrica

Para especificar el tipo de métrica al crear una métrica calculada:

1. Seleccione el icono de engranaje situado junto a la métrica cuyo tipo desee seleccionar.

   ![](assets/cm_type_alloc.png)

1. Elija entre las siguientes opciones:

   | Tipo de métrica | Definición |
   |---|---|
   | Estándar | Estas métricas son las mismas métricas utilizadas en los informes de [!DNL Analytics] estándares. Si una fórmula consiste en una única métrica estándar, muestra datos idénticos a los de su métrica no calculada homóloga. Las métricas estándar son útiles para crear métricas calculadas específicas para cada elemento de línea individual. Por ejemplo, [Pedidos] / [Visitas] toma pedidos de ese elemento de línea en concreto y lo divide por el número de visitas de ese elemento de línea específico. |
   | Total general | Utilice el total general para el período de informe de cada elemento de línea. Si una fórmula consiste en una única métrica de total general, muestra el mismo número total en cada elemento de línea. Las métricas de total general son útiles para crear métricas calculadas que se comparan con los datos totales del sitio. Por ejemplo, [Pedidos] / [Visitas totales] muestra la proporción de pedidos en comparación con TODAS las visitas de su sitio, no solo las visitas de una línea en concreto. |

## Modelo de atribución de columnas

## Funcionamiento de la asignación lineal (a partir del 19 de julio de 2018)

[Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md) es cómo se evalúan los modelos de asignación en las métricas calculadas.

Para obtener una lista completa de los modelos de atribución no predeterminados y de las ventanas retroactivas, consulte [Modelos de atribución y ventanas retroactivas](/help/analyze/analysis-workspace/attribution/models.md).

El siguiente ejemplo ilustra cómo funcionan las métricas calculadas con asignaciones lineales en los informes:

|  | Visita 1 | Visita 2 | Visita 3 | Visita 4 | Visita 5 | Visita 6 | Visita 7 |
|--- |--- |--- |--- |--- |--- |--- |--- |
| Datos recibidos | PROMOCIÓN A | - | PROMOCIÓN A | PROMOCIÓN B | - | PROMOCIÓN C | $10 |
| eVar de último toque | PROMOCIÓN A | PROMOCIÓN A | PROMOCIÓN A | PROMOCIÓN B | PROMOCIÓN B | PROMOCIÓN C | $10 |
| eVar de primer toque | PROMOCIÓN A | PROMOCIÓN A | PROMOCIÓN A | PROMOCIÓN A | PROMOCIÓN A | PROMOCIÓN A | $10 |
| Prop de ejemplo | PROMOCIÓN A | - | PROMOCIÓN A | PROMOCIÓN B | - | PROMOCIÓN C | $10 |

En este ejemplo, los valores A, B y C se han enviado a una variable en las visitas 1, 3, 4 y 6 antes de realizarse una compra de 10 USD en la visita 7. En la segunda fila, estos valores persisten a lo largo de las visitas con base en una visita de último toque. La tercera fila ilustra una persistencia de visita de primer toque. Finalmente, la última fila ilustra de qué forma se registrarán los datos para una prop que no tiene persistencia.

## Diferencias entre el funcionamiento de la asignación lineal en Reports &amp; Analytics y Workspace

Hay algunas diferencias en el funcionamiento de la atribución lineal entre estas dos herramientas:

* En Reports &amp; Analytics, la atribución lineal (procesada) siempre se basa en visitas, mientras que en Workspace puede basarse en visitas o visitantes.
* En Reports &amp; Analytics, si no se pasa ningún valor en la primera visita individual de una visita, el valor (inicial) persistiría a partir de la visita anterior. Este NO es el caso en Workspace (Attribution IQ). Si no se pasa ningún valor en la primera visita individual de una visita, entonces “Ninguno” es el valor inicial.

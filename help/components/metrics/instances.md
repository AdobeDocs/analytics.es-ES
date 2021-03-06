---
title: Instancias
description: El número de visitas que se configuró una variable (y no persistió).
feature: Metrics
exl-id: 9d1a66b5-46f9-4834-87a1-5f63e386e61d
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: ht
source-wordcount: '129'
ht-degree: 100%

---

# Instancias

La métrica “Instancias” muestra el número de veces que una dimensión se ha definido explícitamente en una solicitud de imagen. Algunas dimensiones, como las [eVars](../dimensions/evar.md) persisten los elementos de dimensión más allá de la visita en la que están establecidas. Esta métrica resulta útil cuando desea ver el número de veces que se estableció un elemento de dimensión sin las visitas individuales en las que dicho valor persistió.

## Cálculo de esta métrica

De todas las visitas individuales de un grupo de informes, solo incluye las visitas que establecen explícitamente un elemento de dimensión en la solicitud de imagen. Algunas dimensiones, como las [eVars](../dimensions/evar.md), persisten más allá de la visita en la que están configuradas. Las métricas como [Vistas de página](page-views.md) y [Ocurrencias](occurrences.md) cuentan tanto los valores iniciales como los persistentes. Esta métrica no cuenta los valores persistentes.

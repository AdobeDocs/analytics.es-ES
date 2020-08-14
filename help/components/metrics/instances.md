---
title: 'Instancias '
description: El número de visitas que se configuró una variable (y no persistió).
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '129'
ht-degree: 52%

---


# Instancias 

La métrica “Instancias” muestra el número de veces que una dimensión se ha definido explícitamente en una solicitud de imagen. Some dimensions, such as [eVars](../dimensions/evar.md), persist dimension items past the hit they are set on. Esta métrica es útil cuando desea ver el número de veces que se configuró un elemento de dimensión sin las visitas individuales en las que dicho valor persistió.

## Cálculo de esta métrica

De todas las visitas individuales de un grupo de informes, solo incluye las visitas que establecen explícitamente un elemento de dimensión en la solicitud de imagen. Algunas dimensiones, como las [eVars](../dimensions/evar.md), persisten más allá de la visita en la que están configuradas. Las métricas como [Vistas de página](page-views.md) y [Ocurrencias](occurrences.md) cuentan tanto los valores iniciales como los persistentes. Esta métrica no cuenta los valores persistentes.
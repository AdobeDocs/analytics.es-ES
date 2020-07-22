---
title: Ocurrencias
description: Número de visitas que se configuró o persistió una variable.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 1%

---


# Ocurrencias

La métrica &quot;Ocurrencias&quot; muestra el número de visitas en las que se estableció o persistió una dimensión determinada. Cuando arrastra una dimensión en Workspace a un lienzo en blanco, Adobe aplica automáticamente esta métrica al proyecto.

## Cómo se calcula esta métrica

De todas las visitas individuales de un grupo de informes, incluya las visitas en las que se haya definido o mantenido un elemento de dimensión. Algunas dimensiones, como [las eVars](../dimensions/evar.md), persisten más allá de la visita en la que están configuradas. Las métricas como vistas [](page-views.md) de página y [Ocurrencias](occurrences.md) cuentan tanto los valores iniciales como los persistentes. Esta métrica no cuenta los valores persistentes.

## Comparar con métricas similares

* **Ocurrencias vs.[Instancias](instances.md)**: Las ocurrencias cuentan visitas individuales en las que se configuró o persistió un elemento de dimensión. Las instancias no incluyen visitas individuales en las que persiste un elemento de dimensión.
* **Ocurrencias vs. vistas[](page-views.md)**de página: Las ocurrencias incluyen todos los tipos de visitas, incluyendo las llamadas de seguimiento de vista de página ([`t()`](/help/implement/vars/functions/t-method.md)) y las llamadas de seguimiento de vínculos ([`tl()`](/help/implement/vars/functions/tl-method.md)). La métrica vistas de página solo incluye llamadas de seguimiento de vista de página y excluye las llamadas de seguimiento de vínculos.
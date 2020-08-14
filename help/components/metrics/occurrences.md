---
title: Ocurrencias
description: Número de visitas configurado o en las que persiste una variable.
translation-type: tm+mt
source-git-commit: 422e99d9ea70f0192443d7ebc3631c6bf99e7591
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 73%

---


# Ocurrencias

La métrica “Ocurrencias” muestra el número de visitas configurado o en las que persiste una variable. Cuando arrastra una dimensión en Workspace a un lienzo en blanco, Adobe aplica automáticamente esta métrica al proyecto.

## Cálculo de esta métrica

De todas las visitas individuales de un grupo de informes, incluya las visitas en las que se haya definido o mantenido un elemento de dimensión. Algunas dimensiones, como las [eVars](../dimensions/evar.md), persisten más allá de la visita en la que están configuradas. Las métricas como [Vistas de página](page-views.md) y [Ocurrencias](occurrences.md) cuentan tanto los valores iniciales como los persistentes.

## Comparar con métricas similares

* **Ocurrencias vs.[Instancias](instances.md)**: Las ocurrencias cuentan visitas individuales en las que se configuró o persistió un elemento de dimensión. Las instancias no incluyen visitas individuales en las que persiste un elemento de dimensión.
* **Ocurrencias vs.[Vistas de página](page-views.md)**: Las ocurrencias incluyen todos los tipos de visitas, incluyendo las llamadas de seguimiento de vista de página ([`t()`](/help/implement/vars/functions/t-method.md)) y las llamadas de seguimiento de vínculos ([`tl()`](/help/implement/vars/functions/tl-method.md)). La métrica vistas de página solo incluye llamadas de seguimiento de vista de página y excluye las llamadas de seguimiento de vínculos.

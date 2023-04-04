---
title: Ocurrencias
description: Número de visitas configurado o en las que persiste una variable.
feature: Metrics
exl-id: 8428e813-0fb4-4620-884e-1aa92fe33209
source-git-commit: 1be9a8ceb03f8102a0799f4518db35c1e8cd7b14
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 74%

---

# Ocurrencias

La métrica “Ocurrencias” muestra el número de visitas configurado o en las que persiste una variable. Cuando arrastra una dimensión en Workspace a un lienzo en blanco, Adobe aplica automáticamente esta métrica al proyecto.

## Cálculo de esta métrica

De todas las visitas individuales de un grupo de informes, incluya las visitas en las que se define o persiste un valor de dimensión. Algunas dimensiones, como las [eVars](../dimensions/evar.md), persisten más allá de la visita en la que están configuradas. Esta métrica cuenta tanto los valores iniciales como los persistentes.

## Comparar con métricas similares

* **Ocurrencias vs. [Instancias](instances.md)**: Las ocurrencias cuentan visitas individuales en las que se ha establecido o mantenido un valor de dimensión. Las instancias no incluyen visitas individuales en las que persiste un valor de dimensión.
* **Ocurrencias vs. [Vistas de página](page-views.md)**: Las ocurrencias incluyen todos los tipos de visitas, incluidas las llamadas de seguimiento de vista de página ([`t()`](/help/implement/vars/functions/t-method.md)), vincular llamadas de seguimiento ([`tl()`](/help/implement/vars/functions/tl-method.md)) y datos del resumen [Fuentes de datos](/help/import/data-sources/overview.md). La métrica vistas de página solo incluye llamadas de seguimiento de vista de página, excluidas las llamadas de seguimiento de vínculos y las fuentes de datos de resumen.

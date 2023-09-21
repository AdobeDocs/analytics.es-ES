---
title: Ocurrencias
description: Número de visitas configurado o en las que persiste una variable.
feature: Metrics
exl-id: 8428e813-0fb4-4620-884e-1aa92fe33209
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 64%

---

# Ocurrencias

Las &#39;Ocurrencias&#39; [métrica](overview.md) muestra el número de visitas configurado o en las que persiste una dimensión. Cuando arrastra una dimensión en Workspace a un lienzo en blanco, Adobe aplica automáticamente esta métrica al proyecto.

## Cálculo de esta métrica

De todas las visitas individuales de un grupo de informes, incluya las visitas en las que se define o persiste un valor de dimensión. Algunas dimensiones, como las [eVars](../dimensions/evar.md), persisten más allá de la visita en la que están configuradas. Esta métrica cuenta tanto los valores iniciales como los persistentes.

## Comparar con métricas similares

* **Ocurrencias vs. [Instancias](instances.md)**: Las ocurrencias cuentan visitas individuales en las que se ha establecido o mantenido un valor de dimensión. Las instancias no incluyen visitas individuales en las que persiste un valor de dimensión.
* **Ocurrencias vs. [Page views](page-views.md)**: las ocurrencias incluyen todos los tipos de visitas, incluidas las llamadas de seguimiento de vista de página ([`t()`](/help/implement/vars/functions/t-method.md)), llamadas de seguimiento de vínculos ([`tl()`](/help/implement/vars/functions/tl-method.md)) y datos de resumen [Fuentes de datos](/help/import/data-sources/overview.md). La métrica vistas de página solo incluye llamadas de seguimiento de vista de página, excluidas las llamadas de seguimiento de vínculos y las fuentes de datos de resumen.

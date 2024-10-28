---
title: Ocurrencias
description: Número de visitas configurado o en las que persiste una variable.
feature: Metrics
exl-id: 8428e813-0fb4-4620-884e-1aa92fe33209
source-git-commit: 0c5062363e10d9b545a3209ebaefcc6fa5d02c8b
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 57%

---

# Ocurrencias

La [métrica](overview.md) “Ocurrencias” muestra el número de visitas donde se ha establecido o ha permanecido una dimensión determinada. Cuando arrastra una dimensión en Workspace a un lienzo en blanco, Adobe aplica automáticamente esta métrica al proyecto.

## Cómo se calcula esta métrica

De todas las visitas individuales de un grupo de informes, incluya las visitas en las que se define o persiste un valor de dimensión. Algunas dimensiones, como las [eVars](../dimensions/evar.md), persisten más allá de la visita en la que están configuradas. Esta métrica cuenta tanto los valores iniciales como los persistentes.

## Comparar con métricas similares

* **Ocurrencias vs. [Instancias](instances.md)**: Las ocurrencias cuentan visitas individuales en las que se ha establecido o mantenido un valor de dimensión. Las instancias no incluyen visitas individuales en las que persiste un valor de dimensión.
* **Ocurrencias frente a [Vistas de página](page-views.md)**: las ocurrencias incluyen todos los tipos de visitas, incluidas las llamadas de seguimiento de vista de página ([`t()`](/help/implement/vars/functions/t-method.md)), las llamadas de seguimiento de vínculos ([`tl()`](/help/implement/vars/functions/tl-method.md)) y los datos de las [Fuentes de datos](/help/import/data-sources/overview.md) de resumen. La métrica de vistas de página solo incluye las llamadas de seguimiento de vistas de páginas, excluyendo las llamadas de seguimiento de vínculos y las fuentes de datos de resumen.

## Persistencia

La persistencia es la capacidad de un valor de dimensión determinado para relacionarse con una métrica más allá del evento en el que está establecido. Utiliza una combinación de asignación y caducidad. La asignación le permite determinar qué valor se conserva cuando más de un elemento de dimensión puede persistir a la vez en una sola columna. La caducidad le permite determinar cuánto tiempo persiste un elemento de dimensión más allá del evento en el que está establecido.

La persistencia solo está disponible en dimensiones y es retroactiva a los datos a los que se aplica. Se trata de una transformación inmediata de los datos que se produce antes de aplicar el filtrado u otras operaciones de análisis. Si la persistencia no está habilitada, la dimensión solo se relaciona con métricas que existen en el mismo evento.
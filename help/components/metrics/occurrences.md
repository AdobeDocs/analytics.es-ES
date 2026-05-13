---
title: Ocurrencias
description: Número de visitas configurado o en las que persiste una variable.
feature: Metrics
exl-id: 8428e813-0fb4-4620-884e-1aa92fe33209
TQID: https://experienceleague.adobe.com/04bDCj1dkVb9gIDMbpvvGea92oOzd-N0XLfzf4t-6iA
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 280
ht-degree: 66%

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
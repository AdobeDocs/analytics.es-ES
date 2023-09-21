---
title: Instancias
description: El número de visitas que se configuró una variable (y no persistió).
feature: Metrics
exl-id: 9d1a66b5-46f9-4834-87a1-5f63e386e61d
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 57%

---

# Instancias

Las &#39;Instancias&#39; [métrica](overview.md) muestra el número de veces que una dimensión se definió explícitamente en una solicitud de imagen. Algunas dimensiones, como las [eVars](../dimensions/evar.md) persisten los elementos de dimensión más allá de la visita en la que están establecidas. Esta métrica resulta útil cuando desea ver el número de veces que se estableció un elemento de dimensión sin las visitas individuales en las que dicho valor persistió.

## Cálculo de esta métrica

De todas las visitas individuales de un grupo de informes, solo incluye las visitas que establecen explícitamente un elemento de dimensión en la solicitud de imagen. Algunas dimensiones, como las [eVars](../dimensions/evar.md), persisten más allá de la visita en la que están configuradas. Las métricas como [Vistas de página](page-views.md) y [Ocurrencias](occurrences.md) cuentan tanto los valores iniciales como los persistentes. Esta métrica no cuenta los valores persistentes.

Por ejemplo, un visitante llega a su sitio y utiliza la búsqueda interna. Rastrea la búsqueda interna en eVar1. Después de usar la búsqueda interna una vez, visitan cinco páginas más antes de irse.

Si viera un informe en el espacio de trabajo, vería una instancia de eVar1 y seis repeticiones. La instancia única se activó en la página de resultados de búsqueda, mientras que las ocurrencias contaron el valor inicial así como los valores persistentes.

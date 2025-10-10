---
title: Instancias
description: El número de visitas que se configuró una variable (y no persistió).
feature: Metrics
exl-id: 9d1a66b5-46f9-4834-87a1-5f63e386e61d
source-git-commit: 813d209980ad02c412970a698c282c1358921ed6
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 50%

---

# Instancias

La métrica [Instancias](overview.md) muestra el número de veces que una dimensión se definió explícitamente en una solicitud de imagen. Algunas dimensiones, como las [eVars](../dimensions/evar.md) persisten los elementos de dimensión más allá de la visita en la que están establecidas. Esta métrica resulta útil cuando desea ver el número de veces que se estableció un elemento de dimensión sin las visitas individuales en las que dicho valor persistió.

## Cálculo de esta métrica

De todas las visitas individuales de un grupo de informes, solo incluye las visitas que establecen explícitamente un elemento de dimensión en la solicitud de imagen. Algunas dimensiones, como las [eVars](../dimensions/evar.md), persisten más allá de la visita en la que están configuradas. Las métricas como [Vistas de página](page-views.md) y [Ocurrencias](occurrences.md) cuentan tanto los valores iniciales como los persistentes. Esta métrica no cuenta los valores persistentes.

Por ejemplo, un visitante llega a su sitio y utiliza la búsqueda interna. La búsqueda interna se rastrea en eVar1. Después de usar la búsqueda interna una vez, visitan cinco páginas más antes de irse.

Si viera un informe en Workspace, vería una instancia de eVar1 y seis ocurrencias. Una instancia cuenta en la página de resultados de búsqueda, mientras que la métrica ocurrencias cuenta el valor inicial y los valores persistentes posteriores.

## Comparar con métricas similares

* **Instancias vs. [Ocurrencias](occurrences.md)**: Las instancias no incluyen visitas individuales en las que persiste un elemento de dimensión. Las ocurrencias cuentan visitas individuales en las que se ha establecido o mantenido un valor de dimensión.
* **Instancias vs. [Vistas de página](page-views.md)**: Las instancias incluyen todos los tipos de visitas, incluidas las llamadas de seguimiento de vista de página ([`t()`](/help/implement/vars/functions/t-method.md)), las llamadas de seguimiento de vínculos ([`tl()`](/help/implement/vars/functions/tl-method.md)) y los datos del resumen [Fuentes de datos](/help/import/data-sources/overview.md). La métrica de vistas de página solo incluye las llamadas de seguimiento de vistas de páginas, excluyendo las llamadas de seguimiento de vínculos y las fuentes de datos de resumen.

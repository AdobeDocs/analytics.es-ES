---
title: Profundidad promedio de la página
description: Cantidad promedio de páginas en las que existe la dimensión.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 0%

---


# Profundidad promedio de la página

La métrica &#39;Profundidad de página promedio&#39; muestra hasta dónde se encuentra el elemento de dimensión en una visita determinada. Por ejemplo: la página de inicio generalmente muestra una profundidad de página promedio menor que la página de confirmación de compra, que normalmente será mayor en una visita. Esta métrica es útil cuando desea comprender cuántas páginas de un elemento de dimensión determinado se sitúan en promedio. Puede utilizar esta información para optimizar determinadas páginas hacia visitantes nuevos si la página tiene una profundidad media baja.

>[SUGERENCIA] Utilice esta métrica junto con otra métrica (como [Visitas](visits.md)) para obtener mejores perspectivas. Si utiliza esta métrica por sí misma, obtendrá elementos de dimensión que contengan profundidades de página de anomalías, lo que generalmente no es valioso.

## Cómo se calcula esta métrica

La primera página de una visita tiene una profundidad de `0`página. La página siguiente tiene una profundidad de 1 y aumenta la vista de cada página hasta el final de la visita. Esta métrica solo aumenta con las llamadas de vista de página ([`t()`](/help/implement/vars/functions/t-method.md)) y no con las llamadas de seguimiento de vínculos ([`tl()`](/help/implement/vars/functions/tl-method.md)).

Para un elemento de dimensión determinado, agregue todas las profundidades de página para ese elemento de dimensión y dividalo por visitas. El número resultante es la profundidad de página promedio, redondeada al entero más cercano. Los elementos de dimensión con una profundidad de página promedio `0` significa que se encontraban con frecuencia en la primera página de la visita.

Por ejemplo: observe el siguiente ejemplo de visita:

```text
Page1 > Page2 > Page2 > Page3 > Page4 > Page2
```

Si se desea una profundidad de página promedio para el elemento de dimensión `Page2`, se calculará de la siguiente manera:

```text
If 'Count repeat instances' is enabled:
(1 + 2 + 5) / 3 = 2.67, rounded up to 3

If 'Count repeat instances' is disabled:
(1 + 4) / 2 = 2.5, rounded up to 3
```

>[!TIP]
>
>Si desea ver la profundidad de página promedio con un decimal, cree una métrica calculada usando esta métrica como el único elemento dentro de la fórmula. Aumente los lugares decimales en la métrica calculada hasta el decimal deseado.

## Porcentajes superiores al 100%

Esta métrica contiene con frecuencia porcentajes superiores al 100 %. El denominador es la profundidad de página media de toda la dimensión y el numerador es la profundidad de página media del elemento de dimensión. Si la profundidad de página media de toda la dimensión es inferior a la profundidad de página promedio de un elemento de dimensión determinado, verá porcentajes superiores al 100 %. Al ordenar los informes de clasificación por esta métrica, se muestran los valores de profundidad de página promedio de la anomalía, que generalmente no son valiosos. Adobe recomienda ordenar según otra métrica, como [Visitas](visits.md), en los informes de clasificación.
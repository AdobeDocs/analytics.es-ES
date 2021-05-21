---
title: Profundidad promedio de la página
description: Cantidad promedio de páginas en las que existe la dimensión.
exl-id: 6625405a-bda5-4723-8d22-4bc5b7e44d4e
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '369'
ht-degree: 100%

---

# Profundidad promedio de la página

La métrica “Profundidad promedio de la página” muestra hasta dónde alcanza el elemento de la dimensión en una visita determinada. Por ejemplo: la página de inicio generalmente muestra una profundidad de página promedio menor que la página de confirmación de compra, que normalmente tendrá mayor profundidad en una visita. Esta métrica es útil cuando desea comprender cuántas páginas de un elemento de dimensión determinado se sitúan dentro del promedio. Puede utilizar esta información para optimizar determinadas páginas hacia visitantes nuevos si la página tiene una profundidad promedio baja.

>[!TIP]
>
>Utilice esta métrica junto con otra métrica (como [Visitas](visits.md)) para obtener mejores datos. Si utiliza esta métrica de forma independiente, obtendrá elementos de dimensión que contengan profundidades de página anómalas, lo que generalmente no proporciona datos valiosos.

## Cálculo de esta métrica

La primera página de una visita tiene una profundidad de página de `0`. La página siguiente tiene una profundidad de 1 y aumenta la vista de cada página hasta el final de la visita. Esta métrica solo aumenta con las llamadas de vista de página ([`t()`](/help/implement/vars/functions/t-method.md)) y no con las llamadas de seguimiento de vínculos ([`tl()`](/help/implement/vars/functions/tl-method.md)).

Para un elemento de dimensión, agregue todas las profundidades de página para ese elemento de dimensión y divida el elemento por visitas. El número resultante es la profundidad de página promedio, redondeada al entero más cercano. Los elementos de dimensión con una profundidad de página promedio `0` significan que se encontraban con frecuencia en la primera página de la visita.

Veamos el siguiente ejemplo de visita:

```text
Page1 > Page2 > Page2 > Page3 > Page4 > Page2
```

Si se desea una profundidad de página promedio para el elemento de dimensión `Page2`, se debe calcular de la siguiente manera:

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

Esta métrica contiene con frecuencia porcentajes superiores al 100%. El denominador es la profundidad de página promedio de toda la dimensión y el numerador es la profundidad de página promedio del elemento de dimensión. Si la profundidad de página promedio de toda la dimensión es inferior a la profundidad de página promedio de un elemento de dimensión determinado, verá porcentajes superiores al 100%. Al ordenar los informes de clasificación por esta métrica, se muestran los valores de profundidad de página promedio de la anomalía, que generalmente no son muy útiles. Adobe recomienda ordenar según otra métrica, como [Visitas](visits.md), en los informes de clasificación.

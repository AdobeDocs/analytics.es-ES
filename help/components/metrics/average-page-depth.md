---
title: Profundidad promedio de la página
description: Cantidad promedio de páginas en las que existe la dimensión.
feature: Metrics
exl-id: 6625405a-bda5-4723-8d22-4bc5b7e44d4e
TQID: https://experienceleague.adobe.com/Pm2WxRPqn9M-7IdrFQ2Tkj9t-L8ug3nZGr6ncpZg7lg
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 365
ht-degree: 55%

---

# Profundidad promedio de la página

La &quot;Profundidad promedio de la página&quot; [métrica](overview.md) muestra hasta qué punto se extiende un elemento de dimensión en una visita determinada, en promedio. Por ejemplo: la página de inicio (que es un elemento de dimensión para la dimensión Página ) generalmente muestra una profundidad de página promedio menor que la página de confirmación de compra, que probablemente se extiende más allá de una visita. Puede utilizar esta información para optimizar determinadas páginas hacia visitantes nuevos si la página tiene una profundidad promedio baja.

>[!TIP]
>
>Utilice esta métrica junto con otra métrica, como [Visitas](visits.md), para obtener mejores datos. Si utiliza esta métrica de forma independiente, podría obtener elementos de dimensión que contengan profundidades de página anómalas, lo que generalmente no es un insight valioso.

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

Esta métrica contiene con frecuencia porcentajes superiores al 100%. El denominador es la profundidad de página promedio de toda la dimensión y el numerador es la profundidad de página promedio del elemento de dimensión.

Si la profundidad de página promedio de toda la dimensión es menor que la profundidad de página promedio de un elemento de dimensión determinado, verá porcentajes superiores al 100%. Al ordenar los informes de clasificación por esta métrica, se muestran los valores de profundidad de página promedio de la anomalía, que generalmente no son muy útiles. Adobe recomienda ordenar según otra métrica, como [Visitas](visits.md), en los informes de clasificación.

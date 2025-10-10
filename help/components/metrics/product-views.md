---
title: Vistas del producto
description: Número de vistas a páginas de producto.
feature: Metrics
exl-id: 6217391d-8b42-4fdf-b05e-b9b117598ad2
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 72%

---

# Vistas del producto

La [métrica](overview.md) &quot;Vistas del producto&quot; muestra la cantidad de veces que se vio un producto. Esta métrica es útil cuando desea ver los productos más vistos o ver la tendencia de las vistas totales de productos con el paso del tiempo.

## Cálculo de esta métrica

Esta métrica cuenta el número de visitas que coinciden con **cualquiera** de las siguientes:

* El valor `prodView` existe en la variable [`events`](/help/implement/vars/page-vars/events/events-overview.md); o
* La variable [`products`](/help/implement/vars/page-vars/products.md) está establecida y la variable `events` está vacía.

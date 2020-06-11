---
title: vistas del producto
description: Número de vistas a páginas de productos.
translation-type: tm+mt
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: tm+mt
source-wordcount: '94'
ht-degree: 0%

---


# vistas del producto

La métrica &#39;vistas de producto muestra el número de veces que se vio un producto. Esta métrica es útil cuando desea ver los productos más vistos o ver la tendencia de las vistas totales de productos con el paso del tiempo.

## Cómo se calcula esta métrica

Esta métrica cuenta el número de visitas que coinciden con **cualquiera** de las siguientes:

* El valor `prodView` existe en la [`events`](/help/implement/vars/page-vars/events/events-overview.md) variable; o
* La [`products`](/help/implement/vars/page-vars/products.md) variable está configurada y no existen eventos del carro de compras en la `events` variable. Cualquier evento que no es personalizado (`event1` - `event1000`) es un evento del carro de compras.
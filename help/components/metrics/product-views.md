---
title: Vistas del producto
description: Número de vistas a páginas de productos.
exl-id: 6217391d-8b42-4fdf-b05e-b9b117598ad2
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '94'
ht-degree: 100%

---

# Vistas del producto

La métrica “Vistas de producto” muestra el número de veces que se vio un producto. Esta métrica es útil cuando desea ver los productos más vistos o ver la tendencia de las vistas totales de productos con el paso del tiempo.

## Cálculo de esta métrica

Esta métrica cuenta el número de visitas que coinciden con **cualquiera** de las siguientes:

* El valor `prodView` existe en la variable [`events`](/help/implement/vars/page-vars/events/events-overview.md); o
* la variable [`products`](/help/implement/vars/page-vars/products.md) está configurada y no existen eventos del carro de compras en la variable `events`. Cualquier evento que no es personalizado (`event1` - `event1000`) es un evento del carro de compras.

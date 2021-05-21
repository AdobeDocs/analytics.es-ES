---
title: Carros de compras
description: Número de visitas en las que un visitante agregó su primer producto al carro de compras.
exl-id: 890bbaba-0140-4995-bbd2-c69aedc801e5
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '157'
ht-degree: 100%

---

# Carros de compras

La métrica “Eliminaciones del carro de compras” muestra la cantidad de veces que un visitante ha eliminado algo de su carro de compras. Esta métrica es útil cuando desea comprender la parte del canal de conversión en la que los clientes ya no están interesados en un producto.

## Cálculo de esta métrica

Esta métrica cuenta el número de visitas donde `scOpen` existe en la variable [`events`](/help/implement/vars/page-vars/events/events-overview.md).

## Diferencia entre “Carros de compras” y “Vistas de carros de compras”

Dado que “Carros de compras” y “Vistas del carro de compras” son eventos que requieren implementación, su organización decide la diferencia exacta entre estas dos métricas. Sin embargo, Adobe ha diseñado estas métricas para lo siguiente:

* “Carros de compras” solo se activa una vez por compra cuando un visitante agrega su primer producto al carro de compras.
* Los activadores de “Adiciones al carro de compras” para cada producto agregado al carro de compras.

Para el primer producto, se activan tanto “Carros de compras” como “Adiciones al carro de compras”. Una vez más, estas directrices no son concretas; su organización determina la lógica de implementación exacta.

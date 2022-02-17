---
title: Carros de compras
description: Número de visitas en las que un visitante agregó su primer producto al carro de compras.
feature: Metrics
exl-id: 890bbaba-0140-4995-bbd2-c69aedc801e5
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 100%

---

# Carros de compras

La métrica Carros de compras muestra el número de visitas en las que un visitante agregó su primer producto al carro de compras.

## Cálculo de esta métrica

Esta métrica cuenta el número de visitas donde `scOpen` existe en la variable [`events`](/help/implement/vars/page-vars/events/events-overview.md).

## Diferencia entre “Carros de compras” y “Vistas de carros de compras”

Dado que “Carros de compras” y “Vistas del carro de compras” son eventos que requieren implementación, su organización decide la diferencia exacta entre estas dos métricas. Sin embargo, Adobe ha diseñado estas métricas para lo siguiente:

* “Carros de compras” solo se activa una vez por compra cuando un visitante agrega su primer producto al carro de compras.
* Los activadores de “Adiciones al carro de compras” para cada producto agregado al carro de compras.

Para el primer producto, se activan tanto “Carros de compras” como “Adiciones al carro de compras”. Una vez más, estas directrices no son concretas; su organización determina la lógica de implementación exacta.

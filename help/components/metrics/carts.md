---
title: Carros de compras
description: Número de visitas en las que un visitante agregó su primer producto al carro de compras.
feature: Metrics
exl-id: 890bbaba-0140-4995-bbd2-c69aedc801e5
source-git-commit: 932a6c1452d4710b11c1ce5551c845ef6721f137
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 56%

---

# Carros de compras

La métrica Carros de compras muestra el número de visitas en las que un visitante agregó su primer producto al carro de compras.

## Cálculo de esta métrica

Esta métrica cuenta el número de visitas donde `scOpen` existe en la variable [`events`](/help/implement/vars/page-vars/events/events-overview.md).

## Diferencia entre &quot;Carros de compras&quot;, &quot;Vistas del carro de compras&quot; y &quot;Adiciones al carro de compras&quot;

Dado que &quot;Carros de compras&quot;, &quot;Vistas del carro de compras&quot; y &quot;Adiciones al carro de compras&quot; son eventos que requieren implementación, su organización decide la diferencia exacta entre estas métricas. Sin embargo, Adobe diseñó estas métricas para la siguiente lógica:

* “Carros de compras” solo se activa una vez por compra cuando un visitante agrega su primer producto al carro de compras.
* déclencheur de &quot;Vistas del carro de compras&quot; cada vez que un visitante ve su carro de compras.
* Los activadores de “Adiciones al carro de compras” para cada producto agregado al carro de compras.

Cuando un cliente agrega su primer producto a un carro de compras, el comportamiento deseado es que tanto el déclencheur &quot;Carros de compras&quot; como el de &quot;Adiciones al carro de compras&quot;. Una vez más, estas directrices no son concretas; su organización determina la lógica de implementación exacta.

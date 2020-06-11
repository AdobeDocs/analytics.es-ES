---
title: Carros de compras
description: Número de visitas en las que un visitante agregó su primer producto al carro de compras.
translation-type: tm+mt
source-git-commit: 554ced510600a4d5866e89806b058b5d2d9a3edf
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 1%

---


# Carros de compras

La métrica &quot;Eliminaciones del carro de compras&quot; muestra la cantidad de veces que un visitante ha eliminado algo de su carro de compras. Esta métrica es útil cuando desea comprender la parte del canal de conversión en la que los clientes ya no están interesados en un producto.

## Cómo se calcula esta métrica

Esta métrica cuenta el número de visitas donde `scOpen` existe en la [`events`](/help/implement/vars/page-vars/events/events-overview.md) variable.

## Diferencia entre &#39;Carros de compras&#39; y &#39;vistas de carros de compras&#39;

Dado que &#39;Carros de compras&#39; y &#39;vistas del carro de compras&#39; son eventos que requieren implementación, su organización decide la diferencia exacta entre estas dos métricas. Sin embargo, Adobe ha diseñado estas métricas para lo siguiente:

* Los &#39;Carros de compras&#39; solo se activan una vez por compra cuando un visitante agrega su primer producto al carro de compras.
* Los activadores de &#39;Adiciones al carro de compras&#39; para cada producto agregado al carro de compras.

Para el primer producto, se activan tanto &#39;Carros de compras&#39; como &#39;Adiciones al carro de compras&#39;. Una vez más, estas directrices no son concretas; su organización determina la lógica de implementación exacta.

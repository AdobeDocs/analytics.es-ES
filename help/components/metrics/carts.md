---
title: Carros de compras
description: Número de visitas en las que un visitante agregó su primer producto al carro de compras.
feature: Metrics
exl-id: 890bbaba-0140-4995-bbd2-c69aedc801e5
TQID: https://experienceleague.adobe.com/a-qT5Ly8-4mSBGbGTAzbwLIMRFZtqotMPvGFgOrM41Y
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f1f1a2d4-0976-4881-b091-c2bb8de7ffacid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 162
ht-degree: 45%

---

# Carros de compras

La métrica [Carros de compras](overview.md) muestra el número de visitas en las que un visitante agregó su primer producto al carro de compras.

## Cálculo de esta métrica

Esta métrica cuenta el número de visitas donde `scOpen` existe en la variable [`events`](/help/implement/vars/page-vars/events/events-overview.md).

## Diferencia entre &quot;Carros de compras&quot;, &quot;Vistas del carro de compras&quot; y &quot;Adiciones al carro de compras&quot;

Dado que &quot;Carros de compras&quot;, &quot;Vistas del carro de compras&quot; y &quot;Adiciones al carro de compras&quot; son eventos que requieren implementación, su organización decide la diferencia exacta entre estas métricas. Sin embargo, Adobe diseñó estas métricas para la siguiente lógica:

* “Carros de compras” solo se activa una vez por compra cuando un visitante agrega su primer producto al carro de compras.
* Los déclencheur &quot;Vistas del carro de compras&quot; aparecen cada vez que un visitante ve su carro de compras.
* Los activadores de “Adiciones al carro de compras” para cada producto agregado al carro de compras.

Cuando un cliente agrega su primer producto a un carro de compras, el comportamiento deseado es que tanto &quot;Carros de compras&quot; como &quot;Adiciones al carro de compras&quot; generen déclencheur. Una vez más, estas directrices no son concretas; su organización determina la lógica de implementación exacta.

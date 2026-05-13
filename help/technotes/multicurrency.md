---
description: Describe cómo definir códigos de moneda de destino para que funcione la compatibilidad con múltiples monedas.
title: Compatibilidad con múltiples monedas
feature: Analytics Basics
exl-id: b67f459c-0636-4eac-af52-51846bb583b5
TQID: https://experienceleague.adobe.com/-t0JAIvbmUmzTCTznOWcjVmvtJbmQNV5MIrbQBvhv6M
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: a421fb65-2c82-457a-921c-28c46b697a39id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 127
ht-degree: 18%

---

# Compatibilidad con múltiples monedas

Adobe ofrece varios niveles de conversión de moneda para que su organización pueda lograr la moneda deseada en muchos informes. La conversión se produce en tres niveles:

## Nivel de página

Puede usar la variable [`currencyCode`](/help/implement/vars/config-vars/currencycode.md) para establecer la moneda deseada en cada página. Si la moneda de la página no coincide con la del grupo de informes de destino, Adobe realiza una conversión de moneda a la del grupo de informes en función del tipo de cambio del día actual. Se registra la moneda convertida.

## Nivel del grupo de informes

Cada grupo de informes tiene una **moneda base**. Esta moneda dicta el contexto de todas las métricas de moneda (como [Ingresos](/help/components/metrics/revenue.md)). Todos los datos de moneda almacenados están en la moneda base del grupo de informes.


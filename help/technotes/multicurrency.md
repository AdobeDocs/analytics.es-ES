---
description: Describe cómo definir códigos de moneda de destino para que funcione la compatibilidad con múltiples monedas.
title: Compatibilidad con múltiples monedas
feature: Analytics Basics
exl-id: b67f459c-0636-4eac-af52-51846bb583b5
source-git-commit: 99156dd9d898ce0abf214561cb0040c647d7e6ab
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 16%

---

# Compatibilidad con múltiples monedas

Adobe ofrece varios niveles de conversión de moneda para que su organización pueda lograr la moneda deseada en muchos informes. La conversión se produce en tres niveles:

## Nivel de página

Puede usar la variable [`currencyCode`](/help/implement/vars/config-vars/currencycode.md) para establecer la moneda deseada en cada página. Si la moneda de la página no coincide con la del grupo de informes de destino, Adobe realiza una conversión de moneda a la del grupo de informes en función del tipo de cambio del día actual. Se registra la moneda convertida.

## Nivel del grupo de informes

Cada grupo de informes tiene una **moneda base**. Esta moneda dicta el contexto de todas las métricas de moneda (como [Ingresos](/help/components/metrics/revenue.md)). Todos los datos de moneda almacenados están en la moneda base del grupo de informes.


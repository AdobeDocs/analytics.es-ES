---
description: Describe cómo definir códigos de moneda de destino para que funcione la compatibilidad con múltiples monedas.
title: Compatibilidad con múltiples monedas
feature: Analytics Basics
exl-id: b67f459c-0636-4eac-af52-51846bb583b5
source-git-commit: f659d1bde361550928528c7f2a70531e3ac88047
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 10%

---

# Compatibilidad con múltiples monedas

Adobe ofrece varios niveles de conversión de divisas para que su organización pueda conseguir la divisa deseada en muchos informes. La conversión se produce en tres niveles:

## Nivel de página

Puede usar el complemento [`currencyCode`](/help/implement/vars/config-vars/currencycode.md) para establecer la moneda deseada en cada página. Si la divisa de la página no coincide con la del grupo de informes de destino, Adobe realiza una conversión a la divisa del grupo de informes en función del tipo de cambio del día actual. Se registra la moneda convertida.

## Nivel del grupo de informes

Cada grupo de informes tiene un **divisa base**. Esta moneda dicta el contexto de todas las métricas de moneda (como [Ingresos](/help/components/metrics/revenue.md)). Todos los datos de moneda almacenados están en la moneda base del grupo de informes.

## Nivel de usuario

En Reports &amp; Analytics, los usuarios pueden establecer una moneda diferente a la moneda base del grupo de informes en [Configuración de informes](/help/analyze/reports-analytics/report-settings.md). Esta configuración no es destructiva, lo que significa que no altera los datos subyacentes. En su lugar, aplica la conversión de moneda básica a todos los informes vistos en función del tipo de cambio actual. Si ve el mismo informe en diferentes días, los números pueden cambiar debido a diferentes tasas de cambio diarias.

Analysis Workspace no ofrece actualmente la conversión de divisas a nivel de usuario.

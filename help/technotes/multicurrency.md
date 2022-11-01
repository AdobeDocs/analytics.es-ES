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

Adobe ofrece varios niveles de conversión de divisas para que su organización pueda alcanzar la moneda deseada en muchos informes. La conversión sucede en tres niveles:

## Nivel de página

Puede usar la variable [`currencyCode`](/help/implement/vars/config-vars/currencycode.md) para configurar la moneda que desee en cada página. Si la moneda de la página no coincide con la moneda del grupo de informes de destino, el Adobe realiza una conversión de moneda a la moneda del grupo de informes en función del tipo de cambio del día actual. Se registra la moneda convertida.

## Nivel del grupo de informes

Cada grupo de informes tiene un **moneda base**. Esta moneda dicta el contexto de todas las métricas de moneda (como [Ingresos](/help/components/metrics/revenue.md)). Todos los datos de moneda almacenados se encuentran en la moneda base del grupo de informes.

## Nivel de usuario

Para Reports &amp; Analytics, los usuarios pueden establecer una moneda diferente a la moneda base del grupo de informes en [Configuración de informes](/help/analyze/reports-analytics/report-settings.md). Esta configuración no es destructiva, lo que significa que no altera los datos subyacentes. En su lugar, aplica la conversión de moneda básica a todos los informes vistos según el tipo de cambio actual. Si ve el mismo informe en días diferentes, los números pueden cambiar debido a tipos de cambio diarios diferentes.

Actualmente, Analysis Workspace no ofrece conversión de moneda a nivel de usuario.

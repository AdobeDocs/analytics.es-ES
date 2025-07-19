---
title: Recargas
description: El número de veces que se recargó la página.
feature: Metrics
exl-id: 9539a733-9e9f-48b3-b8ab-8d969de27f87
source-git-commit: c9b7c32adfb44a04ab792d12ca049106b3009710
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 21%

---

# Recargas

La [métrica](overview.md) &quot;Recargas&quot; muestra el número de veces que un elemento de dimensión estuvo presente durante una recarga. La forma más común de activar una recarga es a través de un visitante que actualiza su explorador.

## Cálculo de esta métrica

Esta métrica cuenta el número de visitas en las que la dimensión [Página](../dimensions/page.md) contiene el mismo valor que la visita anterior.

El concepto de recarga se aplica a la dimensión Página independientemente de la dimensión que utilice en la creación de informes. Por ejemplo, si usa [eVar1](../dimensions/evar.md) como dimensión y Recargas como métrica, la tabla muestra el número de veces que cada valor de eVar estuvo presente durante una recarga (dos valores de página consecutivos). No muestra el número de veces que estaban presentes dos valores eVar1 consecutivos.

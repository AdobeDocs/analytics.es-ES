---
title: Recargas
description: El número de veces que se recargó la página.
feature: Metrics
exl-id: 9539a733-9e9f-48b3-b8ab-8d969de27f87
TQID: https://experienceleague.adobe.com/Jhm8-usZH-SLOzUvNIC3hdoKDMkm9T5mnCUeeMRga7E
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 132
ht-degree: 21%

---

# Recargas

La [métrica](overview.md) &quot;Recargas&quot; muestra el número de veces que un elemento de dimensión estuvo presente durante una recarga. La forma más común de activar una recarga es a través de un visitante que actualiza su explorador.

## Cálculo de esta métrica

Esta métrica cuenta el número de visitas en las que la dimensión [Página](../dimensions/page.md) contiene el mismo valor que la visita anterior.

El concepto de recarga se aplica a la dimensión Página independientemente de la dimensión que utilice en la creación de informes. Por ejemplo, si usa [eVar1](../dimensions/evar.md) como dimensión y Recargas como métrica, la tabla muestra el número de veces que cada valor de eVar estuvo presente durante una recarga (dos valores de página consecutivos). No muestra el número de veces que estaban presentes dos valores eVar1 consecutivos.

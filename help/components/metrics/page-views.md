---
title: Vistas de páginas
description: El número de veces que un elemento de dimensión se ha establecido o persistido en Adobe Analytics.
feature: Metrics
exl-id: 6b4fb7af-03e2-49e8-a431-f7746c89a626
TQID: https://experienceleague.adobe.com/ZJOoxc3imuMfVTa7caV5eQ6-XJh0amCRq65ByuANFq0
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f1f1a2d4-0976-4881-b091-c2bb8de7ffacid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 169
ht-degree: 100%

---

# Vistas de páginas

La [métrica](overview.md) **[!UICONTROL Vistas de página]** muestra el número de veces que un elemento de dimensión determinado se estableció o persistió en una página. Es una de las métricas más comunes y básicas de los informes.

## Cálculo de esta métrica

Esta métrica cuenta todas las llamadas de seguimiento de vista de página ([`t()`](/help/implement/vars/functions/t-method.md)) en un grupo de informes. Para las dimensiones, incluye visitas en las que se define o persiste un elemento de dimensión. No incluye llamadas de seguimiento de vínculos ([`tl()`](/help/implement/vars/functions/tl-method.md)) o datos de [fuentes de datos](/help/import/data-sources/overview.md).

## Comparar con métricas similares

* **Vistas de página frente a [Visitas](visits.md)**: Vistas de página cuenta la cantidad de veces que se ve una página. Visitas cuenta el número de sesiones de los visitantes. Una visita consiste en una o más vistas.
* **Vistas de página frente a [Eventos de página](page-events.md)**: Vistas de página cuenta el número de llamadas de seguimiento de vista de página (`t()`) y excluye las llamadas de seguimiento de vínculos (`tl()`). Los eventos de página son lo contrario; cuentan el número de llamadas de seguimiento de vínculos y excluyen las llamadas de seguimiento de vista de página.

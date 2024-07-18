---
title: Días transcurridos desde la última visita
description: Número de días entre la visita actual y la última vez que la visitaron.
feature: Dimensions
exl-id: 8063bdc6-516a-4dd0-a4ca-ded739e8d406
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '167'
ht-degree: 83%

---

# Días transcurridos desde la última visita

La dimensión &quot;Días transcurridos desde la última visita&quot; [dimension](overview.md) mide la cantidad de tiempo transcurrido entre la visita actual del visitante y su visita anterior (si es que la hay). Esta dimensión ayuda a comprender el comportamiento de los visitantes tras visitar el sitio. Algunos ejemplos son:

* ¿Con qué frecuencia regresan los usuarios al sitio?
* ¿Cómo se correlaciona la frecuencia de retorno con la conversión? ¿Los compradores habituales realizan visitas frecuentemente o con poca frecuencia?
* ¿Los usuarios que hacen clic en las campañas regresan frecuentemente?

Los usuarios noveles no se incluyen en esta dimensión.

## Rellene esta dimensión con datos

Esta dimensión funciona de forma predeterminada para todas las implementaciones. Si un grupo de informes contiene datos, esta dimensión funciona.

## Elementos de dimensión

Los elementos de dimensión incluyen el número de días entre la última visita de un visitante y la visita actual. Cada número de días es un elemento de dimensión independiente, con `"Same day"` que se produce cuando la última visita de un visitante y la visita actual se produjeron el mismo día.

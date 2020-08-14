---
title: Días transcurridos desde la última visita
description: Número de días entre la visita actual y la última vez que la visitaron.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '167'
ht-degree: 74%

---


# Días transcurridos desde la última visita

La dimensión “Días transcurridos desde la última visita” mide la cantidad de tiempo transcurrido entre la visita actual del visitante y su visita anterior (si existe). Esta dimensión ayuda a comprender el comportamiento de los visitantes tras visitar el sitio. Algunos ejemplos son:

* ¿Con qué frecuencia regresan los usuarios al sitio?
* ¿Cómo se correlaciona la frecuencia de retorno con la conversión? ¿Los compradores habituales realizan visitas frecuentemente o con poca frecuencia?
* ¿Los usuarios que hacen clic en las campañas regresan frecuentemente?

Los usuarios noveles no se incluyen en esta dimensión.

## Rellene esta dimensión con datos

Esta dimensión funciona de forma predeterminada para todas las implementaciones. Si un grupo de informes contiene datos, esta dimensión funciona.

## Elementos de Dimension

Los elementos de Dimension incluyen el número de días entre la última visita de un visitante y la visita actual. Each number of days is a separate dimension item, with `"Same day"` occurring where a visitor&#39;s last visit and the current hit happened on the same day.

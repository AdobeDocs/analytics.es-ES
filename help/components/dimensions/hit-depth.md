---
title: Profundidad de la visita
description: Número de visitas individuales en la visita.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 75%

---


# Profundidad de la visita

La dimensión “Profundidad de la visita” indica hasta dónde llega una visita determinada. Esta dimensión es valiosa para comprender hasta qué punto los visitantes realizan acciones en el sitio durante una visita. La profundidad de visitas cuenta todos los tipos de visitas, incluidas las vistas de página ([`t()`](/help/implement/vars/functions/t-method.md)) y las visitas de seguimiento de vínculos ([`tl()`](/help/implement/vars/functions/tl-method.md)).

## Rellene esta dimensión con datos

Esta dimensión funciona de forma predeterminada para todas las implementaciones. Si un grupo de informes contiene datos, esta dimensión funciona.

## Elementos de Dimension

Dimension items include the string `"Hit Depth"` followed by a number representing the number of hits into the visit. The dimension item of `"Hit Depth 1"` represents the first hit of the visit, while the dimension item `"Hit Depth 8"` represents the 8th hit of the visit.

## Comparación con la profundidad de la visita

La profundidad de la visita individual cuenta todos los tipos de visitas individuales, incluso vistas de página y las visitas de seguimiento de vínculos. Visit depth only increments for page view hits, _and_ the [Page](page.md) dimension item is not the same as the value on the previous page. La profundidad de la visita también es una dimensión basada en visitas, lo que significa que es el mismo valor para todas las visitas individuales de la visita. La siguiente tabla describe una visita de ejemplo y cómo considera la profundidad de la visita individual + la profundidad de la visita:

| Secuencia de páginas | Profundidad de la visita | ¿Cuenta la profundidad de la visita? | Profundidad de la visita |
| --- | --- | --- | --- |
| Página de inicio | 1 | Sí | 4 |
| Página de producto | 2 | Sí | 4 |
| Página de inicio | 3 | Sí | 4 |
| Clic en vínculo personalizado | 4 | No (vínculo personalizado) | 4 |
| Clic en vínculo personalizado | 5 | No (vínculo personalizado) | 4 |
| Página de producto | 6 | Sí | 4 |
| Clic en vínculo personalizado | 7 | No (vínculo personalizado) | 4 |
| Página de producto | 8 | No (igual que la página anterior) | 4 |

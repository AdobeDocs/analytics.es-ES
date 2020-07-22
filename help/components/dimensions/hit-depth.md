---
title: Profundidad de acierto
description: Número de visitas en la visita.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 7%

---


# Profundidad de acierto

La dimensión &#39;Profundidad de acierto&#39; informa hasta dónde llega una visita determinada. Esta dimensión es valiosa para comprender hasta qué punto en una visita los visitantes realizan acciones en el sitio. La profundidad de acierto cuenta todos los tipos de visitas, incluidas las vistas de página ([`t()`](/help/implement/vars/functions/t-method.md)) y las visitas individuales de seguimiento de vínculos ([`tl()`](/help/implement/vars/functions/tl-method.md)).

## Rellenar esta dimensión con datos

Esta dimensión funciona de forma predeterminada para todas las implementaciones. Si un grupo de informes contiene datos, esta dimensión funciona.

## Elementos de dimensión

Los elementos de dimensión incluyen la cadena `"Hit Depth"` seguida de un número que representa el número de visitas en la visita. El elemento de dimensión de `"Hit Depth 1"` representa la primera visita individual de la visita, mientras que el elemento de dimensión `"Hit Depth 8"` representa la octava visita individual de la visita.

## Comparación con la profundidad de la visita

La profundidad de la visita individual cuenta todos los tipos de visitas individuales, incluso las visitas de seguimiento de vista de página y vínculos. La profundidad de la visita solo aumenta para las visitas individuales de vista de página _y,_ el elemento de dimensión [Página](page.md) no es el mismo que el valor de la página anterior. La profundidad de la visita también es una dimensión basada en visitas, lo que significa que es el mismo valor para todas las visitas individuales de la visita. La siguiente tabla describe una visita de ejemplo y cómo considera la profundidad de la visita individual + la profundidad de la visita:

| Secuencia de páginas | Profundidad de acierto | ¿Cuenta la profundidad de la visita? | Profundidad de la visita |
| --- | --- | --- | --- |
| Página de inicio | 1 | Sí | 4 |
| Página de productos | 2 | Sí | 4 |
| Página de inicio | 3 | Sí | 4 |
| Clic en vínculo personalizado | 4 | No (vínculo personalizado) | 4 |
| Clic en vínculo personalizado | 5 | No (vínculo personalizado) | 4 |
| Página de productos | 6 | Sí | 4 |
| Clic en vínculo personalizado | 7 | No (vínculo personalizado) | 4 |
| Página de productos | 8 | No (igual que la página anterior) | 4 |

---
title: Profundidad de la visita
description: Número de visitas individuales en la visita.
exl-id: 84c27e3f-4228-4455-95bf-0239928337b5
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '261'
ht-degree: 100%

---

# Profundidad de la visita

La dimensión “Profundidad de la visita” indica hasta dónde llega una visita determinada. Esta dimensión es valiosa para comprender hasta qué punto los visitantes realizan acciones en el sitio durante una visita. La profundidad de visitas cuenta todos los tipos de visitas, incluidas las vistas de página ([`t()`](/help/implement/vars/functions/t-method.md)) y las visitas de seguimiento de vínculos ([`tl()`](/help/implement/vars/functions/tl-method.md)).

## Rellene esta dimensión con datos

Esta dimensión funciona de forma predeterminada para todas las implementaciones. Si un grupo de informes contiene datos, esta dimensión funciona.

## Elementos de dimensión

Los elementos de dimensión incluyen la cadena `"Hit Depth"` seguida de un número que representa el número de visitas individuales en la visita. El elemento de dimensión `"Hit Depth 1"` representa la primera visita individual de la visita, mientras que el elemento de dimensión `"Hit Depth 8"` representa la octava visita individual de la visita.

## Comparación con la profundidad de la visita

La profundidad de la visita individual cuenta todos los tipos de visitas individuales, incluso vistas de página y las visitas de seguimiento de vínculos. La profundidad de la visita solo aumenta para las visitas individuales de vista de página _y_ el elemento de la dimensión [Página](page.md) no es el mismo que el valor de la página anterior. La profundidad de la visita también es una dimensión basada en visitas, lo que significa que es el mismo valor para todas las visitas individuales de la visita. La siguiente tabla describe una visita de ejemplo y cómo considera la profundidad de la visita individual + la profundidad de la visita:

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

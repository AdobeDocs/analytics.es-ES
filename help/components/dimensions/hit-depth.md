---
title: Profundidad de la visita
description: Número de visitas individuales en la visita.
feature: Dimensions
exl-id: 84c27e3f-4228-4455-95bf-0239928337b5
TQID: https://experienceleague.adobe.com/dH1ItdXZTw9vcqvej3VOQDM-J9FFA38f4bq8HTJbKMo
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 262
ht-degree: 94%

---

# Profundidad de la visita

La &quot;Profundidad de la visita&quot; [dimension](overview.md) indica hasta dónde llega una visita determinada. Esta dimensión es valiosa para comprender hasta qué punto los visitantes realizan acciones en el sitio durante una visita. La profundidad de visitas cuenta todos los tipos de visitas, incluidas las vistas de página ([`t()`](/help/implement/vars/functions/t-method.md)) y las visitas de seguimiento de vínculos ([`tl()`](/help/implement/vars/functions/tl-method.md)).

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

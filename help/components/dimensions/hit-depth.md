---
title: Profundidad de la visita
description: Número de hits en la visita.
feature: Dimensions
exl-id: 84c27e3f-4228-4455-95bf-0239928337b5
TQID: https://experienceleague.adobe.com/dH1ItdXZTw9vcqvej3VOQDM-J9FFA38f4bq8HTJbKMo
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
    internal-label: Functions
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 63%
---
# Profundidad de la visita

La &quot;Profundidad de la visita&quot; [dimension](overview.md) indica hasta dónde llega una visita determinada. Esta dimensión es valiosa para comprender hasta qué punto los visitantes realizan acciones en el sitio durante una visita. La profundidad de visitas cuenta todos los tipos de visitas, incluidas las vistas de página ([`t()`](/help/implement/vars/functions/t-method.md)) y las visitas de seguimiento de vínculos ([`tl()`](/help/implement/vars/functions/tl-method.md)).

## Rellene esta dimensión con datos

Adobe calcula esta dimensión del lado del servidor a partir de la secuencia de visitas individuales en cada visita. No hay ninguna variable que establecer; funciona de forma predeterminada para todas las implementaciones.

| Propiedad | Valor |
| --- | --- |
| **variable de AppMeasurement** | Ninguno (calculado por Adobe) |
| **Campo Web SDK / XDM** | Ninguno (calculado por Adobe) |
| **Parámetro de consulta** | n/a |
| **etiqueta XML** | n/a |
| **Límite de bytes** | n/a |
| **Persistencia** | N/A |

## Elementos de dimensión

Los elementos de dimensión incluyen la cadena `"Hit Depth"` seguida de un número que representa el número de hits en la visita. El elemento de dimensión `"Hit Depth 1"` representa el primer hit de la visita, mientras que el elemento de dimensión `"Hit Depth 8"` representa el octavo hit de la visita.

>[!NOTE]
>
>Adobe Analytics registra marcas de hora con una precisión de solo segundo nivel. En el caso de las visitas que comparten la misma marca de tiempo por segundo, Adobe no puede garantizar que el orden reflejado en los informes sea el mismo que el orden en el que se produjeron las visitas. Si la precisión de milisegundos es una prioridad para su organización, considere la posibilidad de utilizar Customer Journey Analytics.

## Comparación con la profundidad de la visita

La profundidad del hit cuenta todos los tipos de hits, incluso vistas de página y los hits de seguimiento de vínculos. La profundidad de la visita solo aumenta para los hits de vista de página _y_ el elemento de la dimensión [Página](page.md) no es el mismo que el valor de la página anterior. La profundidad de la visita también es una dimensión basada en visitas, lo que significa que es el mismo valor para todos los hits de la visita. La siguiente tabla describe una visita de ejemplo y cómo considera la profundidad del hit + la profundidad de la visita:

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

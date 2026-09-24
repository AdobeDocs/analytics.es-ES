---
title: Días transcurridos desde la última visita
description: Número de días entre el hit actual y la última vez que hizo una visita.
feature: Dimensions
exl-id: 8063bdc6-516a-4dd0-a4ca-ded739e8d406
TQID: https://experienceleague.adobe.com/VOkdvehFSgp1xBEq49W5FIphzHi8ZCbrsoMnI7rgQMs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
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
source-wordcount: '206'
ht-degree: 64%
---
# Días transcurridos desde la última visita

La dimensión &quot;Días transcurridos desde la última visita&quot; [dimension](overview.md) mide la cantidad de tiempo transcurrido entre la visita actual del visitante y su visita anterior (si es que la hay). Esta dimensión ayuda a comprender el comportamiento de los visitantes tras visitar el sitio. Algunos ejemplos son:

* ¿Con qué frecuencia regresan los usuarios al sitio?
* ¿Cómo se correlaciona la frecuencia de retorno con la conversión? ¿Los compradores habituales realizan visitas frecuentemente o con poca frecuencia?
* ¿Los usuarios que hacen clic en las campañas regresan frecuentemente?

Los usuarios noveles no se incluyen en esta dimensión.

## Rellene esta dimensión con datos

Adobe calcula esta dimensión del lado del servidor a partir del historial de visitas del visitante. No hay ninguna variable que establecer; funciona de forma predeterminada para todas las implementaciones.

| Propiedad | Valor |
| --- | --- |
| **variable de AppMeasurement** | Ninguno (calculado por Adobe) |
| **Campo Web SDK / XDM** | Ninguno (calculado por Adobe) |
| **Parámetro de consulta** | n/a |
| **etiqueta XML** | n/a |
| **Límite de bytes** | n/a |
| **Persistencia** | N/A |

## Elementos de dimensión

Los elementos de dimensión incluyen el número de días entre la última visita de un visitante y el hit actual. Cada número de días es un elemento de dimensión independiente, con `"Same day"` que se produce cuando la última visita de un visitante y el hit actual se produjeron el mismo día.

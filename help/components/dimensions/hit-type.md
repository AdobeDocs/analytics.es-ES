---
title: Tipo de visita
description: Determina si el hit fue un hit en primer o segundo plano.
feature: Dimensions
exl-id: b922adbb-fe36-46c7-aab2-b9471de07d2f
TQID: https://experienceleague.adobe.com/6G-XpOMMZGum9LAQzKn0zGdeNRmHFPpmYizqRrbKuUE
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
  - id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2
    internal-label: VRS
  - id: c77ba355-6681-41fe-b719-563d3f507fdb
    internal-label: Mobile SDK
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 31%
---
# Tipo de hit

El &quot;Tipo de visita&quot; [dimension](overview.md) determina si una aplicación móvil estaba en primer o segundo plano cuando la visita se envió a los servidores de recopilación de datos de Adobe. Esta dimensión solo es relevante para los grupos de informes que contienen datos para aplicaciones móviles. Los datos del explorador recopilados mediante AppMeasurement siempre informan de la visita como `"Foreground"`.

## Rellene esta dimensión con datos

La SDK móvil establece la variable [`customerPerspective`](/help/implement/vars/page-vars/customerperspective.md) para indicar si cada visita se produjo en primer o segundo plano. Esta dimensión funciona de forma predeterminada para todas las implementaciones de SDK móvil en la versión 4.13.6 o superior. Si no usa el SDK móvil, todas las visitas se enumeran bajo `"Foreground"`. Si **[!UICONTROL Impedir que las visitas en segundo plano inicien una nueva visita]** está seleccionado al configurar un [grupo de informes virtuales](../vrs/vrs-mobile-visit-processing.md), las visitas en segundo plano no inflan [[!UICONTROL Visitas]](../metrics/visits.md) ni [[!UICONTROL Visitantes únicos]](../metrics/unique-visitors.md).

| Propiedad | Valor |
| --- | --- |
| **variable de AppMeasurement** | [`customerPerspective`](/help/implement/vars/page-vars/customerperspective.md) |
| **Campo Web SDK / XDM** | Ninguno |
| **Parámetro de consulta** | [`cp`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **etiqueta XML** | [`<customerPerspective>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Límite de bytes** | n/a |
| **Persistencia** | N/A |

## Elementos de dimensión

Los elementos de dimensión incluyen `"Foreground"` y `"Background"`. Las visitas en segundo plano solo se producen en dispositivos móviles en los que la aplicación rastreada está en segundo plano.

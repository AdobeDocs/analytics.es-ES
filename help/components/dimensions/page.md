---
title: Página
description: Nombre de la página.
feature: Dimensions
exl-id: 579963c8-8460-425f-b716-3b30d7a259af
TQID: 'https://experienceleague.adobe.com/npKfFB-zOPzNGJJ6YZvtz0oA3NDWuQiHYBraH09lc58'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4
    internal-label: Attribution
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 54%
---
# Página

La [dimensión](overview.md) &quot;Página&quot; muestra los nombres de las páginas del sitio. Es una de las dimensiones más comunes utilizadas en Adobe Analytics, ya que proporciona una perspectiva sobre las páginas del sitio que funcionan mejor.

Esta dimensión está relacionada con las dimensiones [Sección del sitio](site-section.md) y [Servidor](server.md). La página es más granular, el servidor es menos granular y la sección del sitio está entre los dos.

## Rellene esta dimensión con datos

Establecer la variable [`pageName`](/help/implement/vars/page-vars/pagename.md) en [llamadas de vista de página (`t()`)](/help/implement/vars/functions/t-method.md). Si no se establece la variable `pageName`, esta dimensión vuelve a utilizar la variable [`pageURL`](/help/implement/vars/page-vars/pageurl.md). [Las llamadas de seguimiento de vínculos (`tl()`)](/help/implement/vars/functions/tl-method.md) siempre eliminan esta dimensión, incluso si existe el valor `pageName`.

| Propiedad | Valor |
| --- | --- |
| **variable de AppMeasurement** | [`pageName`](/help/implement/vars/page-vars/pagename.md) |
| **Campo Web SDK / XDM** | [`web.webPageDetails.name`](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-types/webpage-details) |
| **Parámetro de consulta** | [`pageName`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **etiqueta XML** | [`<pageName>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Límite de bytes** | 100 bytes |
| **Persistencia** | Hit |

## Elementos de dimensión

Los elementos de dimensión incluyen los nombres de las páginas del sitio. Su organización determina qué elementos de dimensión específicos desea utilizar. Algunas organizaciones utilizan directamente `document.title`, mientras que otras formulan una ruta de exploración personalizada. Sea cual sea el método que utilice, asegúrese de que sea coherente y de que lo grabe en un [documento de diseño de solución](/help/implement/prepare/solution-design.md).

>[!NOTE]
>
>Analysis Workspace utiliza la última atribución de forma predeterminada, con la opción de utilizar cualquier modelo de atribución.

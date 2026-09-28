---
title: Product
description: Nombre del producto.
feature: Dimensions
exl-id: 2649c200-4b0a-49a9-8592-9b9af72b91cf
TQID: 'https://experienceleague.adobe.com/SMFFeSTkQyQoSWNFc8qHJRxYkJQmiJoKd0v4rS6xRKc'
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
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
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
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 58%
---
# Product

El &quot;producto&quot; [dimension](overview.md) indica el nombre del producto en la visita. Resulta útil para implementaciones que utilizan la variable `products` y desean ver métricas en torno a los productos, como los principales vendedores o los más visitados. Esta dimensión puede estar en blanco si no tiene ningún producto en el sitio.

## Rellene esta dimensión con datos

Esta dimensión hace referencia al nombre del producto en la variable [`products`](/help/implement/vars/page-vars/products.md), que es la cadena entre el primer y el segundo punto y coma (`;`).

| Propiedad | Valor |
| --- | --- |
| **variable de AppMeasurement** | [`products`](/help/implement/vars/page-vars/products.md) |
| **Campo Web SDK / XDM** | [`productListItems[].name`](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/event/commerce-details) |
| **Parámetro de consulta** | [`products`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **etiqueta XML** | [`<products>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Límite de bytes** | 100 bytes |
| **Persistencia** | Hit |

## Elementos de dimensión

Dado que esta variable se basa en una cadena personalizada en la implementación, su organización determina cuáles son los elementos de dimensión. Adobe recomienda que establezca una convención de nombres uniforme para los productos. Las [clasificaciones](../classifications/classifications-overview.md) están disponibles si desea agrupar los productos de forma diferente o proporcionar un nombre más descriptivo. Adobe recomienda utilizar las dimensiones “Producto” y “Categoría”.

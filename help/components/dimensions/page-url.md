---
title: URL de la página
description: La URL de la página.
feature: Dimensions
exl-id: 7c0ec494-d79b-4b65-9161-bdc48485af84
TQID: https://experienceleague.adobe.com/Qek7BUR15HjFpK-XaYQ-J9fkJQiBfNi-ZoqXqaACP0A
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
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
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 52%
---
# URL de la página

La &quot;URL de página&quot; [dimensión](overview.md) enumera las direcciones URL del sitio.

>[!IMPORTANT]
>
>Esta dimensión solo está disponible en Data Warehouse. Si desea utilizar una dimensión URL en otras soluciones de Analytics, pruebe a copiar el valor en un [eVar](evar.md) en cada hit.

## Rellene esta dimensión con datos

AppMeasurement recopila automáticamente la dirección URL de la página en cada [llamada de vista de páginas (`t()`)](/help/implement/vars/functions/t-method.md). Puede anular el valor recopilado mediante la variable [`pageURL`](/help/implement/vars/page-vars/pageurl.md). Si una dirección URL tiene más de 255 bytes, el desbordamiento se almacena en el parámetro de cadena de consulta `-g`. Se incluyen las cadenas de consulta y protocolo en la dirección URL. [Las llamadas de seguimiento de vínculos (`tl()`)](/help/implement/vars/functions/tl-method.md) siempre eliminan esta dimensión, incluso si existe el valor de la dirección URL.

| Propiedad | Valor |
| --- | --- |
| **variable de AppMeasurement** | [`pageURL`](/help/implement/vars/page-vars/pageurl.md) |
| **Campo Web SDK / XDM** | [`web.webPageDetails.URL`](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-types/webpage-details) |
| **Parámetro de consulta** | [`g`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **etiqueta XML** | [`<pageUrl>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Límite de bytes** | 255 bytes (sin límite fijo con desbordamiento) |
| **Persistencia** | Hit |

## Rellenar una eVar con una dirección URL

Adobe recomienda configurar una eVar en la cadena concatenada `window.location.hostname + window.location.pathname`. Esta cadena suele funcionar mejor que `window.location.href` porque omite el protocolo, las cadenas de consulta y las etiquetas de anclaje.

Si desea que la eVar coincida exactamente con la dimensión “URL de página” en Data Warehouse, puede utilizar [variables dinámicas](/help/implement/vars/page-vars/dynamic-variables.md) y establecer la eVar en `D=g` en cada hit.

## Elementos de dimensión

Los elementos de dimensión incluyen las direcciones URL de las páginas del sitio.

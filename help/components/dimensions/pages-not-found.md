---
title: Páginas no encontradas (dimensiones)
description: Direcciones URL que devolvieron un error en el sitio.
feature: Dimensions
exl-id: 28c22565-7fcf-49f1-8876-0db88f12a182
TQID: 'https://experienceleague.adobe.com/0S2WzNRJrtOa9ZPTg5cmbwxMLJE5tI6Qa3GtZs6GqKc'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
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
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 48%
---
# Páginas no encontradas

>[!BEGINSHADEBOX]

*Esta página de ayuda describe cómo funciona &quot;Páginas no encontradas&quot; como [dimensión](overview.md). Consulte la página de métrica [Páginas no encontradas](../metrics/pages-not-found.md) para obtener información sobre cómo funciona como métrica.*

>[!ENDSHADEBOX]

La dimensión “Páginas no encontradas” muestra las direcciones URL que contenían un error. Esta dimensión es útil cuando desea reducir el número de errores que los visitantes obtienen en el sitio.

* Puede utilizar esta dimensión en una [visualización de flujo](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) para ver en qué páginas hacen clic los visitantes para llegar al error. A continuación, puede trabajar con los equipos de desarrollo de su organización para corregir el vínculo en cada página.
* Puede utilizar esta dimensión con la dimensión [“Remitente del reenvío”](referrer.md) para ver a qué parte de su sitio llegan los visitantes desde vínculos externos. A continuación, puede implementar redirecciones a la ubicación deseada o trabajar con el tercero para corregir el vínculo.

>[!NOTE]
>
>En Data Warehouse, esta dimensión se denomina &#39;[!UICONTROL Error de tipo de página]&#39;.

## Rellene esta dimensión con datos

AppMeasurement recopila estos datos mediante la variable [`pageType`](/help/implement/vars/page-vars/pagetype.md). Cuando `pageType` se establece en `errorPage`, la dirección URL de la página de la visita se registra como un elemento de dimensión. Si la variable `pageType` no está definida o está establecida en cualquier otro valor, no se recopilarán datos para esta dimensión.

| Propiedad | Valor |
| --- | --- |
| **variable de AppMeasurement** | [`pageType`](/help/implement/vars/page-vars/pagetype.md) |
| **Campo Web SDK / XDM** | [`web.webPageDetails.isErrorPage`](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-types/webpage-details) |
| **Parámetro de consulta** | [`pageType`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **etiqueta XML** | [`<pageType>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Límite de bytes** | n/a |
| **Persistencia** | Hit |

## Elementos de dimensión

Los elementos de dimensión incluyen las direcciones URL de las páginas del sitio en las que se produjo un error.

---
title: Páginas no encontradas (dimensiones)
description: Direcciones URL que devolvieron un error en el sitio.
feature: Dimensions
exl-id: 28c22565-7fcf-49f1-8876-0db88f12a182
TQID: https://experienceleague.adobe.com/0S2WzNRJrtOa9ZPTg5cmbwxMLJE5tI6Qa3GtZs6GqKc
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 232
ht-degree: 73%

---

# Páginas no encontradas

*Esta página de ayuda describe cómo funciona &quot;Páginas no encontradas&quot; como [dimensión](overview.md). Consulte la página de métrica [Páginas no encontradas](../metrics/pages-not-found.md) para obtener información sobre cómo funciona como métrica.*

La dimensión “Páginas no encontradas” muestra las direcciones URL que contenían un error. Esta dimensión es útil cuando desea reducir el número de errores que los visitantes obtienen en el sitio.

* Puede utilizar esta dimensión en una [visualización de flujo](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) para ver en qué páginas hacen clic los visitantes para llegar al error. A continuación, puede trabajar con los equipos de desarrollo de su organización para corregir el vínculo en cada página.
* Puede utilizar esta dimensión con la dimensión [“Remitente del reenvío”](referrer.md) para ver a qué parte de su sitio llegan los visitantes desde vínculos externos. A continuación, puede implementar redirecciones a la ubicación deseada o trabajar con el tercero para corregir el vínculo.

>[!NOTE]
>
>En Data Warehouse, esta dimensión se denomina &#39;[!UICONTROL Error de tipo de página]&#39;.

## Rellene esta dimensión con datos

Esta dimensión recupera datos de [`pageType` y las `g` cadenas de consulta](/help/implement/validate/query-parameters.md) en solicitudes de imagen. Si la cadena de consulta `pageType` es igual a `errorPage`, se registra la cadena de consulta `g` (URL de la página). AppMeasurement recopila estos datos mediante la variable [`pageType`](/help/implement/vars/page-vars/pagetype.md). Si la variable `pageType` no está definida o configurada en otra cosa que no sea `errorPage`, no se recopilarán datos para esta dimensión.

## Elementos de dimensión

Los elementos de dimensión incluyen las direcciones URL de las páginas del sitio en las que se produjo un error.

---
title: Página
description: Nombre de la página.
feature: Dimensions
exl-id: 579963c8-8460-425f-b716-3b30d7a259af
TQID: https://experienceleague.adobe.com/npKfFB-zOPzNGJJ6YZvtz0oA3NDWuQiHYBraH09lc58
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 188
ht-degree: 80%

---

# Página

La [dimensión](overview.md) &quot;Página&quot; muestra los nombres de las páginas del sitio. Es una de las dimensiones más comunes utilizadas en Adobe Analytics, ya que proporciona una perspectiva sobre las páginas del sitio que funcionan mejor.

Esta dimensión está relacionada con las dimensiones [Sección del sitio](site-section.md) y [Servidor](server.md). La página es más granular, el servidor es menos granular y la sección del sitio está entre los dos.

## Rellene esta dimensión con datos

Esta dimensión recupera datos de la [`pageName`cadena de consulta](/help/implement/validate/query-parameters.md) en [Llamadas de vista de páginas (`t()`)](/help/implement/vars/functions/t-method.md). [Las llamadas de seguimiento de vínculos (`tl()`)](/help/implement/vars/functions/tl-method.md) siempre eliminan esta dimensión, aunque exista la cadena de consulta `pageName`.

AppMeasurement recopila estos datos mediante la variable [`pageName`](/help/implement/vars/page-vars/pagename.md). Si no se establece la variable `pageName`, esta dimensión vuelve a utilizar la variable [`pageURL`](/help/implement/vars/page-vars/pageurl.md).

## Elementos de dimensión

Los elementos de dimensión incluyen los nombres de las páginas del sitio. Su organización determina qué elementos de dimensión específicos desea utilizar. Algunas organizaciones utilizan directamente `document.title`, mientras que otras formulan una ruta de exploración personalizada. Sea cual sea el método que utilice, asegúrese de que sea coherente y de que lo grabe en un [documento de diseño de solución](/help/implement/prepare/solution-design.md).

>[!NOTE]
>
>Analysis Workspace utiliza la última atribución de forma predeterminada, con la opción de utilizar cualquier modelo de atribución.

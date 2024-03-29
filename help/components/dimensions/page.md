---
title: Página
description: Nombre de la página.
feature: Dimensions
exl-id: 579963c8-8460-425f-b716-3b30d7a259af
source-git-commit: 93099d36a65ca2bf16fbd6342f01bfecdc8c798e
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 94%

---

# Página

La &quot;Página&quot; [dimensión](overview.md) muestra los nombres de las páginas del sitio. Es una de las dimensiones más comunes utilizadas en Adobe Analytics, ya que proporciona una perspectiva sobre las páginas del sitio que funcionan mejor.

Esta dimensión está relacionada con las dimensiones [Sección del sitio](site-section.md) y [Servidor](server.md). La página es más granular, el servidor es menos granular y la sección del sitio está entre los dos.

## Rellene esta dimensión con datos

Esta dimensión recupera datos de la [`pageName`cadena de consulta](/help/implement/validate/query-parameters.md) en [Llamadas de vista de páginas (`t()`)](/help/implement/vars/functions/t-method.md). [Las llamadas de seguimiento de vínculos (`tl()`)](/help/implement/vars/functions/tl-method.md) siempre eliminan esta dimensión, aunque exista la cadena de consulta `pageName`.

AppMeasurement recopila estos datos mediante la variable [`pageName`](/help/implement/vars/page-vars/pagename.md). Si la variable `pageName` no está definida, vuelve a utilizar la variable [`pageURL`](/help/implement/vars/page-vars/pageurl.md).

## Elementos de dimensión

Los elementos de dimensión incluyen los nombres de las páginas del sitio. Su organización determina qué elementos de dimensión específicos desea utilizar. Algunas organizaciones utilizan directamente `document.title`, mientras que otras formulan una ruta de exploración personalizada. Sea cual sea el método que utilice, asegúrese de que sea coherente y de que lo grabe en un [documento de diseño de solución](/help/implement/prepare/solution-design.md).

>[!NOTE]
>
>Analysis Workspace utiliza la última atribución de forma predeterminada, con la opción de utilizar cualquier modelo de atribución.

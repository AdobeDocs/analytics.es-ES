---
title: Página
description: Nombre de la página.
translation-type: tm+mt
source-git-commit: ec6d8e6a3cef3a5fd38d91775c83ab95de47fd55
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 71%

---


# Página

La dimensión “Página” muestra los nombres de las páginas del sitio. Es una de las dimensiones más comunes utilizadas en Adobe Analytics, ya que proporciona una perspectiva sobre las páginas del sitio que funcionan mejor.

Esta dimensión está relacionada con las dimensiones [Sección del sitio ](site-section.md) y [Servidor](server.md). La página es más granular, el servidor es menos granular y la sección del sitio está entre los dos.

## Rellene esta dimensión con datos

Esta dimensión recupera datos de la cadena [`pageName` de](/help/implement/validate/query-parameters.md) consulta en las llamadas de vista de [página (`t()`)](/help/implement/vars/functions/t-method.md). [Las llamadas de seguimiento de vínculos (`tl()`)](/help/implement/vars/functions/tl-method.md) siempre eliminan esta dimensión, incluso si existe la cadena de `pageName` consulta.

AppMeasurement recopila estos datos mediante la variable [`pageName`](/help/implement/vars/page-vars/pagename.md). If the `pageName` variable is not defined, it falls back to using the [`pageURL`](/help/implement/vars/page-vars/pageurl.md) variable.

## Elementos de Dimension

Los elementos de Dimension incluyen los nombres de las páginas del sitio. Su organización determina qué elementos de dimensión específicos desea utilizar. Algunas organizaciones utilizan directamente `document.title`, mientras que otras formulan una ruta de exploración personalizada. Sea cual sea el método que utilice, asegúrese de que sea coherente y de que lo grabe en un [documento de diseño de solución](/help/implement/prepare/solution-design.md).

>[!NOTE]
>
>En Reports &amp; Analytics, las métricas de conversión utilizan la atribución lineal para esta dimensión. Por ejemplo, los ingresos se dividen entre todas las páginas vistas en una visita antes de un evento `purchase`. Analysis Workspace utiliza la última atribución de forma predeterminada, con la opción de utilizar cualquier modelo de atribución.

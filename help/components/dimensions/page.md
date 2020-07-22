---
title: Página
description: Nombre de la página.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 3%

---


# Página

La dimensión &#39;Página&#39; lista los nombres de las páginas del sitio. Es una de las dimensiones más comunes utilizadas en Adobe Analytics, ya que proporciona una perspectiva sobre las páginas del sitio que funcionan mejor.

Esta dimensión está relacionada con la sección [](site-section.md) Sitio y las dimensiones [Servidor](server.md) . La página es más granular, el servidor es menos granular y la sección Sitio está entre los dos.

## Rellenar esta dimensión con datos

Esta dimensión recupera datos de la cadena [`pageName` de](/help/implement/validate/query-parameters.md) consulta en solicitudes de imagen. AppMeasurement recopila estos datos mediante la `pageName` variable. Si la `pageName` variable no está definida, vuelve a utilizar la dirección URL de la página.

## Elementos de dimensión

Los elementos de dimensión incluyen los nombres de las páginas del sitio. Su organización determina qué elementos de dimensión específicos desea utilizar. Algunas organizaciones utilizan directamente `document.title`, mientras que otras formulan una ruta de exploración personalizada. Sea cual sea el método que utilice, asegúrese de que sea coherente y de que lo grabe en un documento [de diseño de](/help/implement/prepare/solution-design.md)solución.

>[!NOTE]
>
>En Informes y Analytics, las métricas de conversión utilizan la atribución lineal para esta dimensión. For example, revenue is split between all pages viewed in a visit before a `purchase` event. Analysis Workspace utiliza la última atribución de forma predeterminada, con la opción de utilizar cualquier modelo de atribución.

---
title: Sección Sitio
description: Nombre de la sección del sitio.
translation-type: tm+mt
source-git-commit: 1869d69566d26aa7d99c520efc2e835901439d48
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 0%

---


# Sección Sitio

La dimensión &#39;Sección del sitio&#39; lista los nombres de las secciones del sitio. Para los sitios grandes, resulta útil agrupar las páginas en secciones. Esta dimensión es útil para ver las secciones del sitio más visitadas o de mayor rendimiento.

Esta dimensión está relacionada con las dimensiones [Página](page.md) y [Servidor](server.md) . La página es más granular, el servidor es menos granular y la sección Sitio está entre los dos.

## Rellenar esta dimensión con datos

Esta dimensión recupera datos de la cadena [`ch` de](/help/implement/validate/query-parameters.md) consulta en solicitudes de imagen. AppMeasurement recopila estos datos mediante la [`channel`](/help/implement/vars/page-vars/channel.md) variable.

## Valores de dimensión

Los valores de dimensión incluyen los nombres de las secciones del sitio. Su organización determina qué valores de dimensión específicos desea utilizar. Sea cual sea el método que utilice, asegúrese de que sea coherente y de que lo grabe en un documento [de diseño de](/help/implement/prepare/solution-design.md)solución.

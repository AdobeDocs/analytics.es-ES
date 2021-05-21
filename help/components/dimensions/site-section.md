---
title: Sección del sitio
description: Nombre de la sección del sitio.
exl-id: 349bace0-4596-4b4c-bf29-6cd8866c246b
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '137'
ht-degree: 100%

---

# Sección del sitio

La dimensión “Sección del sitio” incluye los nombres de las secciones del sitio. Para los sitios grandes, resulta útil agrupar las páginas en secciones. Esta dimensión es útil para ver las secciones del sitio más visitadas o de mayor rendimiento.

Esta dimensión está relacionada con las dimensiones [Página](page.md) y [Servidor](server.md). La página es más granular, el servidor es menos granular y la sección del sitio está entre los dos.

## Rellene esta dimensión con datos

Esta dimensión recupera datos de la [`ch`cadena de consulta](/help/implement/validate/query-parameters.md) en solicitudes de imagen. AppMeasurement recopila estos datos mediante la variable [`channel`](/help/implement/vars/page-vars/channel.md).

## Elementos de dimensión

Los elementos de dimensión incluyen los nombres de las secciones del sitio. Su organización determina qué elementos de dimensión específicos desea utilizar. Sea cual sea el método que utilice, asegúrese de que sea coherente y de que lo grabe en un [documento de diseño de solución](/help/implement/prepare/solution-design.md).

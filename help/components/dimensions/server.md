---
title: Servidor
description: El nombre del servidor.
exl-id: c2454c0d-497e-46f8-8569-7d0517097cab
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '136'
ht-degree: 100%

---

# Servidor

La dimensión “Servidor” generalmente indica el nombre de host del sitio. Para los grupos de informes que combinan varios dominios o subdominios, esta dimensión es valiosa para ver qué dominios o subdominios funcionan mejor.

Esta dimensión está relacionada con las dimensiones de la sección [Página](page.md) y [Sección del sitio](site-section.md). La página es más granular, el servidor es menos granular y la sección del sitio está entre los dos.

## Rellene esta dimensión con datos

Esta dimensión recupera datos de la [`server`cadena de consulta](/help/implement/validate/query-parameters.md) en solicitudes de imagen. AppMeasurement recopila estos datos mediante la variable [`server`](/help/implement/vars/page-vars/server.md).

## Elementos de dimensión

Los elementos de dimensión incluyen los servidores del sitio. Su organización determina qué elementos de dimensión específicos desea utilizar. Algunas organizaciones utilizan `window.location.hostname`, mientras que otras formulan valores personalizados. Sea cual sea el método que utilice, asegúrese de que sea coherente y de que lo grabe en un [documento de diseño de solución](/help/implement/prepare/solution-design.md).

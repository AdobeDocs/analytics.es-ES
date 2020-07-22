---
title: Server
description: El nombre del servidor.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 1%

---


# Server

La dimensión &#39;Servidor&#39; generalmente lista el nombre de host del sitio. Para los grupos de informes que combinan varios dominios o subdominios, esta dimensión es valiosa para ver qué dominios o subdominios funcionan mejor.

Esta dimensión está relacionada con las dimensiones de la sección [Página](page.md) y [](site-section.md) Sitio. La página es más granular, el servidor es menos granular y la sección Sitio está entre los dos.

## Rellenar esta dimensión con datos

Esta dimensión recupera datos de la cadena [`server` de](/help/implement/validate/query-parameters.md) consulta en solicitudes de imagen. AppMeasurement recopila estos datos mediante la [`server`](/help/implement/vars/page-vars/server.md) variable.

## Elementos de dimensión

Los elementos de dimensión incluyen servidores en el sitio. Su organización determina qué elementos de dimensión específicos desea utilizar. Algunas organizaciones utilizan `window.location.hostname`, mientras que otras formulan valores personalizados. Sea cual sea el método que utilice, asegúrese de que sea coherente y de que lo grabe en un documento [de diseño de](/help/implement/prepare/solution-design.md)solución.

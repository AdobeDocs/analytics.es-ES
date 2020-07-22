---
title: Páginas no encontradas
description: Direcciones URL que devolvieron un error en el sitio.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 2%

---


# Páginas no encontradas

*Esta página de ayuda describe cómo funciona &#39;Páginas no encontradas&#39; como dimensión. Consulte la métrica[Páginas no encontradas](../metrics/pages-not-found.md)para obtener más información.*

La dimensión &#39;Páginas no encontradas&#39; muestra las direcciones URL que contenían un error. Esta dimensión es útil cuando desea reducir el número de errores que el visitante obtiene en el sitio.

* Puede utilizar esta dimensión en una visualización [de](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) flujo para ver qué páginas pulsan los visitantes para llegar al error. A continuación, puede trabajar con los equipos de desarrollo de su organización para corregir el vínculo en cada página.
* Puede utilizar esta dimensión con la dimensión [&#39;Remitente del reenvío&#39;](referrer.md) para ver dónde llegan los visitantes a su sitio a partir de vínculos externos. A continuación, puede implementar redirecciones a la ubicación deseada o trabajar con el tercero para corregir el vínculo.

## Rellenar esta dimensión con datos

Esta dimensión recupera datos de las cadenas [`pageType` y de `g` consulta](/help/implement/validate/query-parameters.md) en solicitudes de imagen. Si la cadena de `pageType` consulta es igual a `errorPage`, se registra la cadena de `g` consulta (URL de la página). AppMeasurement recopila estos datos mediante la [`pageType`](/help/implement/vars/page-vars/pagetype.md) variable. Si la `pageType` variable no está definida o configurada en otra cosa que no sea `errorPage`, no se recopilarán datos para esta dimensión.

## Elementos de dimensión

Los elementos de dimensión incluyen las direcciones URL de las páginas del sitio en las que se produjo un error.

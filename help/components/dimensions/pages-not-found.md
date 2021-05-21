---
title: Páginas no encontradas
description: Direcciones URL que devolvieron un error en el sitio.
exl-id: 28c22565-7fcf-49f1-8876-0db88f12a182
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '214'
ht-degree: 100%

---

# Páginas no encontradas

*Esta página de ayuda describe cómo funciona “Páginas no encontradas” como dimensión. Consulte la métrica [Páginas no encontradas](../metrics/pages-not-found.md) para obtener más información.*

La dimensión “Páginas no encontradas” muestra las direcciones URL que contenían un error. Esta dimensión es útil cuando desea reducir el número de errores que el visitante obtiene en el sitio.

* Puede utilizar esta dimensión en una [visualización de flujo](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) para ver qué páginas pulsan los visitantes para llegar al error. A continuación, puede trabajar con los equipos de desarrollo de su organización para corregir el vínculo en cada página.
* Puede utilizar esta dimensión con la dimensión [“Remitente del reenvío”](referrer.md) para ver a qué parte de su sitio llegan los visitantes desde vínculos externos. A continuación, puede implementar redirecciones a la ubicación deseada o trabajar con el tercero para corregir el vínculo.

## Rellene esta dimensión con datos

Esta dimensión recupera datos de [`pageType` y las `g` cadenas de consulta](/help/implement/validate/query-parameters.md) en solicitudes de imagen. Si la cadena de consulta `pageType` es igual a `errorPage`, se registra la cadena de consulta `g` (URL de la página). AppMeasurement recopila estos datos mediante la variable [`pageType`](/help/implement/vars/page-vars/pagetype.md). Si la variable `pageType` no está definida o configurada en otra cosa que no sea `errorPage`, no se recopilarán datos para esta dimensión.

## Elementos de dimensión

Los elementos de dimensión incluyen las direcciones URL de las páginas del sitio en las que se produjo un error.

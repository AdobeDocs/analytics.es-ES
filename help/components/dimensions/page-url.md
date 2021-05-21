---
title: URL de la página
description: La URL de la página.
exl-id: 7c0ec494-d79b-4b65-9161-bdc48485af84
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '221'
ht-degree: 100%

---

# URL de la página

La dimensión “URL de página” indica las direcciones URL del sitio.

>[!IMPORTANT]
>
>Esta dimensión solo está disponible en Data Warehouse. Si desea utilizar una dimensión URL en otras soluciones de Analytics, pruebe a copiar el valor en un [eVar](evar.md) en cada visita.

## Rellene esta dimensión con datos

Esta dimensión recupera datos de [`g` y las `-g` cadenas de consulta](/help/implement/validate/query-parameters.md) en [solicitudes de imagen (`t()`)](/help/implement/vars/functions/t-method.md). [Las llamadas de seguimiento de vínculos (`tl()`)](/help/implement/vars/functions/tl-method.md) siempre eliminan esta dimensión, aunque exista la cadena de consulta `g`.

A veces, las direcciones URL tienen más de 255 bytes. AppMeasurement utiliza el parámetro de cadena de consulta de `g` para los primeros 255 bytes de la dirección URL en las solicitudes de imagen. Si una dirección URL tiene más de 255 bytes, el resto de la dirección URL se almacena en el parámetro de cadena de consulta de `-g`. Las cadenas de consulta y protocolo de la dirección URL se incluyen en esta variable.

AppMeasurement recopila automáticamente estos datos en función de la dirección URL de la página. Puede anular el valor recopilado mediante la variable [`pageURL`](/help/implement/vars/page-vars/pageurl.md).

## Rellenar una eVar con una dirección URL

Adobe recomienda configurar una eVar en la cadena concatenada `window.location.hostname + window.location.pathname`. Esta cadena suele funcionar mejor que `window.location.href` porque omite el protocolo, las cadenas de consulta y las etiquetas de anclaje.

Si desea que la eVar coincida exactamente con la dimensión “URL de página” en Data Warehouse, puede utilizar [variables dinámicas](/help/implement/vars/page-vars/dynamic-variables.md) y establecer la eVar en `D=g` en cada visita.

## Elementos de dimensión

Los elementos de dimensión incluyen las direcciones URL de las páginas del sitio.

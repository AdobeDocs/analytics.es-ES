---
title: URL de la página
description: La URL de la página.
translation-type: tm+mt
source-git-commit: ec6d8e6a3cef3a5fd38d91775c83ab95de47fd55
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 64%

---


# URL de la página

La dimensión “URL de página” indica las direcciones URL del sitio.

>[!IMPORTANT]
>
>Esta dimensión solo está disponible en Data Warehouse. Si desea utilizar una dimensión URL en otras soluciones de Analytics, considere copiar el valor en un [eVar](evar.md) en cada visita.

## Rellene esta dimensión con datos

This dimension retrieves data from the [`g` and `-g` query strings](/help/implement/validate/query-parameters.md) in [Page view calls (`t()`)](/help/implement/vars/functions/t-method.md). [Las llamadas de seguimiento de vínculos (`tl()`)](/help/implement/vars/functions/tl-method.md) siempre eliminan esta dimensión, incluso si existe la cadena de `g` consulta.

A veces, las direcciones URL tienen más de 255 bytes. AppMeasurement utiliza el parámetro de cadena de consulta de `g` para los primeros 255 bytes de la dirección URL en las solicitudes de imagen. Si una dirección URL tiene más de 255 bytes, el resto de la dirección URL se almacena en el parámetro de cadena de consulta de `-g`. Las cadenas de consulta y protocolo de la dirección URL se incluyen en esta variable.

AppMeasurement recopila automáticamente estos datos en función de la dirección URL de la página. Puede anular el valor recopilado mediante la [`pageURL`](/help/implement/vars/page-vars/pageurl.md) variable.

## Rellenar una eVar con una dirección URL

Adobe recomienda configurar una eVar en la cadena concatenada `window.location.hostname + window.location.pathname`. Esta cadena suele funcionar mejor que `window.location.href` porque omite el protocolo, las cadenas de consulta y las etiquetas de anclaje.

Si desea que la eVar coincida exactamente con la dimensión “URL de página” en Data Warehouse, puede utilizar [variables dinámicas](/help/implement/vars/page-vars/dynamic-variables.md) y establecer la eVar en `D=g` en cada visita.

## Elementos de Dimension

Los elementos de Dimension incluyen las direcciones URL de las páginas del sitio.

---
title: URL de la página
description: La dirección URL de la página.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 2%

---


# URL de la página

La dimensión &#39;URL de página&#39; lista las direcciones URL del sitio.

>[!IMPORTANT]
>
>Esta dimensión solo está disponible en Data warehouse. Si desea utilizar una dimensión URL en otras soluciones de Analytics, utilice una [eVar](evar.md).

## Rellenar esta dimensión con datos

Esta dimensión recupera datos de la cadena [`g` de](/help/implement/validate/query-parameters.md) consulta en solicitudes de imagen. AppMeasurement recopila estos datos mediante la [`pageURL`](/help/implement/vars/page-vars/pageurl.md) variable.

## Rellenar una eVar con dirección URL

Adobe recomienda configurar una eVar en la cadena concatenada `window.location.hostname + window.location.pathname`. Esta cadena suele funcionar mejor que `window.location.href` porque omite el protocolo, las cadenas de consulta y las etiquetas de anclaje.

Si desea que la eVar coincida exactamente con la dimensión &#39;URL de página&#39; en la Data warehouse, puede utilizar variables [](/help/implement/vars/page-vars/dynamic-variables.md) dinámicas y establecer la eVar en `D=g` cada visita. Tenga en cuenta que este método no funciona para las visitas de vínculos personalizados, ya que la dirección URL de la página se elimina para todas las [`tl()`](/help/implement/vars/functions/tl-method.md) llamadas.

## Elementos de dimensión

Los elementos de dimensión incluyen las direcciones URL de las páginas del sitio.

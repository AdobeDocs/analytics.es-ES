---
title: URL de la página
description: La URL de la página.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 92%

---


# URL de la página

La dimensión “URL de página” indica las direcciones URL del sitio.

>[!IMPORTANT]
>
>Esta dimensión solo está disponible en Data Warehouse. Si desea utilizar una dimensión URL en otras soluciones de Analytics, utilice una [eVar](evar.md).

## Rellene esta dimensión con datos

Esta dimensión recupera datos de la [`g`cadena de consulta](/help/implement/validate/query-parameters.md) en solicitudes de imagen. AppMeasurement recopila estos datos mediante la variable [`pageURL`](/help/implement/vars/page-vars/pageurl.md).

## Rellenar una eVar con una dirección URL

Adobe recomienda configurar una eVar en la cadena concatenada `window.location.hostname + window.location.pathname`. Esta cadena suele funcionar mejor que `window.location.href` porque omite el protocolo, las cadenas de consulta y las etiquetas de anclaje.

Si desea que la eVar coincida exactamente con la dimensión “URL de página” en Data Warehouse, puede utilizar [variables dinámicas](/help/implement/vars/page-vars/dynamic-variables.md) y establecer la eVar en `D=g` en cada visita. Tenga en cuenta que este método no funciona para las visitas de vínculos personalizados, ya que la dirección URL de la página se elimina para todas las a [`tl()`](/help/implement/vars/functions/tl-method.md).

## Elementos de Dimension

Los elementos de Dimension incluyen las direcciones URL de las páginas del sitio.

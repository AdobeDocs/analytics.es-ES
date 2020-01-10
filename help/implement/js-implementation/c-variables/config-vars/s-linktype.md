---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Analytics Implementation
solution: null
title: Variables dinámicas
translation-type: ht
source-git-commit: 21f278017472ae39c6066ca7694a5cdbbfde41f3

---


# s.linkType

Contiene el tipo de vínculo determinado automáticamente, si hubiera. Se puede configurar como uno de los siguientes:

    * “d” (descarga)
    * “e” (salida)
    * “o” (personalizado/otro)

Este es el parámetro `pe` en la solicitud de imagen. Si se configura con [`linkURL`](https://docs.adobe.com/content/help/es-ES/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkurl.html) o [`linkName`](https://docs.adobe.com/content/help/es-ES/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkname.html), se envía una llamada al servidor como un vínculo de descarga, de salida o personalizado.

*Nota: La variable[`pageName`](https://docs.adobe.com/content/help/es-ES/analytics/implementation/testing-and-validation/optimize-implementation/page-naming-strategies.translate.html)no se puede establecer para una descarga de archivo, un vínculo de salida o un vínculo personalizado, porque ninguno de los tipos de vínculos es una vista de página y no tiene un nombre de página asociado.*


**Ejemplo**

```js
function s_doPlugins(s) { 
    if (s.linkType == "d" && s.linkURL.indexOf(".aspx?f=") { 
        //special tracking for .aspx file download script 
        s.eVar11 = s.linkURL.substring(s.linkURL.lastIndexOf("?f=") + 3, s.linkURL.length); 
    } 
  
    else if (s.linkType == "o" ) { 
        // note: linkType is set to "o" only if you make a custom call 
        // to s.tl() and set the link type to "o". Automatically tracked 
        // links are set to "d" or "e" only. 
        s.eVar10 = s.LinkURL; 
    } 
}
```

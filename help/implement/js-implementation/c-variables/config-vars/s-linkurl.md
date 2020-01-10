---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Analytics Implementation
seo-description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
solution: null
title: Variables dinámicas
translation-type: ht
source-git-commit: 1773e84809e04b3be25c77bf1fb8ad8317b7f8c0

---


# s-linkURL

La dirección URL del vínculo que actúa como nombre si no existe ningún valor para `linkName`. Se puede establecer en cualquier cadena de URL. Este es el parámetro `pev1` en la solicitud de imagen.


Si se configura con [`linkType`](https://docs.adobe.com/content/help/es-ES/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html), se enviará una solicitud de imagen como un vínculo de descarga, de salida o personalizado.


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

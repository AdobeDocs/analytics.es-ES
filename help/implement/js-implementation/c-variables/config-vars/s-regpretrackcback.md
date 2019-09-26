---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Implementación de análisis
seo-description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
solution: null
title: Variables dinámicas
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# s.registerPreTrackCallback and s.registerPostTrackCallback

Estas funciones toman como parámetros la rellamada (una función) y los parámetros que llevan a esa función. Por ejemplo:

```
s.registerPreTrackCallback(function(requestUrl,a,b,c) { 
    console.log("pre track callback"); 
    console.dir(requestUrl); // Request URL 
    console.dir(a); // param1 
    console.dir(b); // param2 
    console.dir(c); // param3 
}, "param1", "param2", "param3");
```

La rellamada se invoca con `requestUrl` y cualquier parámetro que haya pasado cuando se registró la rellamada. Esto ocurre antes o después de la llamada de seguimiento, según el método que se utilice para registrar la rellamada.

No se puede garantizar el orden en el que se realizan estas rellamadas. Las rellamadas que se registran en la función previa se invocan después de crearse la URL de seguimiento final. Las rellamadas posteriores se realizan cuando se ha llevado a cabo una llamada de seguimiento con éxito (si la llamada de seguimiento falla, no se llaman a estas funciones). Las rellamadas que se registren con `registerPreTrackCallback` no afectan a la llamada de seguimiento. Además, no se recomienda llamar a ninguno de los métodos de seguimiento en una rellamada registrada, ya que podría causar un bucle infinito.

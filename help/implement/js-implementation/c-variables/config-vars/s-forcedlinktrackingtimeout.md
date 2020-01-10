---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Analytics Implementation
seo-description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
solution: null
title: Variables dinámicas
translation-type: ht
source-git-commit: 0c7093518933a88c5057ba95cb3564d6ca0ebcad

---



# s.forcedLinkTrackingTimeout

Este valor especifica el tiempo de espera máximo. Establece el número máximo de milisegundos que hay que esperar para que finalice el seguimiento antes de efectuar el parámetro `doneAction` que se pasó a `s.tl`. Si la llamada de seguimiento de vínculos se completa antes de este tiempo de espera, el parámetro `doneAction` se ejecuta inmediatamente. Si nota que las llamadas de seguimiento de vínculos no se completan, es posible que tenga que aumentar este tiempo de espera.

Valor predeterminado: 250

Ejemplo: `s.forcedLinkTrackingTimeout = 500`

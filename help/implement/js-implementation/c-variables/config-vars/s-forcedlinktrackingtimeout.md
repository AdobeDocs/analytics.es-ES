---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Analytics Implementation
seo-description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
solution: null
title: Variables dinámicas
translation-type: tm+mt
source-git-commit: 0c7093518933a88c5057ba95cb3564d6ca0ebcad

---



# s.forceLinkTrackingTimeout

Este valor especifica el tiempo de espera máximo. Specifically, it sets the maximum number of milliseconds to wait for tracking to finish before performing the `doneAction` that was passed into `s.tl`. Si la llamada de seguimiento de vínculos se completa antes de este tiempo de espera, el parámetro `doneAction` se ejecuta inmediatamente. Si nota que las llamadas de seguimiento de vínculos no se completan, es posible que tenga que aumentar este tiempo de espera.

Valor predeterminado = 250

Ejemplo: `s.forcedLinkTrackingTimeout = 500`

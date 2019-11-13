---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Implementación de Analytics
seo-description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
solution: null
title: Variables dinámicas
translation-type: tm+mt
source-git-commit: 8c06a54ccd652f3f915af3af040e9cc69f01d0c1

---



# s.forceLinkTrackingTimeout

El número máximo de milisegundos que hay que esperar para que finalice el seguimiento antes de ejecutar el parámetro doneAction que se pasó a `s.tl`. Este valor especifica el tiempo de espera máximo. Si la llamada de seguimiento de vínculos se completa antes de este tiempo de espera, el parámetro doneAction se ejecuta inmediatamente. Si nota que las llamadas de seguimiento de vínculos no se completan, es posible que tenga que aumentar este tiempo de espera.

Valor predeterminado = 250

Ejemplo: `s.forcedLinkTrackingTimeout = 500`

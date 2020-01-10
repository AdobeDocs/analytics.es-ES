---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Analytics Implementation
solution: null
title: Variables dinámicas
translation-type: ht
source-git-commit: 8deec068fcea49f1183633826d5ce8271fb38a14

---



# s.useForcedLinkTracking

Esta marca se usa para deshabilitar el seguimiento de vínculos forzado para algunos exploradores. El seguimiento de vínculos forzado está habilitado de forma predeterminada para los exploradores FireFox 20+ y WebKit.

Cuando se habilita `useForcedLinkTracking`, el archivo AppMeasurement anula el comportamiento predeterminado de los vínculos en algunos exploradores para evitar que la llamada de seguimiento de vínculos se cancele cuando se abra una nueva página. El archivo AppMeasurement ejecuta esta llamada y administra el evento de navegación de forma manual, en lugar de realizar la acción predeterminada del explorador.

En JavaScript H.25.4 (lanzado en febrero de 2013), se agregaron las siguientes limitaciones de ámbito a los vínculos seguidos cuando `useForcedLinkTracking` está habilitada. El seguimiento de vínculo forzado automático solo se aplica a:

* Etiquetas `<A>` y `<AREA>`.
* La etiqueta debe tener un atributo `HREF`
* El atributo `HREF` no puede empezar con `#`, `about:` o `javascript:`.
* El atributo `TARGET` no debe estar configurado o bien `TARGET` tiene que referirse a la ventana actual (`_self`_`_top`, o el valor de `window.name`).

Valor predeterminado = `true`

## Ejemplo

`s.useForcedLinkTracking = false`

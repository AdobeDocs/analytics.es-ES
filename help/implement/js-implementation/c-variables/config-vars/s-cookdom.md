---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Analytics Implementation
solution: null
title: Variables dinámicas
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.cookieDomain

La variable determina el dominio en que se establecen las cookies de [!DNL Analytics] `s_cc`y `s_sq`.

Normalmente, `s.cookieDomainPeriods` se utiliza para generar `s.cookieDomain` desde `window.location.hostname`. En lugar de utilizar `s.cookieDomainPeriods`, puede establecer de forma explícita `s.cookieDomain` en el valor que desee utilizar en su implementación. Por ejemplo, podría establecer cookies en el nombre de página completo mediante:

`s.cookieDomain = window.location.hostname;`

---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Implementación de análisis
seo-description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
solution: null
title: Variables dinámicas
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# s.cookieDomain

The  variable determines the domain on which the [!DNL Analytics] cookies `s_cc` and `s_sq` are set.

Normalmente, `s.cookieDomainPeriods` se utiliza para generar `s.cookieDomain` a partir de `window.location.hostname`.  En lugar de usar `s.cookieDomainPeriods`, puede establecer explícitamente `s.cookieDomain` lo que desee utilizar en la implementación. Por ejemplo, podría establecer cookies en el nombre de página completo mediante:

`s.cookieDomain = window.location.hostname;`

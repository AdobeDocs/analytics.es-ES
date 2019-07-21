---
description: 'null'
seo-description: 'null'
seo-title: PHP
solution: Analytics
subtopic: Notas de la versión
title: PHP
topic: Desarrollador e implementación
uuid: 65 a 644 ef -8 e 50-406 b -8 b 12-0582495 d 130 a
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# PHP{#php}

>[!NOTE]
>
>Para encontrar la versión actual de la biblioteca, active la depuración de registro.

## Versión 1.2.2 {#section_0D547871DC684417B6CE1370E5C6AAC2}

Fecha de versión: **agosto de 2014**

* Cambios internos para admitir próximas funciones.

## Versión 1.2.1 {#section_5717907F67AB482F860F1DFBCB4198C7}

Fecha de versión: **julio de 2012**

* Added a check for the "off" returned for the $_SERVER['HTTPS'] in IIS. Without this check, typecasting to boolean ((bool)$_SERVER['HTTPS']) returned true in IE whether the request was made through HTTP or HTTPS. Esto hizo que páginas no seguras intentasen hacer una solicitud de imagen segura.

## Versión 1.1 {#section_8F4479681ED642FCB9233459E04FF702}

La biblioteca de mediciones para PHP 1.1 incluye las siguientes actualizaciones desde la versión 1.0:

* Mejor precisión en la segmentación geográfica (cuando `sendFromServer` está habilitada).
* Se ha corregido un error para que el usuario ahora pueda anexar a la variable `userAgent`.
* La señalización de imagen es ahora compatible con más exploradores móviles.
* La variable `imageDimensions` ahora establece 5x5 como valor predeterminado cuando la opción móvil está habilitada.
* Lista de detección de bots refinada.
* Se ha agregado información de depuración (encabezados HTTP, respuesta, errores, etc.) cuando `debugTracking` y `sendFromServer` están habilitadas.

* Added the `debugFilename` variable (when `sendFromServer` is enabled).

* The pagename variable defaults to `$_SERVER['SCRIPT_NAME']` when neither `pagename` nor `pageURL` are set.

* Compatibilidad completa con implementaciones CGI de PHP.
* Mejoras de rendimiento.


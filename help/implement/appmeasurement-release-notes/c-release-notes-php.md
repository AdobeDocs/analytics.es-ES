---
description: 'null'
subtopic: Release notes
title: PHP
topic: Developer and implementation
uuid: 65a644ef-8e50-406b-8b12-0582495d130a
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# PHP{#php}

> [!NOTE] Para saber la versión de la biblioteca actual, active los registros de depuración.

## Versión 1.2.2 {#section_0D547871DC684417B6CE1370E5C6AAC2}

Fecha de versión: **agosto de 2014**

* Cambios internos para admitir próximas funciones.

## Versión 1.2.1 {#section_5717907F67AB482F860F1DFBCB4198C7}

Fecha de versión: **julio de 2012**

* Se ha agregado una comprobación para el mensaje de "desactivado" que se devolvió para ['HTTPS'] en IIS. Sin esta comprobación, la colocación en un booleano ((bool)$_SERVER['HTTPS']) devolvió un estado de verdadero en IE, ya se efectuase la solicitud en HTTP o HTTPS. Esto hizo que páginas no seguras intentasen hacer una solicitud de imagen segura.

## Versión 1.1 {#section_8F4479681ED642FCB9233459E04FF702}

La biblioteca de mediciones para PHP 1.1 incluye las siguientes actualizaciones desde la versión 1.0:

* Mejor precisión en la segmentación geográfica (cuando `sendFromServer` está habilitada).
* Se ha corregido un error para que el usuario ahora pueda anexar a la variable `userAgent`.
* La señalización de imagen es ahora compatible con más exploradores móviles.
* La variable `imageDimensions` ahora establece 5x5 como valor predeterminado cuando la opción móvil está habilitada.
* Lista de detección de bots refinada.
* Se ha agregado información de depuración (encabezados HTTP, respuesta, errores, etc.) cuando `debugTracking` y `sendFromServer` están habilitadas.

* Se ha agregado la variable `debugFilename` (cuando `sendFromServer` está habilitada).

* La variable toma `$_SERVER['SCRIPT_NAME']` como valor predeterminado cuando ni el valor `pagename` ni `pageURL` están habilitados.

* Compatibilidad completa con implementaciones CGI de PHP.
* Mejoras de rendimiento.


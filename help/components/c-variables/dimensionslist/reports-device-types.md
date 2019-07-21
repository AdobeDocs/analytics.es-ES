---
description: Agrupa dispositivos móviles en teléfonos móviles, tabletas, lectores electrónicos, consolas de juegos, televisores, receptores de televisión, reproductores multimedia y otras categorías de alto nivel para poder ver la distribución entre tipos de dispositivos móviles.
seo-description: Agrupa dispositivos móviles en teléfonos móviles, tabletas, lectores electrónicos, consolas de juegos, televisores, receptores de televisión, reproductores multimedia y otras categorías de alto nivel para poder ver la distribución entre tipos de dispositivos móviles.
seo-title: Tipos de dispositivos
solution: Analytics
title: Tipos de dispositivos
topic: 'Informes '
uuid: e 1224769-9 a 94-4 cad-a 1 ed-e 285 d 60 d 23 f 3
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Tipos de dispositivos

Agrupa dispositivos móviles en teléfonos móviles, tabletas, lectores electrónicos, consolas de juegos, televisores, receptores de televisión, reproductores multimedia y otras categorías de alto nivel para poder ver la distribución entre tipos de dispositivos móviles.

Esta dimensión también resulta útil para definir segmentos para usuarios de teléfonos y tabletas mediante segmentación donde el tipo de dispositivo móvil es igual a "tipo de dispositivo".

**Datos de dispositivos dinámicos**

Esta dimensión utiliza datos de dispositivos dinámicos que se actualizan constantemente a medida que se anuncian e identifican nuevos dispositivos. Por ejemplo, una nueva tablet que se publique durante el mes en curso podría ser incorrecta porque todavía no existe en la base de datos de dispositivos. Cuando se actualiza la base de datos de dispositivos con un nuevo dispositivo, como resultado, los cambios se aplican a todos los informes de fechas futuras (no a los datos históricos). Por consiguiente, podría ver leves variaciones en este informe para fechas históricas con el transcurso del tiempo. Como regla general, el informe más actual tendrá la fecha más exacta para cualquier período de informe.

Los datos de este informe se rellenan utilizando la cadena agente-usuario.

>[!Note]
>Solo los cambios realizados en un ID móvil existente son retroactivos. Si el dispositivo es nuevo y todavía no tiene un ID móvil, los únicos datos que se conectarán a este dispositivo comienzan en la fecha en que se agrega un ID a la base de datos de dispositivos.
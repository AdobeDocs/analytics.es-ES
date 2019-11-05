---
description: Agrupa dispositivos móviles en teléfonos móviles, tabletas, lectores electrónicos, consolas de juegos, televisores, receptores de televisión, reproductores multimedia y otras categorías de alto nivel para poder ver la distribución entre tipos de dispositivos móviles.
seo-description: Agrupa dispositivos móviles en teléfonos móviles, tabletas, lectores electrónicos, consolas de juegos, televisores, receptores de televisión, reproductores multimedia y otras categorías de alto nivel para poder ver la distribución entre tipos de dispositivos móviles.
seo-title: Tipos de dispositivos
solution: Analytics
title: Tipos de dispositivos
topic: Informes
uuid: e1224769-9a94-4cad-a1ed-e285d60d23f3
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# Tipos de dispositivos

Agrupa dispositivos móviles en teléfonos móviles, tabletas, lectores electrónicos, consolas de juegos, televisores, receptores de televisión, reproductores multimedia y otras categorías de alto nivel para poder ver la distribución entre tipos de dispositivos móviles.

Esta dimensión también es útil para definir segmentos para usuarios de teléfonos y tabletas mediante la segmentación donde Tipo de dispositivo móvil es igual a "tipo de dispositivo".

**Datos de dispositivos dinámicos**

Esta dimensión utiliza datos de dispositivos dinámicos que se actualizan constantemente a medida que se anuncian e identifican nuevos dispositivos. Por ejemplo, una tableta nueva que se libera durante el mes actual podría no identificarse correctamente porque aún no existe en la base de datos del dispositivo. Cuando se actualiza la base de datos de dispositivos con un nuevo dispositivo, como resultado, los cambios se aplican a todos los informes de fechas futuras (no a los datos históricos). Por consiguiente, podría ver leves variaciones en este informe para fechas históricas con el transcurso del tiempo. Como regla general, el informe más actual tendrá la fecha más exacta para cualquier período de informe.

Los datos de este informe se rellenan utilizando la cadena agente-usuario.

>[!Note]
>Solo los cambios realizados en un ID móvil existente son retroactivos. Si el dispositivo es nuevo y aún no tiene un ID móvil, los únicos datos que se vincularán a este dispositivo empezarán en la fecha en que se agregue un ID a la base de datos del dispositivo.

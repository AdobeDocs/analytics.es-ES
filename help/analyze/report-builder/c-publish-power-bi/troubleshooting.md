---
description: Estos son algunos problemas comunes que se producen al utilizar el Creador de informes con Power BI.
seo-description: Estos son algunos problemas comunes que se producen al utilizar el Creador de informes con Power BI.
seo-title: Solución de problemas de integración de Power BI
title: Solución de problemas de integración de Power BI
uuid: c1e7e164-4bc6-4513-9332-92c53be021cc
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Solución de problemas de integración de Power BI

Estos son algunos problemas comunes que se producen al utilizar el Creador de informes con Power BI.

## Paso 1. Failure to publish to Power BI {#section_5B87DC1C302C4FD8AB9E4DD6B162DC9B}

Los libros programados que requieren la publicación en Power BI dependen de los servicios de Power BI para funcionar y ejecutarse. Dos de los principales motivos de error en la publicación son:

* Los servicios de Power BI pueden estar caídos.
* El usuario que programó el libro ya no dispone de credenciales en una cuenta Microsoft válida.

Cada tarea programada del Creador de informes intenta ejecutarse hasta tres veces:

* Tras el primer intento fallido se recibe este mensaje: "No ha sido posible publicar este libro programado en Microsoft Power BI. Se intentará de nuevo en breve."
* Tras el segundo intento fallido no se recibe ningún mensaje.
* Tras el tercer intento fallido se recibe este mensaje: "No ha sido posible publicar este libro en Power BI".

## Paso 2: Broken visualizations in Power BI {#section_FFFE200D06F843B2AF093710FD678166}

Estas son las principales razones que pueden provocar errores en las visualizaciones al publicar en Power BI solicitudes del Creador de informes:

* Se editó una solicitud en el Creador de informes (p. ej., se cambiaron métricas o dimensiones) y después se volvió a publicar en Power BI. Editar las solicitudes puede provocar errores en las visualizaciones.
* Se eliminó una solicitud empleada en una visualización.


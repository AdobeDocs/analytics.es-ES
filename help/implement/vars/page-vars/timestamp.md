---
title: timestamp
description: Establezca manualmente la marca de tiempo de la visita.
translation-type: tm+mt
source-git-commit: f75c6759feb6576017733f1aac5bff2e21d4b0af

---


# timestamp

La `timestamp` variable establece manualmente la marca de tiempo de la visita para los grupos de informes habilitados para la marca de tiempo.

> [!WARNING] No utilice esta variable si el grupo de informes no está configurado explícitamente para aceptar visitas con marca de hora. AppMeasurement establece automáticamente la hora de una visita para los grupos de informes que no admiten visitas con marca de hora. Si envía una visita con esta variable a un grupo de informes que no admite marcas de hora, esos datos se pierden de forma permanente.

## Marca de hora en el lanzamiento de la plataforma Adobe Experience

No hay un campo dedicado en Launch para utilizar esta variable. Utilice el editor de código personalizado, siguiendo la sintaxis de AppMeasurement.

## s.timestamp en el editor de código personalizado AppMeasurement e Launch

La `s.timestamp` variable es una cadena que contiene la fecha y la hora de la visita. Los formatos válidos de marca de hora incluyen [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) y [Unix time](https://en.wikipedia.org/wiki/Unix_time).

```js
// Timestamp using ISO 8601
s.timestamp = "2020-01-01T00:00:00Z";

// Timestamp using Unix timestamp
s.timestamp = "1577836800";

// Automatically get the current Unix timestamp
s.timestamp = Math.round(new Date().getTime()/1000);

// Automatically get the current ISO 8601 timestamp
s.timestamp = new Date().toISOString();
```

## Valores ISO 8601

Las fechas y horas expresadas en [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) pueden adoptar diferentes formas. Adobe no admite todas las funciones de ISO 8601.

* Both the date and time must be provided, separated by `T`.
* Se requieren horas y minutos; segundos son opcionales pero se recomiendan.
* Los días de la semana y las fechas con números ordinales no son compatibles.
* La fecha puede tener un formato estándar o extendido. Por ejemplo, `2020-01-01T00:00:00Z` y `20200101T000000Z` son válidos.
* Los minutos y segundos fraccionales son técnicamente válidos, pero Adobe ignora las fracciones.
* Los husos horarios se admiten en formatos estándar y extendidos.

Los siguientes son valores ISO 8601 válidos en la `timestamp` variable:

```text
2020-01-01T00:00:00+00:00
2020-01-01T00:00:00Z
2020-01-01T00:00:00
2020-01-01T00:00
20200101T000000+0000
20200101T000000Z
20200101T000000
20200101T0000
```

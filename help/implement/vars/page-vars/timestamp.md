---
title: timestamp
description: Establecer manualmente la marca de tiempo de la visita.
translation-type: ht
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: ht
source-wordcount: '243'
ht-degree: 100%

---


# timestamp

La variable `timestamp` establece manualmente la marca de tiempo de la visita en los grupos de informes que tengan habilitada la marca de tiempo.

>[!WARNING]
>
>No utilice esta variable si el grupo de informes no está configurado explícitamente para aceptar visitas con marca de tiempo. AppMeasurement establece automáticamente la hora de una visita en los grupos de informes que no admiten visitas con marca de tiempo. Si envía una visita con esta variable a un grupo de informes que no admita marcas de tiempo, los datos se perderán de forma irreversible.

## Marca de tiempo en Adobe Experience Platform Launch

No hay un campo específico en Launch para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.timestamp en AppMeasurement y el editor de código personalizado de Launch

La variable `s.timestamp` es una cadena que contiene la fecha y la hora de la visita. Los formatos válidos para la marca de tiempo son [ISO 8601](https://es.wikipedia.org/wiki/ISO_8601) y [Unix time](https://es.wikipedia.org/wiki/Tiempo_Unix).

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

Las fechas y horas expresadas de conformidad con la norma [ISO 8601](https://es.wikipedia.org/wiki/ISO_8601) pueden adoptar diferentes formas. Adobe no admite algunas de las formas descritas en la norma ISO 8601.

* La fecha y la hora deben proporcionarse separadas por una `T`.
* Es obligatorio detallar las horas y los minutos; los segundos son opcionales pero se recomiendan.
* Los días de la semana y las fechas con números ordinales no son compatibles.
* La fecha puede tener un formato estándar o extendido. `2020-01-01T00:00:00Z` y `20200101T000000Z` son dos ejemplos válidos.
* Los minutos y segundos fraccionarios son técnicamente válidos, pero Adobe ignora las fracciones.
* Los husos horarios se admiten en formatos estándar y extendidos.

Estos son algunos ejemplos de valores ISO 8601 válidos para la variable `timestamp`:

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

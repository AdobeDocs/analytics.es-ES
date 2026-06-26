---
title: timestamp
description: Establecer manualmente la marca de tiempo de la visita.
feature: Appmeasurement Implementation
exl-id: 9d5ce5ef-2d84-4f65-b2e3-7aa3e219bc34
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/f2r9jWtF5HgCP6jUKg3YnLFxNwx1DiUBI-2Nquy5-K0'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 1ed4ab984231b7c72580c5ae505b1a16c0330c2f
workflow-type: tm+mt
source-wordcount: 304
ht-degree: 67%

---

# timestamp

La variable `timestamp` establece manualmente la marca de tiempo de la visita en los grupos de informes que tengan habilitada la marca de tiempo.

>[!WARNING]
>
>No utilice esta variable si el grupo de informes no está configurado explícitamente para aceptar visitas con marca de tiempo. AppMeasurement establece automáticamente la hora de una visita en los grupos de informes que no admiten visitas con marca de tiempo. Si envía una visita con esta variable a un grupo de informes que no admita marcas de tiempo, los datos se perderán de forma irreversible.

## Marca de tiempo mediante Web SDK

La marca de tiempo está [asignada para Adobe Analytics](/help/implement/aep-edge/xdm-var-mapping.md) en el campo XDM `xdm.timestamp`. Este campo solo admite Tiempo Unix.

## Marca de tiempo con la extensión Adobe Analytics

No hay ningún campo dedicado en la extensión de Adobe Analytics para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.timestamp en AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `s.timestamp` es una cadena que contiene la fecha y la hora de la visita. Los formatos válidos para la marca de tiempo son [ISO 8601](https://datatracker.ietf.org/doc/html/rfc3339#section-5.6) y [Unix time](https://es.wikipedia.org/wiki/Tiempo_Unix) en segundos.

```js
// Timestamp using ISO 8601
s.timestamp = "2026-01-01T00:00:00Z";

// Timestamp using Unix timestamp
s.timestamp = "1577836800";

// Automatically get the current Unix timestamp
s.timestamp = Math.round(new Date().getTime()/1000);

// Automatically get the current ISO 8601 timestamp
s.timestamp = new Date().toISOString();
```

## Valores ISO 8601

Las fechas y horas expresadas de conformidad con la norma [ISO 8601](https://datatracker.ietf.org/doc/html/rfc3339#section-5.6) pueden adoptar diferentes formas. Adobe no admite algunas de las formas descritas en la norma ISO 8601.

* La fecha y la hora deben proporcionarse separadas por una `T`.
* Es obligatorio detallar las horas y los minutos; los segundos son opcionales pero se recomiendan.
* Los días de la semana y las fechas con números ordinales no son compatibles.
* La fecha puede tener un formato estándar o extendido. `2026-01-01T00:00:00Z` y `20260101T000000Z` son dos ejemplos válidos.
* Los minutos y segundos fraccionarios son técnicamente válidos, pero las fracciones se omiten. Adobe Analytics admite marcas de tiempo con una precisión de solo segundo nivel. Si la precisión de milisegundos es una prioridad para su organización, considere la posibilidad de utilizar Customer Journey Analytics.
* Los husos horarios se admiten en formatos estándar y extendidos.

Estos son algunos ejemplos de valores ISO 8601 válidos para la variable `timestamp`:

```text
2026-01-01T00:00:00+00:00
2026-01-01T00:00:00Z
2026-01-01T00:00:00
2026-01-01T00:00
20260101T000000+0000
20260101T000000Z
20260101T000000
20260101T0000
```

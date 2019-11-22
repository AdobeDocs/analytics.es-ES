---
description: Las variables de página rellenan directamente un informe, como pageName, Props de lista, Variables de lista, etc.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Variables de página
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 47291fb3d55ab3eb5ef181770bf2078c7ea55bc4

---


# timestamp

Esta variable permite personalizar la marca de tiempo de una visita de forma similar a las bibliotecas de AppMeasurement para otras plataformas.


<!-- 

timestamp.xml

 -->

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| 4 bytes | Fecha/Hora | No se notifica directamente. | Configurado por los servidores de recopilación de datos. |

**Sintaxis** {#section_1DF752B1202C4412A301AC7CC10874DF}

```js
s.timestamp="UNIX or ISO-8601 format timestamp"
```

La variable *`timestamp`* debe tener el formato que se describe en la sección siguiente.

>[!IMPORTANT]
>
>Para poder usar la variable *`timestamp`*, el servicio de Atención al cliente debe habilitarla para el grupo de informes. Una vez habilitada, deberá establecerse de forma manual una marca de tiempo para todas las visitas que se envíen al grupo de informes desde JavaScript (con *`s.timestamp`*). De no hacerlo así, las visitas no se registrarán.
>
>Asimismo, si habilita la compatibilidad con la marca de tiempo en un grupo de informes de modo que se admita el seguimiento sin conexión, también deberá establecerse de forma manual una marca de tiempo para todas las visitas que se envíen a este grupo de informes desde JavaScript (con *`s.timestamp`*). No es posible enviar visitas con y sin marca de tiempo a un mismo grupo de informes.
>
>También se puede usar el ajuste [Marcas de hora opcionales](/help/implement/js-implementation/timestamps-overview.md) para combinar datos con y sin marca de tiempo en el mismo grupo de informes global, enviar datos con marca de tiempo desde una aplicación móvil a un grupo de informes global, y actualizar aplicaciones para emplear marcas de tiempo sin tener que crear un nuevo grupo de informes.

**Formatos de las marcas de tiempo** {#section_C12CBCECCD7047D38EF63A5800761CE9}

Las marcas de tiempo deben tener el formato UNIX (segundos transcurridos desde el 1 de enero de 1970) o ISO-8601, con las siguientes restricciones para el formato ISO-8601 aceptado:

* La fecha y la hora deben proporcionarse separadas por una "T".
* La fecha debe ser una fecha de calendario con precisión completa (año, mes y día). . Los días de la semana y las fechas con números ordinales no son compatibles.
* La fecha puede mostrarse en formato estándar o en formato extendido (`YYYY-MM-DD` o `YYYYMMDD`), pero debe incluir las horas y los minutos. Los segundos son opcionales (`HH:MM`, `HH:MM:SS`, `HHMM`o `HHMMSS`). Los minutos y los segundos fraccionados se pueden incluir, pero la parte fraccionada se ignorará.

* Se puede especificar un huso horario opcional en formato estándar o extendido (`±HH`, `±HH:MM`, `±HH`, `±HHMM` o Z)

Las marcas de tiempo UNIX siguen siendo compatibles (segundos transcurridos desde el 1 de enero de 1970).

**Ejemplos** {#section_FA19C53D70DE4CF2AF259A5B968B84C3}

```js
s.timestamp=Math.round((new Date()).getTime()/1000);
```

```js
s.timestamp="2012-04-20T12:49:31-0700";
```

La siguiente lista contiene ejemplos de marcas de tiempo con el formato ISO-8601 válidas:

```
2013-01-01T12:30:05+06:00 
2013-01-01T12:30:05Z 
2013-01-01T12:30:05 
2013-01-01T12:30
```

**Parámetros de configuración** {#section_5275D206F2CB4009B3681E8C4457124A}

El Servicio de atención al cliente debe habilitar un grupo de informes para que acepte marcas de tiempo personalizadas antes de poder usar esta variable. Una vez habilitadas las marcas de tiempo personalizadas, todas las visitas que se envíen al grupo de informes deben contener una marca de tiempo o descartarse.

**Problemas, preguntas y consejos** {#section_EFDE8F67D13C4775A461E0B00D30AFD7}

* Las marcas de tiempo se usan principalmente para realizar el seguimiento de datos sin conexión en plataformas móviles. Las marcas de tiempo personalizadas suelen estar deshabilitadas a menos que estén recopilando datos de aplicaciones web y sin conexión en el mismo grupo de informes.
* Los datos se marcan con la hora cuando los datos sin conexión están activados en el SDK móvil (configuración predeterminada) o cuando se configura un grupo de informes para aceptar datos con marca de hora. Los datos recopilados sin conexión pueden enviarse horas o semanas después de la fecha en que se produjo el evento originalmente. Puede que estas visitas se mantengan en cola en la plataforma Analytics durante más minutos u horas que las visitas sin marca de tiempo:

   * Para los datos con marca de hora enviados en tiempo muy cercano al actual, el retraso probable es de 10 a 15 minutos.
   * Para los datos con marca de hora enviados desde ayer, el retraso probable es de aproximadamente 2 horas.
   * Para los datos con marca de hora que se envían con una antigüedad mayor que ayer, cada día agrega unas 2 horas de retraso, hasta un máximo de 48 horas.


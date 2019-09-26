---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Implementación de análisis
seo-description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
solution: null
title: Variables dinámicas
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.linkTrackEvents

The  variable is a comma-separated list of events that are sent with a [!UICONTROL custom], [!UICONTROL exit], or [!UICONTROL download] link.

If an event is not in *`linkTrackEvents`*, it is not sent to [!DNL Analytics], even if it is populated in the [!UICONTROL onClick] event of a link, as shown in the following example:

```js
s.linkTrackVars="events" 
s.events="event1,event2" 
s.t() // both event1 and event2 are recorded 
<a href="help.php" onClick="s=s_gi('rs1');s.tl(this,'o')">event1 is recorded</a> 
<a href="test.php" onClick="s=s_gi('rs1');s.events='event2';s.tl(this,'o')">No events are recorded</a> 
```

En el primer vínculo a [!DNL help.php], observe que la variable events retiene el valor que se configuró antes de hacer clic en el vínculo. Esto permite enviar event1 con el vínculo personalizado. In the second example, the link to [!DNL test.php], event2 is not recorded because it is not listed in *`linkTrackEvents`*.

Para evitar confusiones y posibles problemas, Adobe recomienda rellenar *`linkTrackVars`* y *`linkTrackEvents`* en el evento [!UICONTROL onClick] de un vínculo que se utiliza para el seguimiento de vínculos.

The *`linkTrackEvents`* variable contains the events that should be sent with [!UICONTROL custom], [!UICONTROL download], and [!UICONTROL exit] links. Esta variable solo se considera si *`linkTrackVars`* contiene "events".

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | N.D. | Conversión | "None" |

## Sintaxis y valores posibles

La sintaxis de la variable *`linkTrackEvents`* es una lista de eventos separados por coma (sin espacios).

```js
s.linkTrackEvents="event1[,event2[,event3[...]]]"
```

Solo se permiten nombres de evento en *`linkTrackEvents`*. These events are listed in [Events](https://docs.adobe.com/content/help/en/analytics/implementation/analytics-basics/ref-events.html). Si aparece un espacio antes o después del nombre de evento, el evento no se puede enviar con ninguna solicitud de imagen de vínculo.

## Ejemplos

```js
s.linkTrackEvents="purchase,event1"
```

```js
s.linkTrackEvents="scAdd,scCheckout,purchase,event14"
```

## Parámetros de configuración

Ninguno.

## Problemas, preguntas y consejos

* El archivo JavaScript solo usa *`linkTrackEvents`* si *`linkTrackVars`* contiene la variable "events". "events" debe incluirse en *`linkTrackVars`* solo cuando *`linkTrackEvents`* se defina.

* Beware if an event is fired on a page, and is listed in *`linkTrackEvents`*. That event is recorded again with any [!UICONTROL exit], [!UICONTROL download], or [!UICONTROL custom] links unless the events variable is reset prior to that event (in the [!UICONTROL onClick] of a link or after the call to the *`t()`* function).

* If *`linkTrackEvents`* contains spaces between event names, the events are not recorded.

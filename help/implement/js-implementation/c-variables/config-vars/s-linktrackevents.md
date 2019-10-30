---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Implementación de Analytics
seo-description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
solution: null
title: Variables dinámicas
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# s.linkTrackEvents

La variable es una lista de eventos separados por comas que se envían con un vínculo [!UICONTROL personalizado], [!UICONTROL de salida], o [!UICONTROL de descarga].

Si el evento no aparece en *`linkTrackEvents`*, no se envía a [!DNL Analytics], aunque esté relleno en el evento [!UICONTROL onClick] de un vínculo, como se muestra en el ejemplo siguiente:

```js
s.linkTrackVars="events" 
s.events="event1,event2" 
s.t() // both event1 and event2 are recorded 
<a href="help.php" onClick="s=s_gi('rs1');s.tl(this,'o')">event1 is recorded</a> 
<a href="test.php" onClick="s=s_gi('rs1');s.events='event2';s.tl(this,'o')">No events are recorded</a> 
```

En el primer vínculo a [!DNL help.php], observe que la variable de eventos retiene el valor que se configuró antes de hacer clic en el vínculo. Esto permite enviar event1 con el vínculo personalizado. En el segundo ejemplo, el vínculo a [!DNL test.php], event2 no se registra porque no está en la lista de *`linkTrackEvents`*.

Para evitar confusiones y posibles problemas, se recomienda rellenar *`linkTrackVars`* y *`linkTrackEvents`* en el evento [!UICONTROL onClick] de un vínculo que se utiliza para el seguimiento de vínculos.

La variable *`linkTrackEvents`* contiene los eventos que deben enviarse con los vínculos [!UICONTROL personalizados], de [!UICONTROL descarga] y de [!UICONTROL salida]. Esta variable solo se tiene en cuenta si *`linkTrackVars`* contiene “events”.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | N.D. | Conversión | "Ninguna" |

## Sintaxis y valores posibles

La variable *`linkTrackEvents`* es una lista de eventos separados por comas (sin espacios).

```js
s.linkTrackEvents="event1[,event2[,event3[...]]]"
```

Solo se permiten nombres de evento en *`linkTrackEvents`*. Estos eventos se incluyen en [Eventos](https://docs.adobe.com/content/help/en/analytics/implementation/analytics-basics/ref-events.html). Si aparece un espacio antes o después del nombre de evento, el evento no se puede enviar con ninguna solicitud de imagen de vínculo.

## Ejemplos

```js
s.linkTrackEvents="purchase,event1"
```

```js
s.linkTrackEvents="scAdd,scCheckout,purchase,event14"
```

## Parámetros de configuración

Ninguna

## Problemas, preguntas y consejos

* El archivo JavaScript solo utiliza *`linkTrackEvents`* si *`linkTrackVars`* contiene la variable “events”. “events” debe incluirse en *`linkTrackVars`* solo cuando *`linkTrackEvents`* se defina.

* Tenga cuidado si se activa un evento en una página y está incluido en *`linkTrackEvents`*. Ese evento se registra de nuevo con los vínculos de [!UICONTROL salida], [!UICONTROL descarga] o [!UICONTROL personalizados] a menos que la variable de eventos se restablezca antes de dicho evento (en el evento [!UICONTROL onClick] de un vínculo o después de la llamada a la función *`t()`*).

* Si *`linkTrackEvents`* contiene espacios entre los nombres de evento, los eventos no se registran.

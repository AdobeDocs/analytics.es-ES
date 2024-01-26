---
title: getTimeBetweenEvents
description: Mida el tiempo entre dos eventos.
feature: Variables
exl-id: 15887796-4fe4-4b3a-9a65-a4672c5ecb34
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '786'
ht-degree: 91%

---

# Complemento de Adobe: getTimeBetweenEvents

{{plug-in}}

El complemento `getTimeBetweenEvents` le permite realizar un seguimiento del tiempo entre dos eventos de Analytics cualesquiera, incluidos el carro de compras y los eventos personalizados. Resulta útil para rastrear el tiempo que tarda un proceso de pago en completarse o cualquier otro proceso que desee medir. Este complemento no es necesario si no tiene ningún proceso de conversión cuya duración desee medir.

## Instalación del complemento con el SDK web o la extensión del SDK web

Este complemento aún no es compatible con el SDK web.

## Instalación del complemento con la extensión de Adobe Analytics

Adobe ofrece una extensión que le permite utilizar los complementos más utilizados con Adobe Analytics.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad de etiquetas deseada.
1. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Catálogo].
1. Instalación y publicación de la extensión [!UICONTROL Common Analytics Plugins].
1. Si aún no lo ha hecho, cree una regla con la etiqueta “Inicializar complementos” con la siguiente configuración:
   * Condición: Ninguna
   * Evento: Core – Biblioteca cargada (Principio de página)
1. Añada una acción a la regla anterior con la siguiente configuración:
   * Extensión: Common Analytics Plugins
   * Tipo de acción: Inicializar getTimeBetweenEvents
1. Guarde y publique los cambios en la regla.

## Instalación del complemento con el editor de código personalizado de 

Si no desea utilizar la extensión de complemento Common Analytics Plugins, puede utilizar el editor de código personalizado.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad deseada.
1. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón **[!UICONTROL Configurar]** en la extensión de Adobe Analytics.
1. Expanda [!UICONTROL Configurar seguimiento con el código personalizado], que muestra el botón [!UICONTROL Abrir editor].
1. Abra el editor de código personalizado y pegue el código del complemento que se proporciona a continuación en la ventana de edición.
1. Guarde y publique los cambios en la extensión de Analytics.

## Instalación del complemento con AppMeasurement

Copie y pegue el siguiente código en cualquier parte del archivo AppMeasurement después de crear una instancia del objeto de seguimiento de Analytics (con [`s_gi`](../functions/s-gi.md)). Conservar los comentarios y los números de versión del código en la implementación ayuda a Adobe a solucionar cualquier posible problema.

```js
/* Adobe Consulting Plugin: getTimeBetweenEvents v3.0 (AppMeasurement highly recommended) */
function getTimeBetweenEvents(ste,rt,stp,res,cn,etd,fmt,bml,rte){var v=ste,B=rt,x=stp,C=res,k=cn,m=etd,E=fmt,F=bml,p=rte;if("-v"===v)return{plugin:"getTimeBetweenEvents",version:"3.0"};var q=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();if("undefined"!==typeof q&&(q.contextData.getTimeBetweenEvents="3.0",window.cookieWrite=window.cookieWrite||function(c,b,d){if("string"===typeof c){var n=window.location.hostname,f=window.location.hostname.split(".").length-1;if(n&&!/^[0-9.]+$/.test(n)){f=2<f?f:2;var l=n.lastIndexOf(".");if(0<=l){for(;0<=l&&1<f;)l=n.lastIndexOf(".",l-1),f--;l=0<l?n.substring(l):n}}g=l;b="undefined"!==typeof b?""+b:"";if(d||""===b)if(""===b&&(d=-60),"number"===typeof d){var e=new Date;e.setTime(e.getTime()+6E4*d)}else e=d;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(d?" expires="+e.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof window.cookieRead)?window.cookieRead(c)===b:!1}},window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,d=b.indexOf(" "+c+"="),e=0>d?d:b.indexOf(";",d);return(c=0>d?"":decodeURIComponent(b.substring(d+2+c.length,0>e?b.length:e)))?c:""},window.formatTime=window.formatTime||function(c,b,d){function e(b,d,c,e){if("string"!==typeof d)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==e&&d===b[c]||d.toLowerCase()===b[c].toLowerCase())return!0;return!1}if(!("undefined"===typeof c||isNaN(c)||0>Number(c))){var f="";"string"===typeof b&&"d"===b||("string"!==typeof b||!e("h,m,s",b))&&86400<=c?(b=86400,f="days",d=isNaN(d)?1:b/(d*b)):"string"===typeof b&&"h"===b||("string"!==typeof b||!e("m,s",b))&&3600<=c?(b=3600,f="hours",d=isNaN(d)?4:b/(d*b)):"string"===typeof b&&"m"===b||("string"!==typeof b||!e("s",b))&&60<=c?(b=60,f="minutes",d=isNaN(d)?2:b/(d*b)):(b=1,f="seconds",d=isNaN(d)?.2:b/d);f=Math.round(c*d/b)/d+" "+f;0===f.indexOf("1 ")&&(f=f.substring(0,f.length-1));return f}},window.inList=window.inList||function(c,b,d,e){if("string"!==typeof b)return!1;if("string"===typeof c)c=c.split(d||",");else if("object"!==typeof c)return!1;d=0;for(a=c.length;d<a;d++)if(1==e&&b===c[d]||b.toLowerCase()===c[d].toLowerCase())return!0;return!1},"string"===typeof v&&"undefined"!==typeof B&&"string"===typeof x&&"undefined"!==typeof C)){k=k?k:"s_tbe";m=isNaN(m)?1:Number(m);var r=!1,t=!1,y=v.split(","),z=x.split(",");p=p?p.split(","):[];for(var u=window.cookieRead(k),w,D=new Date,A=D.getTime(),h=new Date,e=0;e<p.length;++e)if(window.inList(q.events,p[e])){h.setDate(h.getDate()-1);window.cookieWrite(k,"",h);return}h.setTime(h.getTime()+864E5*m);for(e=0;e<y.length&&!r&&(r=window.inList(q.events,y[e]),!0!==r);++e);for(e=0;e<z.length&&!t&&(t=window.inList(q.events,z[e]),!0!==t);++e);1===y.length&&1===z.length&&v===x&&r&&t?(u&&(w=(A-u)/1E3),window.cookieWrite(k,A,m?h:0)):(!r||1!=B&&u||window.cookieWrite(k,A,m?h:0),t&&u&&(w=(D.getTime()-u)/1E3,!0===C&&(h.setDate(h.getDate()-1),window.cookieWrite(k,"",h))));return w?window.formatTime(w,E,F):""}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Uso del complemento

La función `getTimeBetweenEvents` utiliza los siguientes argumentos:

* **`ste`** (obligatorio, cadena): Iniciar eventos de temporizador. Una cadena delimitada por comas de eventos de Analytics para “iniciar el temporizador”.
* **`rt`** (obligatorio, booleano): Reiniciar la opción del temporizador. Se establece en `true` si desea reiniciar el temporizador cada vez que la variable `events` contenga un evento que arranque el temporizador. Se establece en `false` si no desea que el temporizador se reinicie cuando identifique un evento que arranque el temporizador.
* **`stp`** (obligatorio, cadena): Detener los eventos de temporizador. Cadena delimitada por comas de eventos de Analytics que “detienen el temporizador”.
* **`res`** (obligatorio, booleano): Opción restablecer temporizador. Configúrelo en `true` si desea registrar el tiempo desde que se inició el temporizador Y restablézcalo después de que se detenga. Configúrelo en `false` si desea registrar la hora pero no detener el temporizador. Si se establece en `false`, el temporizador continúa ejecutándose después de que la variable de eventos registre un evento de parada.

  >[!TIP]
  >
  >Si establece este argumento en `false`, se recomienda encarecidamente que configure el siguiente argumento `rte`.
* **`cn`** (opcional, cadena): El nombre de la cookie en la que se almacena la hora del primer evento. El valor predeterminado es `"s_tbe"`.
* **`etd`** (opcional, entero): El tiempo de caducidad de la cookie en días. Configúrelo en `0` para que caduque al terminar la sesión del explorador. Si no se configura de forma distinta, el valor predeterminado es 1 día.
* **`fmt`** (opcional, cadena): El formato del tiempo en el que se devuelve el número de segundos (el valor predeterminado es nada)
   * `"s"` para los segundos
   * `"m"` para los minutos
   * `"h"` para las horas
   * `"d"` para los días
   * Si no se establece, el formato del valor devuelto se basa en las siguientes reglas:
      * Cualquier valor inferior a un minuto se redondea a la referencia de 5 segundos más cercana. Por ejemplo: 10 segundos, 15 segundos
      * Cualquier valor entre un minuto y una hora se redondea a la referencia de 1/2 minuto más cercana. Por ejemplo, 30,5 minutos, 31 minutos
      * Cualquier valor entre una hora y un día se redondea a la referencia de cuarto de hora más cercana. Por ejemplo, 2,25 horas, 3,5 horas
      * Cualquier valor mayor que un día se redondea a la referencia del día más próximo. Por ejemplo: 1 día, 3 días, 9 días
* **`bml`** (opcional, número): La duración de la referencia de redondeo según el formato del argumento `fmt`. Por ejemplo, si el argumento `fmt` es `"s"` y este argumento es `2`, el valor devuelto se redondea a la referencia de 2 segundos más cercana. Si el argumento `fmt` es `"m"` y este argumento es `0.5`, el valor devuelto se redondea a la referencia de medio minuto más cercana.
* **`rte`** (opcional, cadena): La cadena delimitada por comas de eventos de Analytics que anulan o eliminan el temporizador. No tiene valor predeterminado.

La llamada a esta función hace que se devuelva un entero que representa el tiempo entre el evento de inicio del temporizador y el evento de fin del temporizador en el formato deseado.

## Llamadas de ejemplo

```js
// The timer starts or restarts when the events variable contains event1
// The timer stops and resets when the events variable contains event2
// The timer resets when the events variable contains event3 or the visitor closes their browser
// Sets eVar1 to the number of seconds between event1 and event2, rounded to the nearest 2-second benchmark
s.eVar1 = getTimeBetweenEvents("event1", true, "event2", true, "", 0, "s", 2, "event3");

// The timer starts when the events variable contains event1. It does NOT restart with subsequent hits that also contain event1
// The timer records a "lap" when the events variable contains event2. It does not stop the timer.
// The timer resets when the events variable contains event3 or if more than 20 days pass since the timer started
// The timer is stored in a cookie labeled "s_20"
// Sets eVar4 to the number of hours between event1 and event2, rounded to the nearest 90-minute benchmark
s.eVar4 = getTimeBetweenEvents("event1", false, "event2", false, "s_20", 20, "h", 1.5, "event3");

// Similar to the above timer in eVar4, except the return value is returned in seconds/minutes/hours/days depending on the timer length.
// The timer expires after 1 day.
s.eVar4 = getTimeBetweenEvents("event1", true, "event2", true);
```

## Historial de versiones

### 3.0 (19 de marzo de 2021)

* Se ha añadido el número de versión como datos de contexto.

### 2.1 (26 de mayo de 2018)

* Incorpora los cambios realizados a la nueva versión del complemento `formatTime`.

### 2.0 (6 de abril de 2018)

* Reescritura/reanálisis completo del complemento.

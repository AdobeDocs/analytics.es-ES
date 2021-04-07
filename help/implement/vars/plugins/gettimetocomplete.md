---
title: getTimeToComplete
description: Mida el tiempo que se tarda en completar una tarea.
translation-type: ht
source-git-commit: 37a3a44053260d9cdb2a3797e07f6d34592abc1f
workflow-type: ht
source-wordcount: '762'
ht-degree: 100%

---


# Complemento de Adobe: getTimeToComplete

>[!IMPORTANT]
>
>Adobe Consulting proporciona este complemento por cortesía para ayudarle a sacar el máximo partido a Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica con este complemento, incluida la instalación o solución de problemas. Si necesita ayuda con este complemento, póngase en contacto con el administrador de cuentas de su organización. Ellos podrán organizar una reunión con un consultor para ayudarle.

El complemento `getTimeToComplete` rastrea el tiempo que un usuario tarda en completar un proceso en un sitio. El “reloj” comienza cuando se llama a la acción `start` y finaliza cuando se llama a la acción `stop`. Adobe recomienda utilizar este complemento si hay un flujo de trabajo en el sitio que lleve cierto tiempo completar y si desea saber cuánto tiempo tardan los visitantes en completarlo. No es necesario utilizar este complemento si el flujo de trabajo del sitio lleva un breve periodo de tiempo (menos de 3 segundos) porque la granularidad solo se reduce al segundo completo.

## Instalación del complemento con la extensión de Adobe Experience Platform Launch

Adobe ofrece una extensión que le permite disfrutar de los complementos más utilizados.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad deseada.
1. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Catálogo].
1. Instalación y publicación de la extensión [!UICONTROL Common Analytics Plugins].
1. Si aún no lo ha hecho, cree una regla con la etiqueta “Inicializar complementos” con la siguiente configuración:
   * Condición: Ninguna
   * Evento: Core – Biblioteca cargada (Principio de página)
1. Añada una acción a la regla anterior con la siguiente configuración:
   * Extensión: Common Analytics Plugins
   * Tipo de acción: Inicializar getTimeToComplete
1. Guarde y publique los cambios en la regla.

## Instalación del complemento con el editor de código personalizado de Launch

Si no desea utilizar la extensión del complemento, puede utilizar el editor de código personalizado.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad deseada.
1. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Configurar] en la extensión de Adobe Analytics.
1. Expanda [!UICONTROL Configurar seguimiento con el código personalizado], que muestra el botón [!UICONTROL Abrir editor].
1. Abra el editor de código personalizado y pegue el código del complemento que se proporciona a continuación en la ventana de edición.
1. Guarde y publique los cambios en la extensión de Analytics.

## Instalación del complemento con AppMeasurement

Copie y pegue el siguiente código en cualquier parte del archivo AppMeasurement después de crear una instancia del objeto de seguimiento de Analytics (con [`s_gi`](../functions/s-gi.md)). Conservar los comentarios y los números de versión del código en la implementación ayuda a Adobe a solucionar cualquier posible problema.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getTimeToComplete v4.0 */
function getTimeToComplete(sos,cn,exp,tp){var f=sos,m=cn,l=exp,e=tp;if("-v"===f)return{plugin:"getTimeToComplete",version:"4.0"};var k=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof k&&(k.contextData.getTimeToComplete="4.0");window.formatTime=window.formatTime||function(c,b,d){function e(b,d,c,e){if("string"!==typeof d)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==e&&d===b[c]||d.toLowerCase()===b[c].toLowerCase())return!0;return!1}if(!("undefined"===typeof c||isNaN(c)||0>Number(c))){var h="";"string"===typeof b&&"d"===b||("string"!==typeof b||!e("h,m,s",b))&&86400<=c?(b=86400,h="days",d=isNaN(d)?1:b/(d*b)):"string"===typeof b&&"h"===b||("string"!==typeof b||!e("m,s",b))&&3600<=c?(b=3600,h="hours",d=isNaN(d)?4:b/(d*b)):"string"===typeof b&&"m"===b||("string"!==typeof b||!e("s",b))&&60<=c?(b=60,h="minutes",d=isNaN(d)?2:b/(d*b)):(b=1,h="seconds",d=isNaN(d)?.2:b/d);h=Math.round(c*d/b)/d+" "+h;0===h.indexOf("1 ")&&(h=h.substring(0,h.length-1));return h}};window.cookieWrite=window.cookieWrite||function(c,b,d){if("string"===typeof c){var e=window.location.hostname,h=window.location.hostname.split(".").length-1;if(e&&!/^[0-9.]+$/.test(e)){h=2<h?h:2;var f=e.lastIndexOf(".");if(0<=f){for(;0<=f&&1<h;)f=e.lastIndexOf(".",f-1),h--;f=0<f?e.substring(f):e}}g=f;b="undefined"!==typeof b?""+b:"";if(d||""===b)if(""===b&&(d=-60),"number"===typeof d){var k=new Date;k.setTime(k.getTime()+6E4*d)}else k=d;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(d?" expires="+k.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,d=b.indexOf(" "+c+"="),e=0>d?d:b.indexOf(";",d);return(c=0>d?"":decodeURIComponent(b.substring(d+2+c.length,0>e?b.length:e)))?c:""};f=f?f.toLowerCase():"start";if("stop"===f||"start"===f){m=m?m:"s_gttc";e?e="d"===e?864E5:"h"===e?36E5:"s"===e?1E3:6E4:(l=30,e=6E4);l=isNaN(l)?30:l;l*=e;k=cookieRead(m);e=new Date;if("stop"===f&&k)return l=Math.round((e.getTime()-k)/1E3),cookieWrite(m,"",0),formatTime(l);"start"!==f||k?k&&Number(k)<e.getTime()+18E5&&cookieWrite(m,k,30):(f=String(e.getTime()),e.setTime(e.getTime()+l),cookieWrite(m,f,e))}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Uso del complemento

El método `getTimeToComplete` utiliza los siguientes argumentos:

* **`sos`** (opcional, cadena): Configúrelo en `"start"` cuando desee iniciar el temporizador. Configúrelo en `"stop"` cuando desee detener el temporizador. El valor predeterminado es `"start"`.
* **`cn`** (opcional, cadena): El nombre de la cookie para almacenar la hora de inicio. El valor predeterminado es `"s_gttc"`.
* **`exp`** (opcional, entero): El número de días en que caduca la cookie (y el temporizador). El valor predeterminado es `0`, que representa el final de la sesión del explorador.

Llamar a este método devuelve una cadena que contiene el número de días, horas, minutos y/o segundos que transcurridos entre la acción `"start"` y `"stop"`.

## Llamadas de ejemplo

### Ejemplo 1

Utilice estas llamadas para determinar el tiempo que transcurre entre el momento en que un visitante inicia el proceso de cierre de compra y el momento en que realiza una compra.

Inicie el temporizador cuando el visitante inicie el cierre de compra:

```js
if(s.events.indexOf("scCheckout") > -1) s.getTimeToComplete("start");
```

Detenga el temporizador cuando el visitante realice la compra y configure prop1 en la diferencia horaria entre la detención y el inicio:

```js
if(s.events.indexOf("purchase") > -1) s.prop1 = s.getTimeToComplete("stop");
```

s.prop1 registrará el tiempo necesario para completar el proceso de compra

### Ejemplo 2

Si desea que varios temporizadores se ejecuten al mismo tiempo (para medir diferentes procesos), deberá configurar manualmente el argumento de cookie cn.  Por ejemplo: Si desea medir el tiempo necesario para completar una compra, debe establecer el siguiente código...

```javascript
if(s.inList(s.events, "scCheckout")) s.getTimeToComplete("start", "gttcpurchase");
if(s.inList(s.events, "purchase")) s.prop1 = s.getTimeToComplete("start", "gttcpurchase");
```

...pero si también desea medir (a la vez) el tiempo necesario para rellenar un formulario de registro, también debe ejecutar el siguiente código:

```js
if(s.inList(s.events, "event1")) s.getTimeToComplete("start", "gttcregister", 7);
if(s.inList(s.events, "event2")) s.prop2 = s.getTimeToComplete("stop", "gttcregister", 7);
```

En el segundo ejemplo, event1 tiene el propósito de registrar el inicio de un proceso de registro que, por cualquier razón, puede llevar hasta 7 días completar y event2 tiene el propósito de capturar la finalización del registro.  s.prop2 registrará el tiempo necesario para completar el proceso de registro

## Historial de versiones

### 4.0 (19 de marzo de 2021)

* Se ha añadido el número de versión como datos de contexto.

### 3.1 (30 de septiembre de 2019)

* Se ha añadido una lógica que requiere un valor de “start” o “stop” en el primer argumento.  El resto de valores pasados detienen la ejecución del complemento.
* Se ha actualizado el complemento `inList 2.0` a `inList 2.1`.

### 3.0 (23 de agosto de 2018)

* Se ha actualizado el complemento `formatTime v1.0` a `formatTime v1.1`.

### 3.0 (17 de abril de 2018)

* Versión puntual (compilada de nuevo, con un tamaño de código más pequeño).
* Se han corregido errores menores.

### 2.0 (21 de junio de 2016)

* Se ha eliminado la dependencia del complemento `p_fo`.
* Se ha agregado compatibilidad con el código H y con AppMeasurement.
* Se ha agregado el registro de la consola.

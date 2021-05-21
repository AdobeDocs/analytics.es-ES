---
title: getVisitDuration
description: Rastree cuánto tiempo ha pasado un visitante en el sitio hasta el momento.
exl-id: 5299caa8-1e47-40b0-a8f4-422590f33ee4
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '585'
ht-degree: 100%

---

# Complemento de Adobe: getVisitDuration

>[!IMPORTANT]
>
>Adobe Consulting proporciona este complemento por cortesía para ayudarle a sacar el máximo partido a Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica con este complemento, incluida la instalación o solución de problemas. Si necesita ayuda con este complemento, póngase en contacto con el administrador de cuentas de su organización. Ellos podrán organizar una reunión con un consultor para ayudarle.

El complemento `getVisitDuration` rastrea el tiempo en minutos que el visitante ha pasado en el sitio hasta ese momento. Adobe recomienda utilizar este complemento si desea rastrear el tiempo acumulado en el sitio hasta ese momento o para rastrear el tiempo que tarda en realizar una actividad. Este complemento no rastrea el tiempo entre eventos; si desea esta funcionalidad, utilice el complemento [`getTimeBetweenEvents`](gettimebetweenevents.md).

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
   * Tipo de acción: Inicializar getVisitDuration
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
/* Adobe Consulting Plugin: getVisitDuration v2.1 */
function getVisitDuration(){if(arguments&&"-v"===arguments[0])return{plugin:"getVisitDuration",version:"2.1"};var d=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof d&&(d.contextData.getVisitDuration="2.1");window.cookieWrite=window.cookieWrite||function(c,b,f){if("string"===typeof c){var h=window.location.hostname,a=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){a=2<a?a:2;var e=h.lastIndexOf(".");if(0<=e){for(;0<=e&&1<a;)e=h.lastIndexOf(".",e-1),a--;e=0<e?h.substring(e):h}}g=e;b="undefined"!==typeof b?""+b:"";if(f||""===b)if(""===b&&(f=-60),"number"===typeof f){var d=new Date;d.setTime(d.getTime()+6E4*f)}else d=f;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(f?" expires="+d.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};d=(new Date).getTime();var k=cookieRead("s_dur"),a=0;if(isNaN(k)||18E5<d-k)k=d;a=d-k;cookieWrite("s_dur",k+"",30);if(0===a)return"first hit of visit";a=Math.floor(a/6E4);return 0===a?"less than a minute":1===a?"1 minute":a+" minutes"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Uso del complemento

El método `getVisitDuration` no utiliza ningún argumento. Devuelve uno de los siguientes valores:

* `"first hit of visit"`
* `"less than a minute"`
* `"1 minute"`
* `"[x] minutes"` (donde `[x]` es el número de minutos transcurridos desde que el visitante accedió al sitio)

Este complemento crea una cookie de origen llamada `"s_dur"`, que es el número de milisegundos transcurridos desde que el visitante accedió al sitio. La cookie caduca tras 30 minutos de inactividad.

## Llamadas de ejemplo

### Ejemplo 1

El siguiente código...

```js
s.eVar10 = s.getVisitDuration();
```

...siempre establecerá eVar10 en el número de minutos transcurridos desde que el visitante accedió al sitio.

### Ejemplo 2

El siguiente código...

```js
if(s.inList(s.events, "purchase")) s.eVar10 = s.getVisitDuration();
```

...utiliza el complemento inList para comprobar si la variable de eventos contiene el evento de compra.  Si es así, eVar10 se establece en el número de minutos entre el inicio de la visita y la hora de compra.

### Ejemplo 3

El siguiente código...

```js
s.prop10 = s.getVisitDuration();
```

...siempre establecerá prop10 en el número de minutos transcurridos desde que el visitante accedió al sitio.  Será útil si prop10 tiene las rutas habilitadas.  Si agrega la métrica “salidas” al informe prop10, se mostrará un informe “de diagrama de dispersión” granular de cuántos minutos duró una visita antes de que abandonara el sitio.

## Historial de versiones

### 2.1 (19 de marzo de 2021)

* Se ha añadido el número de versión como datos de contexto.

### 2.0 (2 de mayo de 2018)

* Versión puntual (reanálisis/reescritura completa del complemento).
